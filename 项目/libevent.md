# 教程

阻塞IO：也即异步IO，调用时，只有完成后或超时才返回。

## 单进程版

客户端

```c
const char query[] =
    "GET / HTTP/1.0\r\n"
    "Host: www.google.com\r\n"
    "\r\n";
const char hostname[] = "www.google.com";
h = gethostbyname(hostname);						//获取ip地址
fd = socket(AF_INET, SOCK_STREAM, 0);				//申请tcp socket
sin.sin_family = AF_INET;							//服务端地址设置
sin.sin_port = htons(80);
sin.sin_addr = *(struct in_addr*)h->h_addr;
connect(fd, (struct sockaddr*) &sin, sizeof(sin))	//发起连接

cp = query;								
remaining = strlen(query);
while (remaining) {									//主动发送数据，循环操作防止一次发送不完数据
    n_written = send(fd, cp, remaining, 0);
    remaining -= n_written;
    cp += n_written;
}

while (1) {											//循环接收数据
    ssize_t result = recv(fd, buf, sizeof(buf), 0);
    fwrite(buf, 1, result, stdout);
}
```

## 单进程处理多连接

当有多条连接时，一个一个的判断，一个连接会阻塞其他连接。修改文件描述符，使其变为非阻塞：`fcntl(fd, F_SETFL, O_NONBLOCK);`。

```c
for (i=0; i < n_sockets; ++i)							//设置socket描述符为非阻塞
    fcntl(fd[i], F_SETFL, O_NONBLOCK);

while (1) {
    for (i=0; i < n_sockets; ++i) {						//不断循环检查各个socket
        n = recv(fd[i], buf, sizeof(buf), 0);			//会阻塞
        handle_input(fd[i], buf, n);
    }
}
```

## 多进程版本

创建进程或线程耗费时间。

```c
void child(int fd) {								//处理孩子进程
    while (1) {
        result = recv(fd, &ch, 1, 0);				//接收数据
        //...
        send(fd, outbuf, outbuf_used, 0);			//发送数据
    }
}

void run(void) {									//主进程，监听
    sin.sin_family = AF_INET;						//地址设置
    sin.sin_addr.s_addr = 0;
    sin.sin_port = htons(40713);
    listener = socket(AF_INET, SOCK_STREAM, 0);		//申请套接字
    
    int one = 1;									//设置socket属性，端口可重复利用，time_waiting状态
    setsockopt(listener, SOL_SOCKET, SO_REUSEADDR, &one, sizeof(one));
    bind(listener, (struct sockaddr*)&sin, sizeof(sin));			//本地地址
    listen(listener, 16)

    while (1) {
        struct sockaddr_storage ss;
        socklen_t slen = sizeof(ss);
        int fd = accept(listener, (struct sockaddr*)&ss, &slen);	//监听连接
    
        if (fork() == 0) {											//创建新进程，处理发送的数据
            child(fd);
        }
    }
}

```

## select

缺点是：需要遍历所有的描述符，用户空间，查询时间与用户**提供监听的描述符个**数有关，内核空间，时间与监听的**描述符最大值**有关。大约等于程序使用的总描述符数量。

poll、epoll提供了更高效的添加监听、删除监听等方法。

```c
struct fd_state {
    char buffer[MAX_LINE];
    size_t buffer_used;

    int writing;
    size_t n_written;
    size_t write_upto;
};

struct fd_state *alloc_fd_state(void){							//为描述符 申请内存资源，
    struct fd_state *state = malloc(sizeof(struct fd_state));
    if (!state)
        return NULL;
    state->buffer_used = state->n_written = state->writing = state->write_upto = 0;
    return state;
}
void free_fd_state(struct fd_state *state) {					//删除资源
    free(state);
}
void make_nonblocking(int fd) {									//设置描述符非阻塞
    fcntl(fd, F_SETFL, O_NONBLOCK);
}
int do_read(int fd, struct fd_state *state) {					//读操作，接收数据
    while (1) {
        result = recv(fd, buf, sizeof(buf), 0); 				//非阻塞，无数据，返回-1 EAGAIN
        //...
    }
}
int do_write(int fd, struct fd_state *state) {					//写操作，发送数据
    while (state->n_written < state->write_upto) {				//以循环的方式，写完所有数据
        ssize_t result = send(fd, state->buffer + state->n_written,
                              state->write_upto - state->n_written, 0);
        state->n_written += result;
    }
}

void run(void) {
    struct fd_state *state[FD_SETSIZE];
    fd_set readset, writeset, exset;
    for (i = 0; i < FD_SETSIZE; ++i)
        state[i] = NULL;
    
    sin.sin_family = AF_INET;									//服务器地址，socket、绑定、监听
    sin.sin_addr.s_addr = 0;
    sin.sin_port = htons(40713);
    listener = socket(AF_INET, SOCK_STREAM, 0);
    make_nonblocking(listener);
    int one = 1;
    setsockopt(listener, SOL_SOCKET, SO_REUSEADDR, &one, sizeof(one));
	bind(listener, (struct sockaddr*)&sin, sizeof(sin));
    listen(listener, 16);

    maxfd = listener;
    FD_ZERO(&readset);
    FD_ZERO(&writeset);
    FD_ZERO(&exset);
    FD_SET(listener, &readset);								//添加到读监听集合

    while (1) {												//遍历所有	
        
        for (i=0; i < FD_SETSIZE; ++i) {					//遍历监听的描述符，
            if (state[i]) {
                if (i > maxfd)
                    maxfd = i;
                FD_SET(i, &readset);		//添加到读监听集合
                if (state[i]->writing) {
                    FD_SET(i, &writeset);
                }
            }
        }

        select(maxfd+1, &readset, &writeset, &exset, NULL);		//等待事件发生

        if (FD_ISSET(listener, &readset)) {						//有新连接请求
            struct sockaddr_storage ss;
            socklen_t slen = sizeof(ss);
            int fd = accept(listener, (struct sockaddr*)&ss, &slen);//新连接的socket
            make_nonblocking(fd);
            state[fd] = alloc_fd_state();
        }

        for (i=0; i < maxfd+1; ++i) {							//其他连接
            if (i == listener)
                continue;
            if (FD_ISSET(i, &readset)) {			//读事件
                r = do_read(i, state[i]);
            }
            if (r == 0 && FD_ISSET(i, &writeset)) {	//写事件
                r = do_write(i, state[i]);
            }
        }
    }
}
```

## libevent

将socket描述符与对应事件处理函数关联起来，当事件发生时，会自动调用对应事件。

```c
/* 1.初始化
 * 2.建立监听连接listener，添加listener的读事件
 * 3.如果有新连接请求，则创建新套接字fd，并添加fd的读事件
 * 4.如果其他连接有读事件，读取数据，删除读事件，添加写事件;
 *			    写事件完成后，删除写事件
 */
struct event_base *base = event_base_new();
evutil_socket_t listener = socket(AF_INET, SOCK_STREAM, 0);
evutil_make_socket_nonblocking(listener);
struct event *listener_event = event_new(base, listener, EV_READ|EV_PERSIST, do_accept, (void*)base);
event_add(listener_event, NULL);
event_base_dispatch(base);
```



```c
void do_read(evutil_socket_t fd, short events, void *arg);
void do_write(evutil_socket_t fd, short events, void *arg);

struct fd_state {
    char buffer[MAX_LINE];
    size_t buffer_used;

    size_t n_written;
    size_t write_upto;

    struct event *read_event;
    struct event *write_event;
};
/************************申请资源*****************************/
struct fd_state * alloc_fd_state(struct event_base *base, evutil_socket_t fd) {
    struct fd_state *state = malloc(sizeof(struct fd_state));
    //关联读、写事件和对应的处理函数
    state->read_event = event_new(base, fd, EV_READ|EV_PERSIST, do_read, state);
    state->write_event = event_new(base, fd, EV_WRITE|EV_PERSIST, do_write, state);
    state->buffer_used = state->n_written = state->write_upto = 0;
    return state;
}
/************************释放资源*****************************/
void free_fd_state(struct fd_state *state) {
    event_free(state->read_event);
    event_free(state->write_event);
    free(state);
}

void do_read(evutil_socket_t fd, short events, void *arg) {
    struct fd_state *state = arg;		//参数转对应的结构
    while (1) {
        result = recv(fd, buf, sizeof(buf), 0);
        if (result <= 0) break;						//读完跳出
       	//....
        event_add(state->write_event, NULL);		//调写函数
    }
}

void do_write(evutil_socket_t fd, short events, void *arg) {
    struct fd_state *state = arg;
    while (state->n_written < state->write_upto) {
        ssize_t result = send(fd, state->buffer + state->n_written,
                              state->write_upto - state->n_written, 0);
        //...
    }
    event_del(state->write_event);					//删除写事件
}

void do_accept(evutil_socket_t listener, short event, void *arg) {
    struct event_base *base = arg;
    struct sockaddr_storage ss;
    socklen_t slen = sizeof(ss);
    int fd = accept(listener, (struct sockaddr*)&ss, &slen);	//新连接
    
    struct fd_state *state;
    evutil_make_socket_nonblocking(fd);
    state = alloc_fd_state(base, fd);
    event_add(state->read_event, NULL);							//添加读事件
}

void run(void) {
    struct event_base *base = event_base_new();				//初始化
    evutil_socket_t listener = socket(AF_INET, SOCK_STREAM, 0);
    evutil_make_socket_nonblocking(listener);
    int one = 1;
    setsockopt(listener, SOL_SOCKET, SO_REUSEADDR, &one, sizeof(one));
    
    sin.sin_family = AF_INET;
    sin.sin_addr.s_addr = 0;
    sin.sin_port = htons(40713);

    bind(listener, (struct sockaddr*)&sin, sizeof(sin));
    listen(listener, 16);
    //创建新的事件
    struct event *listener_event = event_new(base, listener, EV_READ|EV_PERSIST, do_accept, (void*)base);
    event_add(listener_event, NULL);		//增加监听
    event_base_dispatch(base);				//运行，直到没有数据被注册
}
```

# 源码

## event

### 结构体

```c
/***************************event_base结构体******************************************/
#define TAILQ_HEAD(name, type)		\
struct name {						\
	struct type *tqh_first;			\		//第一个元素
	struct type **tqh_last;			\		//后一个元素指针
}
#define TAILQ_ENTRY(type)			\
struct {							\
	struct type *tqe_next;			\		//下一个元素
	struct type **tqe_prev;			\		//前一个元素指针
}
TAILQ_HEAD (event_list, event);

struct event_base {
	const struct eventop *evsel;			//指向具体的操作函数地址 
	void *evbase;							//初始化函数，=base->evsel->init(base);
	
    int event_count;						//总事件数		
	int event_count_active;					//活跃的事件数
	int event_gotterm;						//终止循环		
	int event_break;						//立即终止循环

	struct event_list **activequeues;		//活跃事件列表、个数
	int nactivequeues;

	struct evsignal_info sig;

	struct event_list eventqueue;
	struct timeval event_tv;				//定时器

	struct min_heap timeheap;				//小顶堆

	struct timeval tv_cache;
};

struct event {
	TAILQ_ENTRY (event) ev_next;					//链表结构，
	TAILQ_ENTRY (event) ev_active_next;
	TAILQ_ENTRY (event) ev_signal_next;
	unsigned int min_heap_idx;						//超时

	struct event_base *ev_base;						//根

	int ev_fd;										//socket套接字
	short ev_events;								//事件
	short ev_ncalls;
	short *ev_pncalls;	
	struct timeval ev_timeout;
        int ev_pri;									//越小越大
	void (*ev_callback)(int, short, void *arg);
	void *ev_arg;
	int ev_res;										//结果
	int ev_flags;
};

typedef struct min_heap {
    struct event** p;
    unsigned n, a;
} min_heap_t;

#ifdef HAVE_SELECT									//选择具体实现
extern const struct eventop selectops;
static const struct eventop *eventops[] = {
    ....
    #ifdef HAVE_SELECT
        &selectops,
    #endif
}
```

### 初始化

```c
/****************创建一个event_base结构体***************************/
struct event_base * event_base_new(void) {
	struct event_base *base = calloc(1, sizeof(struct event_base));
	detect_monotonic();
	gettime(base, &base->event_tv);									//base时间设置
	min_heap_ctor(&base->timeheap);									//初始化堆
	TAILQ_INIT(&base->eventqueue);
	base->sig.ev_signal_pair[0] = -1;
	base->sig.ev_signal_pair[1] = -1;
	
	for (i = 0; eventops[i] && !base->evbase; i++) {				//选择第一个可用的API
		base->evsel = eventops[i];
		base->evbase = base->evsel->init(base);
	}

	event_base_priority_init(base, 1);								//创建事件队列

	return (base);
}

```

### 添加event

```c
int event_add(struct event *ev, const struct timeval *tv) {  
	struct event_base *base = ev->ev_base;				//根base
	const struct eventop *evsel = base->evsel;			//API函数集
	void *evbase = base->evbase;						//初始化
	int res = 0;

	if (tv != NULL && !(ev->ev_flags & EVLIST_TIMEOUT)) {
		if (min_heap_reserve(&base->timeheap,
			1 + min_heap_size(&base->timeheap)) == -1)
			return (-1);  /* ENOMEM == errno */
	}

	if ((ev->ev_events & (EV_READ|EV_WRITE|EV_SIGNAL)) &&
	    !(ev->ev_flags & (EVLIST_INSERTED|EVLIST_ACTIVE))) {
		res = evsel->add(evbase, ev);							//调用对应函数初始化ev
		if (res != -1)
			event_queue_insert(base, ev, EVLIST_INSERTED);		//事件插入到队列
	}

	/* 
	 * we should change the timout state only if the previous event
	 * addition succeeded.
	 */
	if (res != -1 && tv != NULL) {
		struct timeval now;

		/* 
		 * we already reserved memory above for the case where we
		 * are not replacing an exisiting timeout.
		 */
		if (ev->ev_flags & EVLIST_TIMEOUT)
			event_queue_remove(base, ev, EVLIST_TIMEOUT);

		/* Check if it is active due to a timeout.  Rescheduling
		 * this timeout before the callback can be executed
		 * removes it from the active list. */
		if ((ev->ev_flags & EVLIST_ACTIVE) &&
		    (ev->ev_res & EV_TIMEOUT)) {
			/* See if we are just active executing this
			 * event in a loop
			 */
			if (ev->ev_ncalls && ev->ev_pncalls) {
				/* Abort loop */
				*ev->ev_pncalls = 0;
			}
			
			event_queue_remove(base, ev, EVLIST_ACTIVE);
		}

		gettime(base, &now);
		evutil_timeradd(&now, tv, &ev->ev_timeout);

		event_queue_insert(base, ev, EVLIST_TIMEOUT);
	}

	return (res);
}

void event_queue_insert(struct event_base *base, struct event *ev, int queue) {
	if (~ev->ev_flags & EVLIST_INTERNAL)
		base->event_count++;

	ev->ev_flags |= queue;
	switch (queue) {
	case EVLIST_INSERTED:
		TAILQ_INSERT_TAIL(&base->eventqueue, ev, ev_next);
		break;
	case EVLIST_ACTIVE:
		base->event_count_active++;
		TAILQ_INSERT_TAIL(base->activequeues[ev->ev_pri], ev,ev_active_next);
		break;
	case EVLIST_TIMEOUT: {
		min_heap_push(&base->timeheap, ev);
		break;
	}
	default:
		event_errx(1, "%s: unknown queue %x", __func__, queue);
	}
}
```



## select

```c
/***********************选择哪种API**************************/
#ifdef HAVE_SELECT					//select选项
extern const struct eventop selectops;
#endif

static const struct eventop *eventops[] = { 	//可选项目
#ifdef HAVE_EVENT_PORTS
	&evportops,
#endif
#ifdef HAVE_WORKING_KQUEUE
	&kqops,
#endif
#ifdef HAVE_EPOLL
	&epollops,
#endif
#ifdef HAVE_DEVPOLL
	&devpollops,
#endif
#ifdef HAVE_POLL
	&pollops,
#endif
#ifdef HAVE_SELECT
	&selectops,
#endif
#ifdef WIN32
	&win32ops,
#endif
	NULL
};

struct eventop {		//API抽象
	const char *name;
	void *(*init)(struct event_base *);
	int (*add)(void *, struct event *);
	int (*del)(void *, struct event *);
	int (*dispatch)(struct event_base *, void *, struct timeval *);
	void (*dealloc)(struct event_base *, void *);
	/* set if we need to reinitialize the event base */
	int need_reinit;
};
/************************select 具体实现,可以执行的操作************************************/
static void *select_init	(struct event_base *);				//具体实现
static int select_add		(void *, struct event *);
static int select_del		(void *, struct event *);
static int select_dispatch	(struct event_base *, void *, struct timeval *);
static void select_dealloc     (struct event_base *, void *);
const struct eventop selectops = {								
	"select",
	select_init,
	select_add,
	select_del,
	select_dispatch,
	select_dealloc,
	0
};
```



```c
struct selectop {
	int event_fds;		/* Highest fd in fd set */
	int event_fdsz;
	fd_set *event_readset_in;
	fd_set *event_writeset_in;
	fd_set *event_readset_out;
	fd_set *event_writeset_out;
	struct event **event_r_by_fd;
	struct event **event_w_by_fd;
};
/**********************初始化*************************/
static void * select_init(struct event_base *base) {
	struct selectop *sop;

	/* Disable select when this environment variable is set */
	if (evutil_getenv("EVENT_NOSELECT"))
		return (NULL);

	if (!(sop = calloc(1, sizeof(struct selectop))))
		return (NULL);

	select_resize(sop, howmany(32 + 1, NFDBITS)*sizeof(fd_mask));

	evsignal_init(base);

	return (sop);
}
/**********************************************************/
static int select_resize(struct selectop *sop, int fdsz) {
	int n_events, n_events_old;

	fd_set *readset_in = NULL;
	fd_set *writeset_in = NULL;
	fd_set *readset_out = NULL;
	fd_set *writeset_out = NULL;
	struct event **r_by_fd = NULL;
	struct event **w_by_fd = NULL;

	n_events = (fdsz/sizeof(fd_mask)) * NFDBITS;
	n_events_old = (sop->event_fdsz/sizeof(fd_mask)) * NFDBITS;

	if (sop->event_readset_in)
		check_selectop(sop);

	if ((readset_in = realloc(sop->event_readset_in, fdsz)) == NULL)
		goto error;
	sop->event_readset_in = readset_in;
	if ((readset_out = realloc(sop->event_readset_out, fdsz)) == NULL)
		goto error;
	sop->event_readset_out = readset_out;
	if ((writeset_in = realloc(sop->event_writeset_in, fdsz)) == NULL)
		goto error;
	sop->event_writeset_in = writeset_in;
	if ((writeset_out = realloc(sop->event_writeset_out, fdsz)) == NULL)
		goto error;
	sop->event_writeset_out = writeset_out;
    
	if ((r_by_fd = realloc(sop->event_r_by_fd, n_events*sizeof(struct event*))) == NULL)
		goto error;
	sop->event_r_by_fd = r_by_fd;
	if ((w_by_fd = realloc(sop->event_w_by_fd, n_events * sizeof(struct event*))) == NULL)
		goto error;
	sop->event_w_by_fd = w_by_fd;

	memset((char *)sop->event_readset_in + sop->event_fdsz, 0, fdsz - sop->event_fdsz);
	memset((char *)sop->event_writeset_in + sop->event_fdsz, 0, fdsz - sop->event_fdsz);
	memset(sop->event_r_by_fd + n_events_old, 0, (n_events-n_events_old) * sizeof(struct event*));
	memset(sop->event_w_by_fd + n_events_old, 0, (n_events-n_events_old) * sizeof(struct event*));

	sop->event_fdsz = fdsz;
	check_selectop(sop);

	return (0);

 error:
	event_warn("malloc");
	return (-1);
}
/**********************************************************/
static int select_add(void *arg, struct event *ev) {
	struct selectop *sop = arg;

	if (ev->ev_events & EV_SIGNAL)
		return (evsignal_add(ev));

	check_selectop(sop);
	/*
	 * Keep track of the highest fd, so that we can calculate the size
	 * of the fd_sets for select(2)
	 */
	if (sop->event_fds < ev->ev_fd) {
		int fdsz = sop->event_fdsz;

		if (fdsz < sizeof(fd_mask))
			fdsz = sizeof(fd_mask);

		while (fdsz < (howmany(ev->ev_fd + 1, NFDBITS) * sizeof(fd_mask)))
			fdsz *= 2;

		if (fdsz != sop->event_fdsz) {
			if (select_resize(sop, fdsz)) {
				check_selectop(sop);
				return (-1);
			}
		}

		sop->event_fds = ev->ev_fd;
	}

	if (ev->ev_events & EV_READ) {
		FD_SET(ev->ev_fd, sop->event_readset_in);
		sop->event_r_by_fd[ev->ev_fd] = ev;
	}
	if (ev->ev_events & EV_WRITE) {
		FD_SET(ev->ev_fd, sop->event_writeset_in);
		sop->event_w_by_fd[ev->ev_fd] = ev;
	}
	check_selectop(sop);

	return (0);
}
```

## event

```c
/*************************事件*******************************/
struct event {
	TAILQ_ENTRY (event) ev_next;
	TAILQ_ENTRY (event) ev_active_next;
	TAILQ_ENTRY (event) ev_signal	_next;
	unsigned int min_heap_idx;	/* for managing timeouts */

	struct event_base *ev_base;

	int ev_fd;
	short ev_events;
	short ev_ncalls;
	short *ev_pncalls;	/* Allows deletes in callback */

	struct timeval ev_timeout;

	int ev_pri;		/* smaller numbers are higher priority */

	void (*ev_callback)(int, short, void *arg);
	void *ev_arg;

	int ev_res;		/* result passed to event callback */
	int ev_flags;
};
```



```c
struct event_base {
	const struct eventop *evsel;
	void *evbase;
	int event_count;		/* counts number of total events */
	int event_count_active;	/* counts number of active events */

	int event_gotterm;		/* Set to terminate loop */
	int event_break;		/* Set to terminate loop immediately */

	/* active event management */
	struct event_list **activequeues;
	int nactivequeues;

	/* signal handling info */
	struct evsignal_info sig;

	struct event_list eventqueue;
	struct timeval event_tv;

	struct min_heap timeheap;

	struct timeval tv_cache;
};

struct event_base * event_base_new(void) {
	int i;
	struct event_base *base;

	if ((base = calloc(1, sizeof(struct event_base))) == NULL)
		event_err(1, "%s: calloc", __func__);

	event_sigcb = NULL;
	event_gotsig = 0;

	detect_monotonic();
	gettime(base, &base->event_tv);
	
	min_heap_ctor(&base->timeheap);
	TAILQ_INIT(&base->eventqueue);
	base->sig.ev_signal_pair[0] = -1;
	base->sig.ev_signal_pair[1] = -1;
	
	base->evbase = NULL;
	for (i = 0; eventops[i] && !base->evbase; i++) {
		base->evsel = eventops[i];

		base->evbase = base->evsel->init(base);
	}

	if (base->evbase == NULL)
		event_errx(1, "%s: no event mechanism available", __func__);

	if (evutil_getenv("EVENT_SHOW_METHOD")) 
		event_msgx("libevent using: %s\n",
			   base->evsel->name);

	/* allocate a single active event queue */
	event_base_priority_init(base, 1);

	return (base);
}
```



## log

`__attribute__(format (archetype, string-index, first-to-check))`：使编译器检查函数声明和函数实际调用参数之间的格式化字符串是否匹配。

+ `archetype`指定是哪种风格；
+ `string-index`指定传入函数的第几个参数是格式化字符串；
+ `first-to-check`指定从函数的第几个参数开始按上述规则进行检查。

获取变量参数：

+ 变量参数指针：`typedef char* va_list; va_list ap;`

+ 初始化ap，`void va_start(va_list ap, last_arg);`
+ 获取参数：`type va_arg ( va_list ap, type );`，获取指定类型的参数，并指向下一参数。
+ 结束解析：`void va_end ( va_list ap );`

```c
/*********************log******************************/
#define EV_CHECK_FMT(a,b) __attribute__((format(printf, a, b))) 	//以printf的格式检查函数
void event_err(int eval, const char *fmt, ...) EV_CHECK_FMT(2,3);
void event_err(int eval, const char *fmt, ...) {
	va_list ap;					//指针，指向变量参数 
	
	va_start(ap, fmt);	//初始化变量指针 第二个参数为变量参数之前的参数，
	_warn_helper(_EVENT_LOG_ERR, errno, fmt, ap);
	va_end(ap);
	exit(eval);
}
/*********************所有log level******************************/
_warn_helper(_EVENT_LOG_ERR, errno, fmt, ap);		//event_err
_warn_helper(_EVENT_LOG_WARN, errno, fmt, ap);		//event_warn

_warn_helper(_EVENT_LOG_ERR, -1, fmt, ap);			//event_errx
_warn_helper(_EVENT_LOG_WARN, -1, fmt, ap);			//event_warnx
_warn_helper(_EVENT_LOG_MSG, -1, fmt, ap);			//event_msgx
_warn_helper(_EVENT_LOG_DEBUG, -1, fmt, ap);		//_event_debugx

static void _warn_helper(int severity, int log_errno, const char *fmt, va_list ap) {
	char buf[1024];
	size_t len;

	if (fmt != NULL)
		evutil_vsnprintf(buf, sizeof(buf), fmt, ap);
	else
		buf[0] = '\0';

	if (log_errno >= 0) {
		len = strlen(buf);
		if (len < sizeof(buf) - 3) {		//后面添加: strerror(log_errno) 返回错误号指定的字符串
			evutil_snprintf(buf + len, sizeof(buf) - len, ": %s",
			    strerror(log_errno));
		}
	}

	event_log(severity, buf);
}
/*********************安装格式得到字符串******************************/
int evutil_vsnprintf(char *buf, size_t buflen, const char *format, va_list ap) {
#ifdef _MSC_VER
	int r = _vsnprintf(buf, buflen, format, ap);	//调用_vsnprintf向buf里打印数据
	buf[buflen-1] = '\0';
	if (r >= 0)
		return r;
	else
		return _vscprintf(format, ap);
#else
	int r = vsnprintf(buf, buflen, format, ap);
	buf[buflen-1] = '\0';
	return r;
#endif
}
int evutil_snprintf(char *buf, size_t buflen, const char *format, ...){
	int r;
	va_list ap;
	va_start(ap, format);
	r = evutil_vsnprintf(buf, buflen, format, ap);
	va_end(ap);
	return r;
}
/******************打印错误*************************************/
typedef void (*event_log_cb)(int severity, const char *msg);
static event_log_cb log_fn = NULL;
static void event_log(int severity, const char *msg) {
	if (log_fn)
		log_fn(severity, msg);
	else {
		const char *severity_str;
		switch (severity) {
		case _EVENT_LOG_DEBUG:
			severity_str = "debug";
			break;
		case _EVENT_LOG_MSG:
			severity_str = "msg";
			break;
		case _EVENT_LOG_WARN:
			severity_str = "warn";
			break;
		case _EVENT_LOG_ERR:
			severity_str = "err";
			break;
		default:
			severity_str = "???";
			break;
		}
		(void)fprintf(stderr, "[%s] %s\n", severity_str, msg);	//输出到stderr 格式[ ] 错误...
	}
}

```


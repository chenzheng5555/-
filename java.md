# 入门

## 运行

+ 一个 Java 程序可以认为是**一系列对象的集合**，而这些对象通过调用彼此的方法来协同工作。一个文件是一个编译单元，且**只有一个public类**。其他类不能加public，编译时，一个文件里的类会各自生成对应的class文件。
+ **源文件名必须和类名相同**。当保存文件的时候，使用类名作为文件名保存。

```java
// MainTest.java 
// package com.learnjava 			//包名
public class MainTest {				//源文件名必须和类名相同。当保存文件的时候，使用类名作为文件名保存
    public static void main(String[] args){ 	//主方法入口,所有的 Java 程序由该方法开始执行。
        System.out.println("hello");
    }
}
```

+ JVM加载某个类时，需要找到对应的.class文件，classpath就是用来储存这些查找目录的变量。JVM会依次在这些目录中进行查找，直到找到。对于java核心包，不需要将其加入到classpath中，jvm可以自己找到。可以在启动JVM时设置`classpath`。`java -classpath .;C:\work\project1\bin`。缩写cp

```shell
javac MainTest.java		# 编译生成字节码 
javac -d . Main.java 	# 有包，添加d直接生成包的目录 com/learn/Main.class

java MainTest			# jvm执行，
java com.learn.Main 	# 有包的执行方法。类名为com.learn.Main

# Main中依赖了app.jar，a.jar...多个分包，将其与Main放在一起运行，
# 使用Maven只需将其配置依赖，则会自动下，指定classpath,.表示当前目录，负责找不到Main
java -cp .;app.jar;a.jar;b.jar com.liaoxuefeng.sample.Main  #包含其他jar包，  cp添加搜索路径
```

![ZSSDMld](img/ZSSDMld.png)



## 数据类型

- 基本类型：`byte`，`short`，`int`，`long`，`boolean`，`float`，`double`，`char`。
- 引用类型：所有`class`和`interface`类型。为了把基本类型视为引用类型，为每个基本类型提供了对应的包装类型。
- Java编译器可以自动在**基本类型和包装类型**之间进行转型。
- 所有的**包装类型都是不变类**。比较必须使用equals()。

### 字符串

字符：因为Java在内存中总是使用Unicode表示字符，占用**两个字节**。

字符串：

+ **String**字符串**不可变**。这种不可变性是通过内部的`private final char[]`字段，较新的JDK版本的`String`则以`byte[]`存储。
+ **StringBuilder**，它是一个可变对象，可以预分配缓冲区，这样，往`StringBuilder`中新增字符时，不会创建新的临时对象。
+ **StringJoiner**(", ", "Hello ", "!");以","进行连接。静态方法join()使用该类。

```java
String s1 = "Hello!";					
s1.equals("Hello!");					//比较		
byte[] b2 = s1.getBytes("UTF-8"); 		// 按UTF-8编码转换

//字符串的定义
public final class String {
    private final char[] value;			//所以字符串不可修改，新版： private final byte[] value;
    private final int offset;			//		           	     private final byte coder; 
    private final int count;
}
```

### JavaBean

面向对象规范：1）若干`private`实例字段；2）通过`public`方法来读写实例字段。

如果读写方法符合以下这种命名规范：这种类就被称为JavaBean。

```java
public Type getXyz()				// 读方法: 特殊boolean isXyz()
public void setXyz(Type value)		// 写方法:
```

### enum

`enum`常量本身带有类型信息，便于检查。不同类型的枚举不能互相比较或者赋值。

`enum`类型的每个常量在JVM中只有一个唯一实例。

- 定义的`enum`类型总是继承自`java.lang.Enum`，且无法被继承；
- 只能定义出`enum`的实例，而无法通过`new`操作符创建`enum`的实例；
- 定义的每个实例都是引用类型的唯一实例；
- 可以将`enum`类型用于`switch`语句。

```java
public enum Color {
    RED, GREEN, BLUE;
}
//类似于
public final class Color extends Enum { // 继承自Enum，标记为final class
    // 每个实例均为全局唯一:
    public static final Color RED = new Color();
    public static final Color GREEN = new Color();
    public static final Color BLUE = new Color();
    // private构造方法，确保外部无法调用new操作符:
    private Color() {}
}
Color col = Color.RED;
```

### record

+ 定义class时使用`final`，无法派生子类；
+ 每个字段使用`final`，保证创建实例后无法修改任何字段。

```java
public record Point(int x, int y) {} 
//等价于
public final class Point extends Record {
    private final int x;
    private final int y;
    ...
}
```









## 类

```java
// 接口
interface Person {				//等价于abstract class Person 
    int MALE = 1;				//等价于public static final int MALE = 1;
}
if (p instanceof Person)		//判断p是否为Person类
```

### 类加载顺序

+ 静态代码块，在类第一次加载的时候，会初始化一次。
+ 初始块与构造方法是一家子，但是初始块会在构造函数前执行。适合各构造函数的公共部分。

```java
//静态块----->非静态快----->构造函数。
//继承关系 父静态块----->子静态块----->父[非静态块----->构造函数]----->子[]
```





## 集合

```java
List<String> list = new ArrayList<>(); 				//创建数组链表
list<String> list = new LinkedList<>();
list.get(i);

Map<String, Student> map = new HashMap<>(); 		//键-值映射表
Map<DayOfWeek, String> map = new EnumMap<>(DayOfWeek.class);
//如果a<b，则返回负数，通常是-1，如果a==b，则返回0，如果a>b，则返回正数，不需要equals
Map<String, Integer> map = new TreeMap<>(cmp);		//key必须实现Comparable,
map.put("Xiao Ming", s);
map.containsKey("Xiao Ming");
map.get("Xiao Ming");

Set<String> set = new HashSet<>();					//需要hashCode	
set.add("abc");
set.contains("xyz");

Queue<String> q = new LinkedList<>();
q.offer("apple");q.add("");
q.peek();q.element();
q.poll();q.remove();

Queue<String> q = new PriorityQueue<>();

Deque<String> deque = new LinkedList<>();
deque.offerLast("A");deque.offerFirst("C");


for (var key : map.keySet()){}
for (Map.Entry<String, Integer> entry : map.entrySet()) {}
```



## 文件操作

```java
File f = new File("C:\\Windows\\notepad.exe");
f.listFiles();

InputStream input = new FileInputStream("src/readme.txt");
InputStream input = new ByteArrayInputStream({1,2,3});
input.read(); 

OutputStream output = new FileOutputStream("out/readme.txt");
output.write(108); 

//通过一个“基础”组件再叠加各种“附加”功能组件的模式，称之为Filter模式（或者装饰器模式：Decorator）。它可以让我们通过少量的类来实现各种功能的组合：
InputStream file = new FileInputStream("test.gz");
InputStream buffered = new BufferedInputStream(file);
InputStream gzip = new GZIPInputStream(buffered);
```





配置文件

```java
Properties props = new Properties();
props.load(getClass().getResourceAsStream("/common/setting.properties"));
String filepath = props.getProperty("last_open_file");
```



## 文件结构	

### 包

```java
package com.learn.java
```

**jar包**，把`package`组织的目录层级，以及各个目录下的所有文件（包括`.class`文件和其他文件）都打成一个jar文件。也就是一个zip格式的压缩文件。

jar包还可以包含一个特殊的`/META-INF/MANIFEST.MF`文件，`MANIFEST.MF`是纯文本，可以指定`Main-Class`和其它信息。JVM会自动读取这个`MANIFEST.MF`文件，如果存在`Main-Class`，我们就不必在命令行指定启动的类名，

**包作用域**是指一个类允许访问同一个`package`的没有`public`、`private`修饰的`class`。

### 模块

jar只是用于存放class的容器，它并不关心class之间的依赖。**为了解决依赖引入了模块**。以`.jmod`扩展名标识。

**模块之间的依赖关系已经被写入到模块内的**`module-info.class`。所有的模块都直接或间接地依赖`java.base`模块，

我们可以打包好的模块，进一步打包JRE。从而达到JRE瘦身。

```java
//Main.java
package com.itranswarp.sample;
import javax.xml.XMLConstants;  					// 引用了其他类，依赖
public class Main {
	public static void main(String[] args) {
		Greeting g = new Greeting();				// Greeting.java里的类
		System.out.println(g.hello(XMLConstants.XML_NS_PREFIX));
	}
}

//module-info.java
//依赖文件 hello.world 模块名
module hello.world {
	requires java.base; //可不写，任何模块都会自动引入java.base
	requires java.xml;	//如果删掉，则 Main.java里import 处会报错 ：程序包 javax.xml 不可见
}
```

```shell
-── src									#源代码
    ├── com
    │    └── learnjava
    │         ├── Greeting.java
    │         └── Main.java
    └── module-info.java				#模块的描述文件，依赖

# 编译java文件到bin目录下 -d 自动按类的结构生成对应的目录结构 
javac -d bin src/module-info.java src/com/learnjava/*.java
# 将bin目录下的所有class打包到hello.jar 并声明有main的类 --main-class 识别main函数  -C 包含
jar --create --file hello.jar --main-class com.itranswarp.sample.Main -C bin . 	
# 运行jar包 
java -jar hello.jar
# 把jar包转换为模块,
jmod create --class-path hello.jar hello.jmod 	
# 继续添加必要的包，将其打包为jre
jlink --module-path hello.jmod --add-modules java.base,java.xml,hello.world --output jre/ 	
# 运行我们打包的jre模块 jre/bin/java用到的是我们打包到的模块中java
jre/bin/java --module hello															
```

访问权限，只有模块声明了导出的包，外部代码才被允许访问。

### maven

Maven就是是专门为Java项目打造的管理和构建工具，设置依赖。目录结构一致。

```java
a-maven-project				//使用Maven管理的Java项目  目录结构
├── pom.xml					//项目描述文件
├── src
│   ├── main
│   │   ├── java			//源码
│   │   └── resources		//资源文件
│   └── test				//测试
│       ├── java
│       └── resourc
└── target					//所有编译、打包生成的文件
```

```xml
<?xml version="1.0" encoding="UTF-8"?>
<project xmlns="http://maven.apache.org/POM/4.0.0"
         xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
         xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/xsd/maven-4.0.0.xsd">
    <modelVersion>4.0.0</modelVersion>

    <groupId>org.example</groupId>
    <artifactId>MavenTest</artifactId>
    <version>1.0-SNAPSHOT</version>
    
	<dependencies>			<!--依赖，Maven就会自动下载这个依赖包并把它放到classpath中。-->
        <dependency>	
            <groupId>commons-logging</groupId>
            <artifactId>commons-logging</artifactId>
            <version>1.2</version>
        </dependency>
	</dependencies>
</project>
```

| 作用scope | 说明                                          |
| --------- | --------------------------------------------- |
| compile   | 编译时需要用到该jar包（默认）                 |
| test      | 编译Test时需要用到该jar包                     |
| runtime   | 编译时不需要，但运行时需要用到                |
| provided  | 编译时需要用到，但运行时由JDK或某个服务器提供 |

默认下载位置：`Default: ${user.home}/.m2/repository`。



## 泛型

Java使用擦拭法实现泛型：

- 编译器把类型`<T>`视为`Object`；
- 编译器根据`<T>`实现安全的强制转型。

Java的泛型是由编译器在编译时实行的，编译器内部永远把所有类型`T`视为`Object`处理，但是，在需要转型的时候，编译器会根据`T`的类型自动为我们实行安全地强制转型。

泛型类型`<T>`不能用于静态方法。

```java
public class ArrayList<T> {			//模板
    private T[] array;
    private int size;
    public void add(T e) {...}
    public void remove(int index) {...}
    public T get(int index) {...}
}

public interface Comparable<T> {	//接口模板
}

List<String> list = new ArrayList<String>();
```





## Reflection

+ **动态加载**，每加载一种`class`，JVM就为其创建一个`Class`类型的实例，并关联起来。**Class实例都是唯一的**。

+ JVM持有的每个`Class`实例都指向一个数据类型（`class`或`interface`）：一**个`Class`实例包含了该`class`的所有完整信息**：类名、包名、父类、实现的接口、所有方法、字段。

```java
//获取类的Class实例
Class cls = String.class;							//类的静态变量
Class cls = s.getClass();							//对象的方法
Class cls = Class.forName("java.lang.String");		//Class的静态方法
```

这种通过`Class`实例获取`class`信息的方法称为**反射**（Reflection）。

字段：先获取一个类的Class类，获取类的字段Field，然后可以：

+ Field.setAccessible(true)：修改访问权限。

+ Field.get(object)：获取对象该字段的值。
+ Field.set(Object, value)：设置对象的值。

**使用反射调用方法时，仍然遵循多态原则**：即总是调用实际类型的覆写方法（如果存在）。

```java
Class stdClass = Student.class;
Field f = stdClass.getField("score");		//获取对象的score字段。.getName() .getType() .getModifiers()
f.setAccessible(true);						//修改字段的访问权限
Object value = f.get(stu1);					//获取stu1的score字段的值

//其他
Method m=stdClass.getMethod("getName"); 	//获取方法,getMethod(参数)
String r = (String) m.invoke(stu1);			//调用方法，静态函数，则object为null
Person.class.newInstance();					//通过反射创建新的实例。只能调用该类的public无参数构造方法。
Constructor cons1 = Integer.class.getConstructor(int.class);	//使用getConstructor不受限制
Integer n1 = (Integer) cons1.newInstance(123);					//使用构造器创建新对象
```

### 动态代理

静态代理：

```java
public interface Hello {									//接口
    void morning(String name);
}
public class HelloWorld implements Hello {					//实现接口
    public void morning(String name) {
        System.out.println("Good morning, " + name);
    }
}
Hello hello = new HelloWorld();								//创建实例，
hello.morning("Bob");
```

动态代理：仍然先定义了接口`Hello`，但是我们并不去编写实现类，而是直接通过JDK提供的一个`Proxy.newProxyInstance()`创建了一个`Hello`接口对象。

1. 定义一个`InvocationHandler`实例，它**负责实现接口的方法调用**；
2. 通过`Proxy.newProxyInstance()`创建`interface`实例，它需要3个参数：
   1. 使用的`ClassLoader`，通常就是接口类的`ClassLoader`；
   2. 需要实现的接口数组，至少需要传入一个接口进去；
   3. 用来处理接口方法调用的`InvocationHandler`实例。
3. 将返回的`Object`强制转型为接口。

**动态代理实际上是JVM在运行期动态创建class字节码并加载的过程**，

```java
public class Main {
    public static void main(String[] args) {
        InvocationHandler handler = new InvocationHandler() {
            @Override
            public Object invoke(Object proxy, Method method, Object[] args) throws Throwable {
                System.out.println(method);
                if (method.getName().equals("morning")) {
                    System.out.println("Good morning, " + args[0]);
                }
                return null;
            }
        };
        
        Hello hello = (Hello) Proxy.newProxyInstance(
            Hello.class.getClassLoader(), 		// 传入ClassLoader
            new Class[] { Hello.class }, 		// 传入要实现的接口
            handler); 							// 传入处理调用方法的InvocationHandler
        
        hello.morning("Bob");
    }
}

interface Hello {
    void morning(String name);
}
```

### 注解

第一类是由编译器使用的注解（这类注解不会被编译进入`.class`文件，它们在编译后就被编译器扔掉了），例如：

- `@Override`：让编译器检查该方法是否正确地实现了覆写；
- `@SuppressWarnings`：告诉编译器忽略此处代码产生的警告。

第二类是由工具处理`.class`文件使用的注解，比如有些工具会在加载class的时候，对class做动态修改，实现一些特殊的功能。这类注解会被编译进入`.class`文件，但加载结束后并不会存在于内存中。这类注解只被一些底层库使用，一般我们不必自己处理。

第三类是在程序运行期能够读取的注解，它们在加载后一直存在于JVM中，这也是最常用的注解。

```java
public @interface Report {					//定义注解
    int type() default 0;
    String level() default "info";
    String value() default "";
}
```

元注解：可以修饰其他注解的注解，

+ `@Target`可以定义`Annotation`能够被应用于源码的哪些位置。`@Target(ElementType.METHOD)`。

+ `@Retention`定义了`Annotation`的生命周期，`@Retention(RetentionPolicy.RUNTIME)`。

+ `@Inherited`定义子类是否可继承父类定义的`Annotation`。`ElementType.TYPE`时有效。

```java
Person.class.isAnnotationPresent(Report.class);		//判断@Report是否存在于Person类
Report report = Person.class.getAnnotation(Report.class);	//获取Person定义的@Report注解
```





## 异常

在方法定义的时候，使用`throws Xxx`表示该方法可能抛出的异常类型。**调用方在调用的时候，必须强制捕获这些异常**，否则编译器会报错。

```java
void func() throws Exception {		//抛异常函数
    throw new Exception();
};	

void call() throws Exception {		//1.继续抛出异常
    try { 							//2.在函数体里捕捉异常
        func();
    }catch (Exception e){			//会从上到下匹配
    }finally {						//finally语句块保证有无错误都会执行。
    }
}
```



## 多线程

创建线程的方法：

```java
class MyThread extends Thread {				// 继承 Thread t = new MyThread();
    @Override
    public void run() {}
}

class MyRunnable implements Runnable {		//Thread t = new Thread(new MyRunnable());
    @Override
    public void run() {}
}

public class MyCallable implements Callable<Integer> {	//callable,有返回值，返回值通过 FutureTask 进行封装。
    public Integer call() {
        return 123;
    }
}
//FutureTask<Integer> ft = new FutureTask<>(mc);
//Thread thread = new Thread(ft);

t.start();									//启动线程

t.setDaemon(true);							//设置为守护线程
//如果一个线程的 run() 方法执行一个无限循环，并且没有执行 sleep() 等会抛出 InterruptedException 的操作，那么调用线程的 interrupt() 方法就无法使线程提前结束。
t.interrupt();								//中断该线程

Thread.sleep(3000);		//3秒
Thread.yield();			//放弃执行权

// 管理多个线程
ExecutorService executorService = Executors.newCachedThreadPool();
executorService.execute(new MyRunnable());
```



### 锁

悲观锁：

+ 互斥同步最主要的问题就是线程阻塞和唤醒所带来的性能问题，因此这种同步也称为阻塞同步。无论共享数据是否真的会出现竞争，它都要进行加锁。

乐观锁：

+ **CAS**：先进行操作，如果没有其它线程争用共享数据，那操作就成功了，否则采取补偿措施(不断地重试，直到成功为止)。

  靠硬件来完成。硬件支持的原子性操作最典型的是: 比较并交换(Compare-and-Swap，CAS)。CAS 指令需要有 3 个操作数，分别是内存地址 V、旧的预期值 A 和新值 B。当执行操作时，只有当 V 的值等于 A，才将 V 的值更新为 B。

final：最终版本，不可修改。

volatile：**保证修改的值会立即被更新到主存**，当有其他线程需要读取时，它会去内存中读取新值。

synchronized：保证任一时刻只有一个线程执行该代码块，原子性操作。JVM。

```java
public void func() {
    synchronized (this) {						//同步一个代码块,同一个对象，不同对象不起作用
    }
}

public synchronized void func () {				//同步一个方法。同一个对象
}

public void func() {							//同步一个类，整个类
    synchronized (SynchronizedExample.class) {
    }
}

public synchronized static void fun() {			//同步一个静态方法，整个类
}
```

+ ReentrantLock：java.util.concurrent(J.U.C)包中的锁。

```java
public class LockExample {
    private Lock lock = new ReentrantLock();
    public void func() {
        lock.lock();
        try {
            //...
        } finally {
            lock.unlock(); // 确保释放锁，从而避免发生死锁。
        }
    }
}
```

### 协作

```java
//在线程中调用另一个线程的 join() 方法，会将当前线程挂起，而不是忙等待，直到目标线程结束。
t.join();
//调用 wait() 使得线程等待某个条件满足，线程在等待时会被挂起，当其他线程的运行使得这个条件满足时，其它线程会调用 notify() 或者 notifyAll() 来唤醒挂起的线程。
wait();				notifyAll();
//java.util.concurrent 类库中提供了 Condition 类来实现线程之间的协调，await() signal() signalAll()
private Lock lock = new ReentrantLock();
private Condition condition = lock.newCondition();
condition.signalAll();condition.await();
```



## IO



**异步IO**则是采用“订阅-通知”模式: 即应用程序向操作系统注册IO监听，然后继续做自己的事情。当操作系统发生IO事件，并且准备好数据后，在主动通知应用程序，触发相应的函数:

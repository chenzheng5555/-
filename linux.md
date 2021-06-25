# 基础

## 文件权限

```bash
lrwxrwxrwx.   1 root root    7 May 10  2019 lib -> usr/lib
#文件类型+权限 硬链接数 文件所属用户 所属组 文件大小 修改时间 文件名
# 三个组的权限可用三位的八进制数表示，如示例可表示为777
```

> **r读，w写，x执行**，d目录，l链接文件，->链接，-表示没有该权限，分为**三组**，分别说明文件的 **所属用户，所属组用户，其他用户** 可以对文件的操作权限，示例表示：文件为目录，所属用户权限：rwx，所属组：r-x（不可写），其他用户：r-x（不可写）







# vim

vim 键盘图[(来源菜鸟教程)](https://www.runoob.com/linux/linux-vim.html)：
![img](img/vi-vim-cheat-sheet-sch.gif)

>分为三种模式，分别是 `视图模式`、`(底线)命令模式` 和 `输入模式` 
>
>+ 启动 vi/vim，便进入了<font color=red>视图模式</font>
>+ 按 <kbd>i</kbd>、<kbd>a</kbd>、<kbd>o</kbd>切换到<font color=red>输入模式</font>；按 <kbd>ESC</kbd> 回到视图模式 
>+ 在视图描述下按 <kbd>:</kbd> 切换到<font color=red>命令模式</font>，可以输入更多命令

## 视图模式

> ---
>
> + 移动光标：<kbd>h</kbd>左，<kbd>j</kbd>下，<kbd>k</kbd>上，<kbd>l</kbd>右；如图所示
> + 剪切：<kbd>x</kbd>字符，<kbd>d</kbd>行
> + 复制：<kbd>y</kbd>行
> + 粘贴：<kbd>p</kbd>后，<kbd>P</kbd>前
> + 撤销：<kbd>u</kbd>
> + 格式化：<kbd>=</kbd>，缩进：<kbd><</kbd>，<kbd>></kbd>。
> + 光标停留在函数上，按<kbd>Shift</kbd>+<kbd>k</kbd>查看函数man手册

## 命令模式 

> ---
>
> + ` q ` 退出，` w ` 保存
> + `:set number`设置行号
> + `/`向后查找，`?`向前查找，查找停留在光标上单词<kbd>shift</kbd>+<kbd>*</kbd>，<kbd>n</kbd>下一个、<kbd>N</kbd>上一个
> + 分屏：`vs`竖屏，`sp`横屏，切换<kbd>Ctrl</kbd>+<kbd>w</kbd>，再按`hjkl`进行切换。

# 命令

命令帮助手册：man

输出重定向 `>`、追加`>>`，管道`|`，前者的输出作为后者的输入

## 用户管理

|        命令        |                        功能                        |
| :----------------: | :------------------------------------------------: |
|   whoami、who、w   |              当前用户、用户登录信息等              |
|      su、exit      |    swith user；用于变更为其他使用者的身份、退出    |
|        sudo        |          以root用户执行操作，然后退出root          |
| groupadd、groupdel |                     添加删除组                     |
|      usermod       |                 modify修改用户账户                 |
|  useradd、userdel  |                    添加删除用户                    |
|       passwd       |                      修改密码                      |
|       chmod        |                    修改文件权限                    |
|       chown        | change owner；用于设置**文件所有者**和文件关联组。 |
|       chgrp        |                  修改文件所属的组                  |

## 软件管理

|          命令          |                     功能                     |
| :--------------------: | :------------------------------------------: |
|          rpm           |     redhat package manager；用于管理套件     |
|       systemctl        |       查看、关闭、开启、设置自启动服务       |
|        ps、top         | process status；命令用于显示当前进程的状态， |
|          kill          |                   终止进程                   |
|        jobs、fg        |                   后台程序                   |
| reboot、shutdown、init |           系统重启、关机、界面切换           |

## 文件管理

|     命令      |                     功能                     |
| :-----------: | :------------------------------------------: |
|      pwd      | print work directory；命令用于显示工作目录。 |
| cp、mv、mkdir | 复制文件、移动文件（修改文件名）、创建文件夹 |
|     file      |                 显示文件类型                 |
|      tar      |        打包（压缩-z）多个文件，解包-x        |
|     gzip      |                压缩和解压缩-d                |
|      wc       |             统计文件字符数等信息             |



## 网络

|   命令    |                 功能                  |
| :-------: | :-----------------------------------: |
| ifconfig  | 网络信息configure a network interface |
| firewalld |                防火墙                 |
|   wget    |          从指定url下载东西，          |
|           |                                       |
|           |                                       |

### ftp

```shell
# 文件传输协议，默认协议21/tcp，配置文件：/etc/vsftpd/vsftpd.conf，
`安装服务后，如果连接不上，检查防火墙firewall`
ftp host		`连接主机
help			`查看帮助
!dir[ldir]		`本地文件夹内容
lcd				`本地进入
```





## 字符串

| 命令 |                  功能                  |
| :--: | :------------------------------------: |
| echo |           用于字符串的输出。           |
| grep | 正则表达式；查找文件里符合条件的字符串 |
|      |                                        |

# shell

```shell
`声明解析器，#！ 约定标记,
#! /bin/bash
# ./test.sh如果无法执行，添加执行权限 chmod +x ./test.h，linux默认会在PATH中查找可执行程序，需要添加当前路径 ./

`变量，变量名=
var="test"
`提取变量、局部变量、环境变量、shell变量
echo $var 		# 可选${var}， echo打印输出
readonly var 	# 修改变量属性
`字符串 单引号（里面的变量无效、里面不能用单引号） 或 双引号
echo ${#str}	# 获取长度
`数组、
arr=(val1...)
x=arr[n]		# 取数组数组
@ 当前所有

#循环控制
for f in *
do 
done
```



# 《linux C编程一战式学习》

### 1. gdb调试

在编译时要加上`-g`选项，生成的目标文件才能用gdb进行调试；其作用为，**在目标文件中加入源代码的信息**。在调试时目标文件必须**保证gdb也能找到源文件**。

- [x] 直接回车，相当于重复上一个命令。
- [x] 观察点是当程序**访问某一存储单元**时中断，

```shell
gcc -g main.c -o main
gdb main #调试
# 命令包括
help			# 帮助命令，如help list
# -----信息-----
list(l)			# 显示源文件对应的函数或行(10)，1个参数，开始行，两个参数【s,e】起始和终止，继续list输出后面的代码
backtrace(bt)	# 查看函数调用的栈帧，
info(i)			# 查看变量值，如locals,breakpoints,watchpoints,registers
disable、delete # 禁用、删除断点
frame(f)		# 跳到其他栈帧，查看信息
print(p)		# 打印变量的值
set 			# 设置某个变量的值，set var sum=0也可以使用print a=b 间接设置
display			# 显示某个值，使得每次停下来都显示该值。undisplay取消
x/7b input		# x打印命令、/7b 表示+7组，b表示字节；Examine memory: x/FMT ADDRESS.
# -----执行-----
quit(q)			# 退出gdb
start 			# 开始执行（默认在main函数设置了临时断点）
next(n)			# 逐条语句地执行，或者缩写n
step(s)			# 进入函数，逐行执行
finish			# 跳出当前函数
continue(c)		# 连续执行
run(r)			# 重新执行
si				# 逐条指令地执行
# -----断点-----breakpoint
break(b)		# 跳出循环，并执行到断点，如执行到9行，break 9 [if sum!=0]
# -----观察点-----Watchpoint
watch			# 检测内存 检测input的第5个元素，watch input[5]
# -----观察点-----汇编 
disassemble		  # 反汇编当前函数或者指定的函数,生成汇编代码
```

### 2. 汇编

+ 汇编代码

```assembly
.section .data	#.xxx 助记符， section表示为一个段 .data表示data段，可读可写
.section .text	#代码段
.globl _start	#.globl告诉汇编器 _start链接时会用到，要在目标文件的符号表中给它特殊标记
_start: 		#_start代表一个符号，即一个地址，程序启动位置

movl $1, %eax 	# 指令
...
```

+ 汇编生成可执行文件

```shell
as hello.s -o hello.o   #汇编器 翻译为机器指令
ld hello.o -o hello		#连接器 将多个目标链接为一个可执行文件，将目标文件中的相对地址符 改为加载时的内存地址
```

+ linux可执行文件采用**ELF**格式，有三种不同的类型，目标文件、可执行文件、共享库。
  + ELF header：体系架构、操作系统等信息，后两部分在文件中的位置。
  + section header table：所有section部分的信息。汇编和链接时。
  + program header table：所有segment部分的信息，加载时。segment是指在程序**运行时加载到内存的具有相同属性的区**
    **域**，由一个或多个Section组成。

```shell
readelf file.o		# 读取elf文件信息
hexdump -C file.xx 	# 以二进制查看文件
objdump	-d file.o	# 反汇编
```

```shell
.data			`数据段，以后原封不动的加载到内存
.bss			`全局变量
.shstrtab		`保存着各Section的名字， 
.strtab			`保存着程序中用到的符号的名字。
.rel.text 		`告诉链接器 指令中的哪些地方需要重定位  
.symtab			`是符号表，每个符号所对应的编号
.text			`代码段
```

在目标文件中，符号地址都是**相对于该符号所在Section的相对地址**  。

因为MMU的权限保护机制是以页为单位的，  不同权限的段需要加载到不同的页

### 3. 程序执行过程

```shell
objdump -dS a.out  		`把C代码和汇编代码穿插起来显示 编译时需要加-g
```

#### 函数启动

+ 汇编程序：一个汇编程序的 汇编过程

```shell
as hello.s -o hello.o	`将汇编文件 汇编成 目标文件，
ld hello.o -o hello		`使用链接器链接成 可执行文件，即使是单个目标文件也需要链接
ld --verboase 	#查看链接器的信息
```

每个**汇编程序都要提供一个_start符号并且用.globl声明**，作为整个程序的入口地址，

+ c语言：

```shell
gcc -E 		`预处理
gcc -S 		`编译不汇编assembly，汇编代码，
gcc -c 		`汇编，目标文件
gcc 		`全过程、
gcc -o 		`指定输出文件名称
gcc -v 		`查看详细的编译过程
# gcc main.o -o main 的链接过程相当于
ld /usr/lib/crt1.o /usr/lib/crti.o main.o -o main -lc -dynamiclinker /lib/ld-linux.so.2
```

1. **gcc编译产生的目标文件不会有_start**，整个程序的入口点是**crt1.o**中提供的**_start**。它首先做一些初始化工作（Startup Routine），然后**调用C代码中提供的main函数**。用gcc链接目标文件时，gcc其实是调用`ld`将目标文件crt1.o和我们的hello.o链接在一起。然后由启动例程调用main，相当于`exit(main(argc, argv))`。
2. 还用到其他目标文件，如`crti.o`，**其包含crt1.o使用的main符号**，未链接之前，main的地址是未知的，在我们提供main函数后（地址），链接器可以替换指令中那些未知地址。



#### 函数调用

操作系统为进程分配一块**栈空间来存储函数栈帧**，**esp寄存器总是指向栈顶，ebp指向栈底**；在x86平台上这个栈是从高地址向低地址增长的。调用过程：

> 1. 将栈顶**增长**满足参数的字节（减某个偏移量），然后将传入的参数**从右向左依次压入栈**（通过栈顶指针加上某个偏移获取变量）。
> 2. 压入调用完函数后的下一条指令地址，esp的减4（压入的地址）。
> 3. 修改程序计数器eip（被调函数的地址），开始执行被调用函数的指令。
> 4. 在被调用函数的汇编代码中，前一段是：压入ebp的值（esp减4），然后将esp的值给ebp，即当前函数栈的栈底，在当前函数中时，不会变化，所以**函数的参数（减）和局部变量（加）都是通过ebp的值加上一个偏移量来访问的**。
> 5. 函数返回时：把ebp值给esp（回到栈底），将保存的 调用函数的ebp值给ebp寄存器（调用函数的ebp），将保存的下一条指令地址，给eip。

#### 变量

结构体的成员在储存时，会有对齐操作。

```shell
`.rodata段和.text段通常合并到一个Segment中 ，它们都为只读数据
`.data和.bss在加载时合并到一个Segment中，  可读可写
`volatile限制优化。
`extern 声明外部变量。
`static 声明本地
`变量使用必须声明，为了不在每个使用文件中都声明一次，可使用头文件。
```

### 4. C内联汇编

平台独有的指令不会出现在c里面，所以gcc提供了一种扩展语法，可以在C代码中使用内联汇编（Inline Assembly）

```c
__asm__("movl $1, %eax\n\t" 	//指令间通过\n\t隔开
		"movl $4, %ebx\n\t"
		"int $0x80");
//与C的变量建立关联
/*__asm__(assembler template
        : output operands 				// optional
        : input operands				// optional 
        : list of clobbered registers   // optional 
        );
 */
#include <stdio.h>
int main()
{
    int a = 10, b;
    __asm__("movl %1, %%eax\n\t"	//%1作为输入，对应a
            "movl %%eax, %0\n\t"	//%0作为输出，对应b
            :"=r"(b) 				// output 将寄存器r里的值给b
            :"r"(a) 				// input 将为a分配一个寄存器
            :"%eax" 				// clobbered register 执行时会修改eax，在此期间不要用eax保存其它值
    	);
    printf("Result: %d, %d\n", a, b);
    return 0;
}
```

### 5. 库

库文件名都是以lib开头的，静态库以.a作为后缀，  

```shell
# 静态库
ar rs libxxxx.a xx1.o xx2.o ...  # 将目标文件打包成静态库 s表示为静态库创建索引，便于链接时使用
# 使用
gcc main.c -L. -lxxxx -Ixxxx -o main 	#-L 查找路径 -l链接到的库 -I头文件查找路径
`链接器可以从静态库中只取出需要的部分来做链接。
# 动态库 ，
gcc -c -fPIC xx1.c xx2.c ....  #PIC表示生成位置无关代码的目标文件
`绝对地址保存在一个地址表中，而指令通过地址表做间接寻址，因此避免了将绝对地址写死在指令中，这也是一种避免硬编码的策略。  
#生成动态库
gcc -shared -o libxxx.so xx1.o xx2.o ...
ldd main  		`ldd命令查看可执行文件依赖于哪些共享库
`运行时，动态库查找路径顺序：LD_LIBRARY_PATH、/etc/ld.so.cache、/usr/lib、/lib
```

### 6. IO

每个进程在Linux内核中都有一个`task_struct`结构体来维护进程相关的信息，称为进程控制块  ， `task_struct`中有一个指针指向`files_struct`结构体，称为**文件描述符表**，其中每个表项包含一个指向已打开的文件的指针，  

由open返回的文件描述符一定是**该进程尚未使用的最小描述符**。  

有缓冲的IO：C标准I/O库函数 ，printf  、scanf，读写位置记录在用户空间IO缓冲区中的位置。

无缓冲的IO：open、 read、 write、 close  。读写位置记录在内核，

```shell
`fgetc() 可能一次读取了1024个字节到IO缓冲区，所以内核中读写位置为1024，FILE中的为1
#从终端设备读，通常以行为单位，读到换行符就返回了。
#读常规文件是不会阻塞的，不管读多少字节， read一定会在有限的时间内返回。从终端设备或网络读则不一定，如果从终端输入的数据没有换行符，调用read读终端设备就会阻塞，
# 如果在open一个设备时指定了O_NONBLOCK标志， read/write就不会阻塞。
#ioctl用于向设备发控制和配置命令。
#mmap可以把磁盘文件的一部分直接映射到内存，这样文件中的位置直接就有对应的内存地址，对文件的读写可以直接用指针来做而不需要read/write函数。
```



## MakeFile

管理和组织代码工程的编译和链接。[参考文章](https://seisman.github.io/how-to-write-makefile/overview.html)

规则包含两个部分，一个是**依赖关系**，一个是**生成目标的方法**。将文件中的第一个目标文件（target）作为最终的目标文件。

make执行时，会检查**目标文件** 与 **依赖** 最后修改时间的关系，来确定目标文件是否需要重新编译

```makefile
#targets : prerequisites ; command
#    command
#    ...
include file1.make

foo.o: foo.c defs.h       # foo模块
    cc -c -g foo.c

# 文件过多，可以使用变量代替。
obj = a.o b.o c.o d.o
out.o: $(obj)
	gcc -o out.o $(obj)
	
# 匹配
%.o:%.c
	gcc -c $< -o $@
# makefile中的自动变量，
# $< 第一个依赖 $^ 所有依赖
# $@ 目标

# 函数
src=$(wildcard ./*.c) #查找当前目录下的所有.c文件
obj=$(patsubst ./%.c, ./%.o, $(src)) #替换 src变量中.c文件名 为.o文件名

.PHONY:clean #伪标签
clean: 
    rm edit $(objects)
VPATH = src:../headers #冒号分割
```

**自动推导**，可以自动把.c文件加入到对应的.o文件的依赖中。且编译命令也可省略。

make命令会在当前目录下按顺序找寻文件名为“GNUmakefile”、“makefile”、“Makefile”的文件。指定需要加`-f`

**引用其它的Makefile**：`include <filename>`

文件搜索：默认会在当前目录下搜索文件，可以用使用VPATH进行扩展。
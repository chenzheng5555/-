# 基础

静态类型的编译语言。

## 1. vscode配置go环境

智能提示由`gopls`提供。如果安装失败可使用代理。

```shell
go env -w GO111MODULE=on
go env -w GOPROXY=https://goproxy.io,direct 
```

Go 是由包组成的。 main 包告诉 Go 编译器该程序可以被编译成可执行文件，是应用程序的入口。

Go 中的工作空间由环境变量「GOPATH」定义。

```shell
go build xx.go		#编译
go run xx.go		#直接运行
go install 			#编译，再将.exe添加到GOPATH/bin
```



## 2. 快速入门

**控制命令可见性**：首字母大小写表示可见性，大写为public，小写为private

**make和new**：new申请内存，返回的指针，make返回的是数据本身，只能用于`slice,map,chan`

对于需要make的数据，如果只声明，则为nil，其他数据默认为空

**匿名**，临时定义，直接作为变量使用

### 变量

判断类型：`_,ok:=x.(T)`

```go
var a int			//变量定义，默认0
var a = 1			//初始化，
msg := "hello"		//定义+初始化
var b,c int = 2,3	//定义多变量
//数据类型int, int8, int16, int32, int64,string,bool,float32等

//数组
var a [2][3]int		//2*3的二维数组

//类型转换
a := int(b)

//指针
var ap *int		//整形指针
var ap new(int)
ap=&a			//取地址
fmt.Println(*ap)//取值
```

### 切片

分为三部分：长度、容量、低层数组。

切片指向一个低层数组，同一数组的不同切分，相当于对该数组一个**引用**。

容量为**当前第一个元素**到**底层数组的最后一个元素**的距离。

使用`...`可以拆分切片`append(a,b...)`

```go
var a []int 	//a==nil 只声明了变量
b := []int{}	//b!=nil
c := [...]int{1,2,3}	//数组
//切片，可扩展的数组，切片是数组的抽象，切片包含三个组件：容量，长度和指向底层数组的指针，
num := make([]int,5,10)		//切片长度为5，容量为10.
append(num,1,2,3)	//末尾添加元素
num[2:]				//子切片
```

### 字典

```go
//字典,必须make
m := make(map[string]int)	//key=string，value=int的字典
m["one"] = 1	//添加键值对
```

### 控制流程

```go
//流程控制
if num<0{	//条件和{在同一行
}else if num<10{
}
switch i{
    case 1:fmt.Println("one")	//不需要break
    case 2:...
    default:...
}
for i:=0;i<10;i++{    //循环
}
for{	//无限循环
}
```

### 函数

参数默认为值，如果需要修改，则用指针参数

```go
//函数
func add(a int,b int) (int,string) { //函数,多返回值
    x:=a+b
    return x, "ok"
}
func add(a int,b int) (c int) { //返回值预先定义
    x = a+b
    return 
}
//可变参数
func add(b ...int) int {
    //b是一个切片
}
//函数作为参数
func add(g func() int) func(){
    g()
    f:=func(){
        //匿名函数
    }
    return f
}
//闭包,函数使用函数外的函数的变量
func call(f func(int,int),x,y int) func(){
    tmp:=func(){
        f(x,y)
    }
    return tmp
}
tmp := call(gg,5,10)	//提前传参 传给的是gg函数
tmp()					//无参函数
```



### 结构体

**可以使用has a实现继承**。

```go
type myint int	//自定义类型
type int2 = int //类型别名
//结构体
type person struct{
    name string 
}
p := person{name:"tom"} //创建实例
p.name					//访问

//方法，一个特殊类型可以使用的函数。 指针接收者，如果是值，则如果内部有修改，该变量不会变化
func (p *person) describe(){ //func 接送者 方法名(参数) {}
    fmt.Printf("hello %v",p.name)
}
p.describle()	//调用方法
```

go结构体和json的结合，

```go
//序列化
bytes,err:=json.Marshal(person) //序列化
json.Unmarshal([]byte(str),&person)
```



### 接口

多态的实现。分为类型和值两部分。

```go
//接口,是一系列方法的集合 
type animal interface{	//定义接口
    description() string
}
//cat的实现
type cat struct{ 		
    name string
}
func (c cat) description() string{ //具体实现
    fmt.Printf("name:%v",c.name)
}
//dot实现
....
func de(x animal){
    x.description()
}
var a cat
var d dog
de(a)
de(d)
```

空接口：`type any interface{}`

### 包

```go
go get <url> 	//获取包
go install 		//安装包
godoc person Description //生成文档
godoc -http=":8080"		 //查看文档
init()  		//函数,在全局函数后自动执行，无法调用，
```

### 异常

```go
//由返回值判断。
panic 	//发生异常
defer 	//在函数结束时执行,如关闭文件，延迟操作
recover //尝试恢复
func deal(){
    defer func(){
        err:=recover()
        //处理异常，尝试恢复后面的程序
    }
    panic("wrong!!!")//程序终止
}
```

### 并发

```go
//并发go routine
go func_name() //Go 不是将一个线程的变量与另一个线程共享

//通道
c := make(chan string) //string类型的通道
c <- "hello"	//向通道里发送数据
msg := <- c		//向通道里读取数据
chan<-			//单通道，只能发送

select{			//多通道
    case s1:=<-ch1:...
    case s2:=<-ch2:...
}

ch:=make(chan string,2)	//缓冲通道 2 在缓冲区满之前接受方不会收到任何消息。
```

### 格式化输出

格式化输出fmt.Printf

|                         |                                            |
| :---------------------: | :----------------------------------------: |
|         %v，%+v         |         输出值，包括结构体的字段名         |
|           %T            |                 变量的类型                 |
| %5d，%b，%x，%-6.2f，%e | 整数、二进制、十六进制、浮点数、科学记数法 |
|       %t，%c，%6s       |            bool值、字符、字符串            |

Sprintf()：格式化输出到字符串。










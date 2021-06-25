## 入门

一个 Java 程序可以认为是**一系列对象的集合**，而这些对象通过调用彼此的方法来协同工作。

一个文件是一个编译单元，且只有一个public类。

```java
// MainTest.java 
public class MainTest {			//源文件名必须和类名相同。当保存文件的时候，使用类名作为文件名保存
    public static void main(String[] args){ 	//主方法入口,所有的 Java 程序由该方法开始执行。
        System.out.println("hello");
    }
}
```

```shell
javac MainTest.java		# 编译生成字节码
java MainTest			# jvm执行，
```

![ZSSDMld](img/ZSSDMld.png)



### 包

JVM加载某个类时，需要找到对应的.class文件，classpath就是用来储存这些查找目录的变量。JVM会依次在这些目录中进行查找，直到找到。

对于java核心包，不需要将其加入到classpath中，jvm可以自己找到。

可以在启动JVM时设置`classpath`。`java -classpath .;C:\work\project1\bin`。缩写cp

jar包，把`package`组织的目录层级，以及各个目录下的所有文件（包括`.class`文件和其他文件）都打成一个jar文件。也就是一个zip格式的压缩文件。

jar包还可以包含一个特殊的`/META-INF/MANIFEST.MF`文件，`MANIFEST.MF`是纯文本，可以指定`Main-Class`和其它信息。JVM会自动读取这个`MANIFEST.MF`文件，如果存在`Main-Class`，我们就不必在命令行指定启动的类名，

### 模块

jar只是用于存放class的容器，它并不关心class之间的依赖。为了解决依赖引入了模块。以`.jmod`扩展名标识。

模块之间的依赖关系已经被写入到模块内的`module-info.class`。所有的模块都直接或间接地依赖`java.base`模块，

```shell
jar --create --file hello.jar --main-class com.itranswarp.sample.Main -C bin . #打包
jmod create --class-path hello.jar hello.jmod 	#模块
jlink --module-path hello.jmod --add-modules java.base,java.xml,hello.world --output jre/ #打包jre
jre/bin/java --module hello.world	# 运行jre
```

访问权限，只有模块声明了导出的包，外部代码才被允许访问。

### 类

访问权限是针对类的，所以同一类的对象可以访问彼此的私有变量。



## 基本

字符串

+ Java字符串的一个重要特点就是字符串*不可变*。这种不可变性是通过内部的`private final char[]`字段，较新的JDK版本的`String`则以`byte[]`存储：

+ 用`+`拼接字符串string。会不断创建新字符串，效率低。

+ `StringBuilder`，它是一个可变对象，可以预分配缓冲区，`StringBuffer`早期的线程安全版本，
+ 比值使用equals()，

基本类型

+ 引用类型可以赋值为`null`，表示空，但基本类型不能赋值为`null`，为了方便，将基本类型包装为类。彼此之间可以相互转换，自动装箱和自动拆箱只发生在编译阶段，目的是为了少写代码。
+  Integer.valueOf(100);，会返回同一个`Integer`实例。

JavaBean

+ 读写方法符合这种命名规范：getXxx,setXxx的类，称为JavaBean。主要用来传递数据，

+ 枚举JavaBean属性，Java核心库提供的`Introspector`：

枚举类

+ `static final`来定义常量。这样做的缺点时，编译器无法检查每个值的合理性。
+ enum，编译器能自动检查某个值在枚举的集合内，可以直接用`==`比较。

## 继承

所有类继承自**object**。

如果父类和子类有相同的成员变量，则按就近原则，在子类函数中，获取到的是子类的变量，父类同理。

向上造型：子类赋值给父类。不改造，只当作父类来看。

类型转换：会改造。



## 多态

动态绑定：根据变量的动态类型决定。

子类会覆盖父类里相同的函数，





# 注解

@注解名(参数)

**元注解**负责注解其他注解，Retention什么时候有效 Document，javadoc包

```java
@Target(value=ElementType.METHOD) //元注解,作用到方法上
@interface MyAnnotation{ //自动继承java.lang.annotation.Annotation接口
    name default ""
}
```

## 反射

### 反射机制

允许程序在执行期间通过reflection api取得任何类的内部信息。并直接操作。

对于每个类，JRE都会为其保留一个Class类型的对象。

```shell
`过程
` JVM在加载类时，
```



```java
Class c=Class.forName("java.long.Class");
Class c=Person.class;
```


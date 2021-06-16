# QT

[中文文档](http://qt5.digitser.net/5.15/zh-CN/index.html)、[教程](https://qtguide.ustclug.org/)、

## 信号和槽函数

信号和槽函数的关联connect。

+ Qt 的关键字 slots 就是槽函数声明段落的标志，
+ `m_conn=connect(ui->pushButton, SIGNAL(clicked()), this, SLOT(FoodIsComing()));`
  + 第一个参数是发信号的源头对象指针，
  + 第二个参数用 SIGNAL 宏包裹的信号，
  + 第三个参数是接收信号的接收对象指针，
  + 第四个参数是使用SLOT 宏封装起来的 接收对象里的槽函数，

connect 函数必须放在 ui->setupUi 之后，否则控件指针是未定义的野指针，

+ 自动关联`void on_<object name>_<signal name>(<signal parameters>);`。要求是槽函数根据源头的对象名（指针）和其信号名称来命名，右键点击对象，选择信号，即可自动生成槽函数。然后是由 uic 和 moc 等工具自动完成的。

解除关联，`disconnect(m_conn);`

```c++
signals:    //添加自定义的信号，默认public
    void SendMsg(QString str);  //信号只需要声明，不要给信号写实体代码
public slots:   //接收按钮信号的槽函数
    void ButtonClicked();
```

emit 发送信号。关联信号的地方，一般在接收者，或两对象都可见的地方。

## 属性系统

```c++
public:
    Q_PROPERTY(int count MEMBER m_count READ count WRITE setCount NOTIFY countChanged)
    int count();//count读函数
signals://修改触发信号
	void countChanged(int nNewCount);
public slots://写函数通常可以作为槽函数，方便与其他信号关联，自动调整数值
	void setCount(int nNewCount);
private:
    int m_count;
```





### 窗口

![Geometry diagram](http://qt5.digitser.net/5.15/images/geometry.png)

[QObject](http://qt5.digitser.net/5.15/zh-CN/qobject.html) 类是所有 Qt 对象的基类。

+ timerEvent，处理计时器事件。

[QWidget ](http://qt5.digitser.net/5.15/zh-CN/qwidget.html)：所有用户界面对象的基类

+ setFocusPolicy，设置widget获取键盘焦点的方式。Qt::StrongFocus，点击和tab。
+ setFixedSize，设置控件宽、高。
+ move，移动控件的位置。
+ setWindowTitle，设置窗口标题
+ show，展示 Widget 及其子级 Widget。
+ keyPressEvent，事件处理程序，用以接收 Widget 按键事件。
+ paintEvent ，以接收传入描绘事件，可由：1）repaint () 或 update () 引起，2）Widget 被遮盖且现被发现，3）许多其它原因。

[QMainWindow](http://qt5.digitser.net/5.15/zh-CN/qmainwindow.html)：主应用程序窗口。

+ statusBar，返回用于主窗口的状态栏。此函数创建并返回空状态栏，若状态栏不存在。

[QStatusBar](http://qt5.digitser.net/5.15/zh-CN/qstatusbar.html)：提供适于呈现状态信息的水平条。

+ showMessage：状态栏显示信息。

[QBoxLayout](http://qt5.digitser.net/5.15/zh-CN/qboxlayout.html)：水平或垂直排列子级 Widget。

+ addWidget，添加控件。

[QHBoxLayout](http://qt5.digitser.net/5.15/zh-CN/qhboxlayout.html#details)：构造水平框布局对象。继承自QBoxLayout。

[QFrame](http://qt5.digitser.net/5.15/zh-CN/qframe.html)：可以拥有框架的 Widget 基类。

[QBasicTimer](http://qt5.digitser.net/5.15/zh-CN/qbasictimer.html)：fast, lightweight, and low-level的**重复定时器**，

+ **start**(int msec , QObject* object)，每隔msec毫秒，会向QObject发送 timer event 。

[QDesktopWidget](http://qt5.digitser.net/5.15/zh-CN/qdesktopwidget.html)：访问系统的屏幕信息

+ geometry，此特性保持 Widget 相对于其父级的几何体，

[QRect](http://qt5.digitser.net/5.15/zh-CN/qrect.html)：定义平面矩形

### 绘画

[QPainter](http://qt5.digitser.net/5.15/zh-CN/qpainter.html)：在小部件和其它绘画设备上履行低级描绘

+ fillRect，重新画某个块
+ setPen，返回描绘器的当前钢笔
+ drawLine，画线

### 事件处理

[QTimerEvent](http://qt5.digitser.net/5.15/zh-CN/qtimerevent.html)：包含计时器事件的描述参数。

+ timerId，返回唯一计时器标识符，

[QKeyEvent](http://qt5.digitser.net/5.15/zh-CN/qkeyevent.html)：描述按键事件

+ key，被按下或释放的健值

[QApplication](http://qt5.digitser.net/5.15/zh-CN/qapplication.html)：管理 GUI 应用程序的控制流和主要设置。

+ exec，进入主事件循环并等待，直到 exit被调用。



+ QQmlEngine：提供实例化 QML 组件的环境。
+ QQmlApplicationEngine：提供从单个 QML 文件加载应用程序的便捷方式。
+ QUrl：提供操控 URL 的方便接口。


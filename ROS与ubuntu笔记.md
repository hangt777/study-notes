# ubuntu与ROS

## 终端常用的命令：

**1.cd:索引文件夹**

**2.catkin\_make是编译**

3.rospack:查找某个包的地址（rospack find name、rospack list）

4.roscd:定位到某个包的路径下面（roscd name）

5.rosls:例举包下面的文件信息（rosls name）

6.rosed:编辑pkg中的文件（rosed pkg\_name file\_name）

**7.catkin\_create\_pkg：创建一个pkg（catkin\_create\_pkg <pkg\_name><依赖项列表>）**

**mkdir filename：创建一个文件夹子目录**

8.rosdep:安装某个pkg所需的依赖项。(rosdep install [pkg\_name])

9.rosnode list 相当于列出目前包中的节点

10.rostopic list 列出所有的topic

11.rostopic info /topic\_name显示某个topic的属性信息

12.rostopic echo /topic\_name显示某个topic的内容

13.rostopic pub /topic\_name…… 向某个topic发布内容

**rosservice类比rostopic、rosmsg类比rossrv**

## 快捷指令：

1.ctrl+alt+t,快速打开terminator

2.shift+ctrl+o,上下分屏

3.shift+ctrl+e,左右分屏

4.shift+ctrl+w,关闭当前窗口

5.alt+方向键（上下左右），选择窗口

## 节点和包的概念

1.节点我们可以理解为APP，一个节点有一个功能，类似于APP。

2.节点是不能脱离包存在的。一般一个包包含很多节点

## ROS通信方式（核心之处）

有四种：topic、service、parameter service 、actionlib

### 一、topic(应用：激光雷达、里程计发布数据)

ROS中的异步通信方式，node通过publish-subscribe通信，topic是一个string。一个话题可以有多个订阅者，多个发布者可以发布在一个话题。**可以理解为发布者会一直发消息，不管有无订阅者或此时是否需要这个信息。**

publish-subscribe（多对多）

**一般文件格式：.msg**

### 二、service（开关传感器、拍照、gazebo里面删除信息之类的）

ROS中的同步通信方式，node通过requset-reply通信可以理解为有人调用才会执行。需要一次来一次！**发出requset后必须有reply请求节点才会继续执行任务。***rosservice不是rosserver*

client-server（多对一）

**一般文件格式：.srv**

### 三、parameter service

roscore时相当于启动了：parameter service、master、rosout

它是存储各种参数的字典（字典就是一种映射关系），可用命令行、launch、node读写

key-value的概念

实际中把一些不常改变的参数放入parameter service，便于读写。

**这个通信多用rosparam，类比rostopic、rosservice**

**.yaml文件存储一般**

#### 常用指令：

rosparam list

rosparam get /…… 获得某个的参数信息

rosparam dump test.yaml 把当前所有参数存入文件

rosparam load test.yaml 加载yaml文件导入我们定义好的参数

### 四、action

类似service，带有状态反馈的通信方式。通常用在长时间（机械臂从a到b点，小车的导航时间）、可抢占的任务中（任务可以被打断，作一半；不做了去做其他的事情）。

**一般文件格式：.action**

action client:goal;action server :result(返回结果一次），feedback（实时的可多次）

---

### 常用工具

***rqt:***

rqt\_graph:显示通信架构。目前有哪些node在运行，消息流向

椭圆代表节点、方框一般为话题

rqt\_plot:绘制曲线，尤其是动态参数（调试机器人要看他的速度……）

rqt\_console:查看日志

***ros\_bag***

ros命令行工具、记录和回放数据流。

比如记录topic，用到record，最后生成文件.bag

rosbag record topicname 记录某个

rosbag record -a 记录所有

rosbag play name.bag 回放

-----
***Client Library***

提供ROS编程的库，例如：建立node、发布消息、调用服务

相当于把底层的东西封装好，方便我们去写代码。一个接口一样。

roscpp、rospy、roslisp，主要是前面两个用的多针对C++、python

roscpp理解为C++编程封装好的一些函数，rospy同理


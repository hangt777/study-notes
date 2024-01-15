

<<<<<<< Updated upstream



54f

# 知识点1：查找ros发行版本
```
echo $ROS_DISTRO
```
```
melodic
```
或用
```
printenv | grep ROS
```
查看更详细的信息
[image-20231210171930505.png](https://postimg.cc/5jFZ85jh)








# 知识点2：操作



## 基本规律

### 1、node、topic、server

话题：发送指令动作（半双工/单向）

服务：生成，删除小海龟（双工/双向）

参数：背景颜色

```
rosnode list
rosetopic pub [话题eg：cmd_vel] （tab） [信息类型，tab可自动补全] （tab) [调参]
rosserver call [服务eg：/call  /spawn] （tab看是否有参数）
rosparam set
```



### 2、bag文件

*下面所有的命令中，前面都有一个`time`，这样做可以同时输出执行每个命令花费的时间，而且有时这些命令需要很长时间，因此使用`time`命令了解给定命令所需的时间是有必要的。如果您不想使用它，可以放心删除下面任何命令中的`time`。*

#### 1、记录（创建）

##### 1、全部

```
rosbag record -a
```

##### 2、部分

```
rosbag record -O subset /turtle1/cmd_vel /turtle1/pose
```

上述命令中的-O参数告诉rosbag record将数据记录到名为subset.bag的文件中，而后面的topic参数告诉rosbag record只能订阅这两个指定的话题。然后通过键盘控制乌龟随意移动几秒钟，最后按Ctrl+C退出rosbag record命令。

#### 2、查找

```
rosbag info <your bagfile>
```



#### 3、使用运行

1、-r 2   （速率）

```
time rosbag play -r 2 <your bagfile> 
```

2、（使用`--immediate`选项），**只**会发布我们感兴趣的话题。

```
time rosbag play --immediate demo.bag --topics /topic1 /topic2 /topic3 /topicN
```







# 知识点3：launch文件

## parameter和arg

![image-20231212112004664](C:\Users\86153\AppData\Roaming\Typora\typora-user-images\image-20231212112004664.png)

[![image-20231212112004664.png](https://i.postimg.cc/XYZdfwD0/image-20231212112004664.png)](https://postimg.cc/fVNVZ0NH)



# 知识点4：msg和srv的创建、配置、使用

## 1、创建文件夹msg/srv（在功能包下）

![image-20231213002650797](C:\Users\86153\AppData\Roaming\Typora\typora-user-images\image-20231213002650797.png)

## 2、在文件夹里添加消息或服务文档（一种结构体）

![image-20231213003105159](C:\Users\86153\AppData\Roaming\Typora\typora-user-images\image-20231213003105159.png)

![image-20231213003002417](C:\Users\86153\AppData\Roaming\Typora\typora-user-images\image-20231213003002417.png)

## 3、修改package.xml里的依赖（为了使信息和服务可随便变为c或python文件格式）**（难）**

package.xml自带依赖？？？，用于给cmake.list添加依赖？？？

![image-20231213003601983](C:\Users\86153\AppData\Roaming\Typora\typora-user-images\image-20231213003601983.png)

## 4、添加依赖进cmake.list文件里

### 1、添加依赖message_generation（对msg和srv都成立）到find_package（）函数

![](C:\Users\86153\AppData\Roaming\Typora\typora-user-images\image-20231213004038538.png)

### 2、修改服务字段？？？

### ![image-20231213005620733](C:\Users\86153\AppData\Roaming\Typora\typora-user-images\image-20231213005620733.png)

=======
# 知识点1：查找ros发行版本
```
echo $ROS_DISTRO
```
```
melodic
```
或用
```
printenv | grep ROS
```
查看更详细的信息
[image-20231210171930505.png](https://postimg.cc/5jFZ85jh)








# 知识点2：操作



## 基本规律

### 1、node、topic、server

话题：发送指令动作（半双工/单向）

服务：生成，删除小海龟（双工/双向）

参数：背景颜色

```
rosnode list
rosetopic pub [话题eg：cmd_vel] （tab） [信息类型，tab可自动补全] （tab) [调参]
rosserver call [服务eg：/call  /spawn] （tab看是否有参数）
rosparam set
```



### 2、bag文件

*下面所有的命令中，前面都有一个`time`，这样做可以同时输出执行每个命令花费的时间，而且有时这些命令需要很长时间，因此使用`time`命令了解给定命令所需的时间是有必要的。如果您不想使用它，可以放心删除下面任何命令中的`time`。*

#### 1、记录（创建）

##### 1、全部

```
rosbag record -a
```

##### 2、部分

```
rosbag record -O subset /turtle1/cmd_vel /turtle1/pose
```

上述命令中的-O参数告诉rosbag record将数据记录到名为subset.bag的文件中，而后面的topic参数告诉rosbag record只能订阅这两个指定的话题。然后通过键盘控制乌龟随意移动几秒钟，最后按Ctrl+C退出rosbag record命令。

#### 2、查找

```
rosbag info <your bagfile>
```



#### 3、使用运行

1、-r 2   （速率）

```
time rosbag play -r 2 <your bagfile> 
```

2、（使用`--immediate`选项），**只**会发布我们感兴趣的话题。

```
time rosbag play --immediate demo.bag --topics /topic1 /topic2 /topic3 /topicN
```







# 知识点3：launch文件

## parameter和arg

![image-20231212112004664](C:\Users\86153\AppData\Roaming\Typora\typora-user-images\image-20231212112004664.png)

[![image-20231212112004664.png](https://i.postimg.cc/XYZdfwD0/image-20231212112004664.png)](https://postimg.cc/fVNVZ0NH)



# 知识点4：msg和srv的创建、配置、使用

## 1、创建文件夹msg/srv（在功能包下）

![image-20231213002650797](C:\Users\86153\AppData\Roaming\Typora\typora-user-images\image-20231213002650797.png)

## 2、在文件夹里添加消息或服务文档（一种结构体）

![image-20231213003105159](C:\Users\86153\AppData\Roaming\Typora\typora-user-images\image-20231213003105159.png)

![image-20231213003002417](C:\Users\86153\AppData\Roaming\Typora\typora-user-images\image-20231213003002417.png)

## 3、修改package.xml里的依赖（为了使信息和服务可随便变为c或python文件格式）**（难）**

package.xml自带依赖？？？，用于给cmake.list添加依赖？？？

![image-20231213003601983](C:\Users\86153\AppData\Roaming\Typora\typora-user-images\image-20231213003601983.png)

## 4、添加依赖进cmake.list文件里

### 1、添加依赖message_generation（对msg和srv都成立）到find_package（）函数

![](C:\Users\86153\AppData\Roaming\Typora\typora-user-images\image-20231213004038538.png)

### 2、修改服务字段？？？

### ![image-20231213005620733](C:\Users\86153\AppData\Roaming\Typora\typora-user-images\image-20231213005620733.png)



# 知识点五：创建和启动ros功能包

# 一、创建ros功能包

## 1、创建工作空间并初始化(src下)

```
mkdir ~/my_ws/src
cd ~/my_ws/src
catkin_init_workspace
```

## 2、创建功能包(src下)

### 在 `~/my_ws/src 中` 目录创建一个新包，名为 `offboard_py` (在这种情况下) 依赖 `rospy` ：

```
catkin_create_pkg    offboard_py   rospy
```

## 3、编译（在工作空间my_ws下）

```
cd ~/my_ws/
catkin_make
```

## 4、配置环境

```
source ~/my_ws/devel/setup.bash
```

# 二、编写python文件

## 1、在功能包里创建scripts文件夹储存文件

```
roscd offboard_py
mkdir scripts
cd scripts
```

## 2、创建python文件并使其有可执行权限

```
touch offb_node.py
chmod +x offb_node.py
```

# 三、用launch文件运行功能包

## 1、创建launch文件（在功能包下）

```
cd ~/my_ws/src/offboard_py/src
roscd offboard_py
mkdir launch
cd launch
touch start_offb.launch
```

## 2、启动launch文件

```
roslaunched offboard_py start_offb.launch
```

>>>>>>> Stashed changes



# 知识点六：VMware+Ubuntu18.04 磁盘扩容

## 1、首先，需要将虚拟机关机。

## 2、进入到虚拟机的设置界面，如下图:

![在这里插入图片描述](%E7%9F%A5%E8%AF%86%E7%82%B91%EF%BC%9A%E6%9F%A5%E6%89%BEros%E5%8F%91%E8%A1%8C%E7%89%88%E6%9C%AC.assets/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2xpbnV4X2VtYmVkZGVk,size_16,color_FFFFFF,t_70.png)

## 3、进入磁盘扩展界面，如下，修改扩展后的磁盘容量为:41G，保存。

![在这里插入图片描述](%E7%9F%A5%E8%AF%86%E7%82%B91%EF%BC%9A%E6%9F%A5%E6%89%BEros%E5%8F%91%E8%A1%8C%E7%89%88%E6%9C%AC.assets/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2xpbnV4X2VtYmVkZGVk,size_16,color_FFFFFF,t_70-17044583026872.png)

![在这里插入图片描述](%E7%9F%A5%E8%AF%86%E7%82%B91%EF%BC%9A%E6%9F%A5%E6%89%BEros%E5%8F%91%E8%A1%8C%E7%89%88%E6%9C%AC.assets/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2xpbnV4X2VtYmVkZGVk,size_16,color_FFFFFF,t_70-17044583081204.png)

# Gparted合并磁盘空间

## 1、Ubuntu默认情况下是没有安装Gparted工具的，需要自行安装。安装命令如下：

```
sudo apt-get install gparted
```

## 2、gparted需要root权限，执行如下命令进入gparted的配置界面:

```
sudo gparted
```

## 3、首先，看一下，扩容前的磁盘使用情况:

![在这里插入图片描述](%E7%9F%A5%E8%AF%86%E7%82%B91%EF%BC%9A%E6%9F%A5%E6%89%BEros%E5%8F%91%E8%A1%8C%E7%89%88%E6%9C%AC.assets/20190125092417735.png)

## 4、gparted列出了当前系统的磁盘的所有分区情况，可以看到刚才我们刚刚扩展的分区，显示未使用的状态，如图:

## 5、我们所要做的就是将这部分磁盘空间合并到第一个分区中，我们编辑一下第一个分区，右键，选择更改大小，如图:

## 6、调整磁盘大小到最大，如图:![在这里插入图片描述](%E7%9F%A5%E8%AF%86%E7%82%B91%EF%BC%9A%E6%9F%A5%E6%89%BEros%E5%8F%91%E8%A1%8C%E7%89%88%E6%9C%AC.assets/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2xpbnV4X2VtYmVkZGVk,size_16,color_FFFFFF,t_70-17044584820727.png)

## 7、点击，上方的确认执行按钮，执行磁盘扩容操作，如图:![在这里插入图片描述](%E7%9F%A5%E8%AF%86%E7%82%B91%EF%BC%9A%E6%9F%A5%E6%89%BEros%E5%8F%91%E8%A1%8C%E7%89%88%E6%9C%AC.assets/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2xpbnV4X2VtYmVkZGVk,size_16,color_FFFFFF,t_70-17044584895549.png)

## 8、稍等片刻，扩容成功，如图:![在这里插入图片描述](%E7%9F%A5%E8%AF%86%E7%82%B91%EF%BC%9A%E6%9F%A5%E6%89%BEros%E5%8F%91%E8%A1%8C%E7%89%88%E6%9C%AC.assets/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2xpbnV4X2VtYmVkZGVk,size_16,color_FFFFFF,t_70-170445849560411.png)

## 9、再次查看系统系统分区信息，如图:![在这里插入图片描述](%E7%9F%A5%E8%AF%86%E7%82%B91%EF%BC%9A%E6%9F%A5%E6%89%BEros%E5%8F%91%E8%A1%8C%E7%89%88%E6%9C%AC.assets/20190125092618438.png)

# 总结

## 通过上面的步骤，大家看到了我们使用vmware和gparted可以轻松的完成Ubuntu分区的磁盘空间扩容操作，原来磁盘扩容可以这么简单。









# 知识点七：使用特定配置和初始化文件调用 make 的完整语法为：

```
make [VENDOR_][MODEL][_VARIANT] [VIEWER_MODEL_DEBUGGER_WORLD]、
```

比如

```
make px4_sitl_default gazebo
```

## **VENDOR_MODEL_VARIANT：（又称 `CONFIGURATION_TARGET` ）****

```
make list_config_targets（获取所有可用 CONFIGURATION_TARGET 选项的列表：）
```

### 1、**VENDOR**供应商：**板子的制造商： `px4` 、、、 `airmind` `atlflight` 、 `auav` `beaglebone` `intel` `nxp` `aerotenna` 等。Pixhawk 系列主板的供应商名称是 `px4` 。**

### 2、**MODEL**：板模型“model”：、、 `fmu-v3` 、、 `fmu-v4` `fmu-v5` `navio2` `fmu-v2` 、 `sitl` 等。

### **3、VARIANT**：**表示特定配置：例如 `bootloader` ， `cyphal` 其中包含配置中不存在的 `default` 组件。最常见的是 `default` ，可以省略。**

## **VIEWER_MODEL_DEBUGGER_WORLD：**

### 1、查看器：这是要启动和连接的模拟器（“查看器”）： `gz` 、、 `gazebo` `jmavsim` `none` 、

## 比如

```
cd PX4-Firmware
make px4_fmu-v5_default
```

构建目标 `px4_fmu-v4` 的第一部分表示固件的目标飞行控制器硬件。在本例 `_default` 中，后缀表示固件配置，例如支持或省略特定功能。

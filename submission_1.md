# Ubuntu与ROS1配置

### Ubuntu下载中文输入法

参考https://zhuanlan.zhihu.com/p/529892064

### 软件源

个人推荐国内的阿里云和清华源

### VMware Ubuntu与主机共享剪切板

下载vmware tools，命令：

```plain
sudo apt install open-vm-tools
 
sudo apt install open-vm-tools-desktop
```

（Ubuntu中复制粘贴为windows中的用法加Shift，Shift+Ctrl+c/v）

### VMware Ubuntu与主机共享文件夹

参考https://blog.csdn.net/weixin_63505616/article/details/126202925

### ROS1对Ubuntu版本支持到20.04，这之后要安装ROS1只能从源码下载

参考https://blog.csdn.net/Drknown/article/details/128701624

建议用鱼香ros开源的一键安装（ros1仅在20.04及更低的版本可选），指令：

```plain
wget http://fishros.com/install -O fishros && . fishros
```



# Ubuntu基础指令

pwd（显示当前工作目录绝对路径）

ls（显示目录内容）

cd（跳转）

命令+ --help（提示）

mkdir（创建文件夹）

touch（创建文本文件）

rm（删除） -r（递归，删除整个文件夹用到）

mv（剪切）

cp（复制粘贴）

sudo（暂时获得root用户权限）

history（查看历史命令）

！+序号（运行历史命令）



# ROS1

rqt_graph(节点图形化工具)

rosnode（节点命令）+

list（列出所以运行的节点）

info+节点（列出节点信息）

rostopic（话题命令）+

pub+节点名+数据结构名（手动发布话题一次）

rosmsg+

show+数据结构名（显示发布的数据类型）

rosservice（服务命令）

rosbag record -a -O +文件名（将接下来的指令全部按压缩包保存在新建文件名.bag的压缩包里，-a表示全部，  -O表示压缩包）

catkin_init_workspace（当前文件夹属性变为工作空间）

catkin_creat_pkg +功能包名+依赖包...（创建功能包）

catkin_make(编译工作空间)

source devel/setup.bash(设置环境变量)

（避免每次重新运行source可以将详细的source +路径+devel/setup.bash添加到主文件夹隐藏文件.bashrc的末尾）

echo $ROS_PACKAGE_PATH（检查环境变量）
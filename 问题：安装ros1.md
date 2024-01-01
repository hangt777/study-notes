<<<<<<< Updated upstream
# 问题1：安装ros1

## 自动安装ros：wget http://fishros.com/install -O fishros && . fishros。但是ros1安装不了？
![image-20231210171930505](C:\markdown\Typora\图片\image-20231210171930505.png)  

[![image-20231210171930505.png](https://i.postimg.cc/y6fs4vK8/image-20231210171930505.png](https://postimg.cc/5jFZ85jh)[![image-20231210171930505.png](https://i.postimg.cc/y6fs4vK8/image-20231210171930505.png](https://postimg.cc/5jFZ85jh)

## 解决方法：

### 安装18.4版本的ubuntu，因为22.4不支持ros1

可以此种方法安装镜像源

https://img-blog.csdnimg.cn/20201002105940856.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NTkxMjI5MQ==,size_16,color_FFFFFF,t_70#pic_center

https://img-blog.csdnimg.cn/20201002105943284.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NTkxMjI5MQ==,size_16,color_FFFFFF,t_70#pic_center

https://img-blog.csdnimg.cn/20201002105945958.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NTkxMjI5MQ==,size_16,color_FFFFFF,t_70#pic_center





# 问题2：无法定位软件包+无法解析域名

## 问题描述：

### 1、无法定位软件包  

[![image-20231210175956862.png](https://i.postimg.cc/0jcDfZs9/image-20231210175956862.png)](https://postimg.cc/H88rWwnN)

### 2、无法解析域名

[![QQ-20231210233828.png](https://i.postimg.cc/sxxmhV1q/QQ-20231210233828.png)
[](https://postimg.cc/vxR5Rwrt)

## 















## 原因：

### 软件源的问题，要更新软件源

## 解决方法：
### 1、更新镜像源

```
sudo apt-get updaate
sudo apt-get upgrade
```
### 2、若还是不行，就换镜像源：

 在软件和更新里——下载自——其他——选服务器（清华，阿里）



# 问题3：无法跑鱼香ros的launch文件

[![image-20231212152739130.png](https://i.postimg.cc/WpnGTpJx/image-20231212152739130.png)](https://postimg.cc/pymhBHCB)

![image-20231212152739130](C:\Users\86153\AppData\Roaming\Typora\typora-user-images\image-20231212152739130.png)

## 问题描述：

### ERROR:cannot launch node of type

## 原因：

### 没有配置好环境（只是把learning_launch功能包文件复制到my_ws工作空间中，还要把其他功能包复制过来）

## 解决方法：

### 1、先复制功能包

[![image-20231212152953763.png](https://i.postimg.cc/pL7Q40nT/image-20231212152953763.png)](https://postimg.cc/0zYJJ0nR)

![image-20231212152953763](C:\Users\86153\AppData\Roaming\Typora\typora-user-images\image-20231212152953763.png)

### 2、编译工作空间

[![image-20231212153122817.png](https://i.postimg.cc/Hkf5BVf8/image-20231212153122817.png)](https://postimg.cc/pmJpdXVP)

![image-20231212153122817](C:\Users\86153\AppData\Roaming\Typora\typora-user-images\image-20231212153122817.png)

### 3、配置环境+运行launch文件

[![image-20231212153404987.png](https://i.postimg.cc/TYNn5k09/image-20231212153404987.png)](https://postimg.cc/JGJs959D)

![image-20231212153404987](C:\Users\86153\AppData\Roaming\Typora\typora-user-images\image-20231212153404987.png)



# 问题4：

=======
# 问题1：安装ros1

## 自动安装ros：wget http://fishros.com/install -O fishros && . fishros。但是ros1安装不了？
![image-20231210171930505](C:\markdown\Typora\图片\image-20231210171930505.png)  

[![image-20231210171930505.png](https://i.postimg.cc/y6fs4vK8/image-20231210171930505.png](https://postimg.cc/5jFZ85jh)[![image-20231210171930505.png](https://i.postimg.cc/y6fs4vK8/image-20231210171930505.png](https://postimg.cc/5jFZ85jh)

## 解决方法：

### 安装18.4版本的ubuntu，因为22.4不支持ros1

可以此种方法安装镜像源

https://img-blog.csdnimg.cn/20201002105940856.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NTkxMjI5MQ==,size_16,color_FFFFFF,t_70#pic_center

https://img-blog.csdnimg.cn/20201002105943284.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NTkxMjI5MQ==,size_16,color_FFFFFF,t_70#pic_center

https://img-blog.csdnimg.cn/20201002105945958.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NTkxMjI5MQ==,size_16,color_FFFFFF,t_70#pic_center





# 问题2：无法定位软件包+无法解析域名

## 问题描述：

### 1、无法定位软件包  

[![image-20231210175956862.png](https://i.postimg.cc/0jcDfZs9/image-20231210175956862.png)](https://postimg.cc/H88rWwnN)

### 2、无法解析域名

[![QQ-20231210233828.png](https://i.postimg.cc/sxxmhV1q/QQ-20231210233828.png)
[](https://postimg.cc/vxR5Rwrt)

## 















## 原因：

### 软件源的问题，要更新软件源

## 解决方法：
### 1、更新镜像源

```
sudo apt-get updaate
sudo apt-get upgrade
```
### 2、若还是不行，就换镜像源：

 在软件和更新里——下载自——其他——选服务器（清华，阿里）



# 问题3：无法跑鱼香ros的launch文件

[![image-20231212152739130.png](https://i.postimg.cc/WpnGTpJx/image-20231212152739130.png)](https://postimg.cc/pymhBHCB)

![image-20231212152739130](C:\Users\86153\AppData\Roaming\Typora\typora-user-images\image-20231212152739130.png)

## 问题描述：

### ERROR:cannot launch node of type

## 原因：

### 没有配置好环境（只是把learning_launch功能包文件复制到my_ws工作空间中，还要把其他功能包复制过来）

## 解决方法：

### 1、先复制功能包

[![image-20231212152953763.png](https://i.postimg.cc/pL7Q40nT/image-20231212152953763.png)](https://postimg.cc/0zYJJ0nR)

![image-20231212152953763](C:\Users\86153\AppData\Roaming\Typora\typora-user-images\image-20231212152953763.png)

### 2、编译工作空间

[![image-20231212153122817.png](https://i.postimg.cc/Hkf5BVf8/image-20231212153122817.png)](https://postimg.cc/pmJpdXVP)

![image-20231212153122817](C:\Users\86153\AppData\Roaming\Typora\typora-user-images\image-20231212153122817.png)

### 3、配置环境+运行launch文件

[![image-20231212153404987.png](https://i.postimg.cc/TYNn5k09/image-20231212153404987.png)](https://postimg.cc/JGJs959D)

![image-20231212153404987](C:\Users\86153\AppData\Roaming\Typora\typora-user-images\image-20231212153404987.png)



# 问题4：无法安装PX4源代码

## 问题描述：无法克隆

```
无法克隆 'https://github.com/PX4/PX4-FlightGear-Bridge.git' 到子模组路径 '/home/jeremy/PX4-Autopilot/Tools/flightgear_bridge'
克隆 'Tools/flightgear_bridge' 失败。按计划重试
```

## 解决办法：

### 1、可以先将PX4文件克隆下来，不去克隆子项目，运行下面指令

```
git clone https://github.com.cnpmjs.org/PX4/PX4-Autopilot.git
```

### 2、然后切换到PX4文件夹，继续克隆子项目,执行下面指令

```
cd PX4-Autopilot
git submodule update --init --recursive
```

### 3、如果还是出现失败也没关系，继续执行

```
git submodule update --recursive`
```

### 直到不出现失败提示为止。（这时是在继续克隆你之前没成功的子项目，注意：此时没有init)



# 问题4：bash文件运行

## 问题描述：mirrors.aliyun.com 无法解析

![image-20231220204413959](%E9%97%AE%E9%A2%98%EF%BC%9A%E5%AE%89%E8%A3%85ros1.assets/image-20231220204413959.png)

## 解决方法：

### 一：已知可行：

#### 1、运行

```
sudo gedit /etc/resolv.conf 
```

#### 2、修改文件参数（更改里面的nameserver）

```
nameserver 8.8.8.8 
nameserver 8.8.4.4
nameserver 223.5.5.5
nameserver 223.6.6.6
```

### 二:待定：

#### 更换软件源



# 问题五：bash文件运行过程

## 问题描述：retrying......Could not find a version that satisfies the requirement

## ![image-20231220211301889](%E9%97%AE%E9%A2%98%EF%BC%9A%E5%AE%89%E8%A3%85ros1.assets/image-20231220211301889.png)

## 解决方法：

### 循环操作直至依赖全部安装好

![image-20231220214857983](%E9%97%AE%E9%A2%98%EF%BC%9A%E5%AE%89%E8%A3%85ros1.assets/image-20231220214857983.png)

## 问题分析

### 1检查pip的版本（升级版本）

```
python -m pip install --upgrade pip
```

### 2更换一个pip源或换软件源

#### 1、这时考虑换一个pip源

```
pip install pymysql -i https://pypi.tuna.tsinghua.edu.cn/simple/
```

#### 2、换软件源

### 3用镜像安装库（考虑是网速的原因，这时采用国内的镜像源来加速）

```
pip install 包名-i http://pypi.douban.com/simple/ --trusted-host pypi.douban.com
```

```text
阿里源 http://mirrors.aliyun.com/pypi/simple/

中国科技大学 https://pypi.mirrors.ustc.edu.cn/simple/ 

清华大学 https://pypi.tuna.tsinghua.edu.cn/simple/
```

直接运行下面的代码

```
bash ./PX4-Autopilot/Tools/setup/ubuntu.sh
```

是将安装相对完整的PX4固件环境需要下载的依赖包多，因为网络原因造成的报错更多**。此外，不管运行哪一个命令，其实大概率都会【遇到一堆红色的报错】，解决方法其实也很简单，即 【**确定导致报错的依赖包名，网上检索安装这个依赖包的方法】**。我们只需要将导致报错的依赖包都安装好了，运行.sh文件时就能会跳过他们。

## PS:如果安装好sympy库后，仍然不行。则按照以下方法把文件里的sympy>=1.10.1改为sympy

![image-20231222195839544](%E9%97%AE%E9%A2%98%EF%BC%9A%E5%AE%89%E8%A3%85ros1.assets/image-20231222195839544.png)





















>>>>>>> Stashed changes

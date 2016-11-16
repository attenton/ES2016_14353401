####lab5 ROS的配置
由于虚拟机装的是ubuntu 16.04，所以是ubuntu 16.04的配置文档
######1.配置Ubuntu的软件库
首先确认是否可以使用命令下载软件库，具体可以参考：<a href="https://help.ubuntu.com/community/Repositories/Ubuntu">向导</a>
######2.设置源列表
设置可以获取来自package.ros.org的软件
```bash
sudo sh -c 'echo "deb http://packages.ros.org/ros/ubuntu $(lsb_release -sc) main" > /etc/apt/sources.list.d/ros-latest.list'
```
######3.设置密钥
```bash
sudo apt-key adv --keyserver hkp://ha.pool.sks-keyservers.net:80 --recv-key 0xB01FA116
```
######4.安装ROS
首先确认是否是最新的软件包：
```bash
sudo apt-get update
```
安装ROS，我安装的是Desktop-Full:
```bash
sudo apt-get install ros-kinetic-desktop-full
```
######5.初始化rosdep
在使用ROS之前，需要先初始化rosdep，rosdep可以使你更简单地安装需要编译的系统。
```bash
sudo rosdep init
rosdep update
```
######6.环境变量设置
为了是ROS的环境变量能够自动的添加到bash session，使用如下命令：
```bash
echo "source /opt/ros/kinetic/setup.bash" >> ~/.bashrc
source ~/.bashrc
```
######7.安装rosinstall
rosinstall是ROS经常使用的命令行工具，安装命令如下：
```bash
sudo apt-get install python-rosinstall
```

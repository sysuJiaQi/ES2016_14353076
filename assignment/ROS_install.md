## Description（ROS框架描述） ##

**Robot Operation System (ROS)** 是一套框架，底层提供硬件驱动，软件层面支持通用的文件格式。我们主要使用它的仿真功能。

## How to install ##

#### 1. 配置 Ubuntu 的软件仓库，允许“restricted”，“universe”，“multiverse” ####

![photo1](http://a1.qpic.cn/psb?/V10tjyIS2Dudkp/bTa9yXRUyb9NbQz8U2IiMtM2sg85mmW*MCYTtG93qnA!/b/dHcBAAAAAAAA&bo=UwIlAVMCJQEDACU!&rf=viewer_4)

#### 2. 配置sources.list ####
 
设置计算机接受来自 packages.ros.org 的软件，ROS Jade 只支持 Trusty (14.04), Utopic (14.10) and Vivid (15.04) 的 Debian 软件包。

**sudo sh -c 'echo "deb http://packages.ros.org/ros/ubuntu $(lsb_release -sc) main" > /etc/apt/sources.list.d/ros-latest.list'**

#### 3. 设置 keys ####
 
**sudo apt-key adv --keyserver hkp://ha.pool.sks-keyservers.net:80 --recv-key 0xB01FA116**

![photo2](http://a3.qpic.cn/psb?/V10tjyIS2Dudkp/8NI7KBAKPPMZtVskyQrtWsazzAsCdjnf5pp99AwlQHg!/b/dHwBAAAAAAAA&bo=1wLOANcCzgADACU!&rf=viewer_4)

#### 4. 安装 ####
 
首先，确保 Debian 软件包的 index 是最新的。

**sudo apt-get update**

ROS 有很多不同的库和工具，这里选择了配置桌面完全安装，它包括：ROS, rqt, rviz, robot-generic libraries, 2D/3D simulators, navigation and 2D/3D perception

**sudo apt-get install ros-jade-desktop-full**

![photo3](http://a3.qpic.cn/psb?/V10tjyIS2Dudkp/H.H*KbsR2YdH0WNJ8IyHpq8c*oDxY*3.90ohQqzVzbg!/b/dHwBAAAAAAAA&bo=twK2ALcCtgADACU!&rf=viewer_4)

要查找可用的软件包，使用：

**apt-cache search ros-jade**

![photo4](http://a2.qpic.cn/psb?/V10tjyIS2Dudkp/KximUo4J8uRAO6uARqxg8qKo9KcQVPPUfR2MjjFcJ8c!/b/dNwAAAAAAAAA&bo=1QJUAdUCVAEDACU!&rf=viewer_4)

#### 5. 初始化 rosdep ####

在使用ROS之前，需要初始化 rosdep。rosdep 使你可以轻松地安装系统对要编译的源的依赖关系，并且在 ROS 中运行一些核心组件时也需要rosdep。

**sudo rosdep init**

![photo5](http://a3.qpic.cn/psb?/V10tjyIS2Dudkp/mXhy32Vbuy40ZOLSw565LhWDnOgZbNwOXJsBKDDB0JM!/b/dI8AAAAAAAAA&bo=3gGqAN4BqgADACU!&rf=viewer_4)

**rosdep update**

![photo6](http://a3.qpic.cn/psb?/V10tjyIS2Dudkp/CM7Znp3iq*kgDMgO8GNPiW9XweZsc3TEqX4LJeWdmYg!/b/dAoBAAAAAAAA&bo=1gI3AdYCNwEDACU!&rf=viewer_4)

#### 6. 环境设置 ####

每次有新的 shell 启动时，如果 ROS 环境变量能自动添加到 bash 命令，这会是很方便的。

**echo "source /opt/ros/jade/setup.bash" >> ~/.bashrc**

**source ~/.bashrc**

如果已安装了多个 ROS 分布，_~/.bashrc_ 只能获取你正在使用的版本的 _setup.bash_。

如果只想改变当前的 shell 环境，可以键入：

**source /opt/ros/jade/setup.bash**

![photo7](http://a3.qpic.cn/psb?/V10tjyIS2Dudkp/b8*0Cyw0PXSazjn5kEblLew*bKoR7be2adoyv3stKkU!/b/dAoBAAAAAAAA&bo=hgJLAIYCSwADACU!&rf=viewer_4)

#### 7. 获取 rosinstall ####

rosinstall 是 ROS 经常使用的命令行工具，使用一条命令就可以轻松下载 ROS 包的源代码树。

在 Ubuntu 安装这个工具，运行：

**sudo apt-get install python-rosinstall**

![photo8](http://a1.qpic.cn/psb?/V10tjyIS2Dudkp/DPCgyGdAryaOzjeq1Tt4v1hWhegyZUCH0uPztS2fUPI!/b/dHcBAAAAAAAA&bo=egIkAXoCJAEDACU!&rf=viewer_4)

## Experimental experience ##

ROS 安装过程较漫长，按照官网的安装文档一步步配置，最终也安装完成。安装过程中要注意根据自己的计算机选择合适的版本，出现错误时仔细检查命令是否打错，根据报错信息寻找解决方案。
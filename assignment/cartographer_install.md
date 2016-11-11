## Description（Cartographer 算法描述） ##

**Cartographer** 是 Google 开源的一个 SLAM 算法，基于激光雷达以及 IMU（惯性处理单元）。

## How to install ##

#### 0. 安装所有依赖项 ####

**sudo apt-get install -y google-mock libboost-all-dev  libeigen3-dev libgflags-dev libgoogle-glog-dev liblua5.2-dev libprotobuf-dev  libsuitesparse-dev libwebp-dev ninja-build protobuf-compiler python-sphinx  ros-indigo-tf2-eigen libatlas-base-dev libsuitesparse-dev liblapack-dev**

![photo1](http://a2.qpic.cn/psb?/V10tjyIS2Dudkp/zq*DR4Pu3dDDP3sIMvVWOMC*KlKBqp5r1*5dh75asRo!/b/dAwBAAAAAAAA&bo=zwLkAM8C5AADACU!&rf=viewer_4)

#### 1. 安装 ceres solver，选择的版本是1.11 ####

**git clone https://github.com/hitcm/ceres-solver-1.11.0.git**

![photo2](http://a3.qpic.cn/psb?/V10tjyIS2Dudkp/20PPvAl31s6VyeDxla5T9kBVKwAU04NeMXSzQgLQxyg!/b/dHwBAAAAAAAA&bo=zwKUAM8ClAADACU!&rf=viewer_4)

**cd ceres-solver-1.11.0**  
**mkdir build**  
**cd build**

**cmake ..**

![photo3](http://a1.qpic.cn/psb?/V10tjyIS2Dudkp/mM3fuQmVoQy1S93M0dlFj6HpDxcqnA9t2BHa5heldKg!/b/dAsBAAAAAAAA&bo=0wIaAdMCGgEDACU!&rf=viewer_4)

**make**

![photo4](http://a2.qpic.cn/psb?/V10tjyIS2Dudkp/j*nl8kb15QDzSy4wLRYiL00ILHzc7RchcOYlhMaa0k0!/b/dAwBAAAAAAAA&bo=0gIbAdICGwEDACU!&rf=viewer_4)

**sudo make install**

![photo5](http://a2.qpic.cn/psb?/V10tjyIS2Dudkp/6HiWvDfkBiSdg2bQas8CZHM0H.3*hqFo.bgI4AQMm7I!/b/dNwAAAAAAAAA&bo=WwLRAFsC0QADACU!&rf=viewer_4)

#### 2. 安装 cartographer ####
 
**git clone https://github.com/hitcm/cartographer.git**

![photo6](http://a1.qpic.cn/psb?/V10tjyIS2Dudkp/SxD3JLKK56zMlL7b2dkF0ZeKQFfdjtGNphuxexL3z*A!/b/dHcBAAAAAAAA&bo=igKQAIoCkAADACU!&rf=viewer_4)

**cd cartographer**  
**mkdir build**  
**cd build**

**cmake .. -G Ninja**

![photo7](http://a1.qpic.cn/psb?/V10tjyIS2Dudkp/t8dZqBLOsepC1DFUTimSjMV7IEFEQD3DvKxD*7KAdXA!/b/dHcBAAAAAAAA&bo=jgKwAI4CsAADACU!&rf=viewer_4)

**ninja**

![photo8](http://a1.qpic.cn/psb?/V10tjyIS2Dudkp/.4LOt5AR6.otQidku8Z.1Z1iNwrYcz6EAPQNN1hJSvI!/b/dHcBAAAAAAAA&bo=1ALUANQC1AADACU!&rf=viewer_4)

**ninja test**

![photo9](http://a3.qpic.cn/psb?/V10tjyIS2Dudkp/4ftUDeUuM3vNjxZG5Xkxe5KAe7vjd2opjIU02vPN.x4!/b/dHwBAAAAAAAA&bo=1gLkANYC5AADACU!&rf=viewer_4)

如图所示，40个测试全部通过。

**sudo ninja install**

![photo10](http://a2.qpic.cn/psb?/V10tjyIS2Dudkp/YdbYH16HkWsUvT49EKO71aWaMz4DMM8YSP98*hsop80!/b/dAwBAAAAAAAA&bo=0gKcANICnAADACU!&rf=viewer_4)

#### 3. 安装 cartographer_ros ####

**mkdir ~/catkin\_ws**  
**cd ~/catkin_ws**  
**mkdir src**  
**cd src**

![photo11](http://a3.qpic.cn/psb?/V10tjyIS2Dudkp/8VbK3Z.Fl.chb7TvL90sQmE6YJTCzUcy0AxitQtU1uo!/b/dHwBAAAAAAAA&bo=AQJJAAECSQADACU!&rf=viewer_4)

**git clone https://github.com/Durant35/HectorSLAM_catkin.git**

![photo12](http://a2.qpic.cn/psb?/V10tjyIS2Dudkp/OCnSEoR.p2lCktqxkdx4LYIIdV5DUL*piXzbzBxWktY!/b/dAkBAAAAAAAA&bo=1wKnANcCpwADACU!&rf=viewer_4)

**mv HectorSLAM\_catkin/\* .**  
**rm -rf HectorSLAM_catkin/**  
**cd ..**

![photo13](http://a2.qpic.cn/psb?/V10tjyIS2Dudkp/Bp3aU3JxvOa.lwPDX7KdXfTol0mOXGek27gvnBGfQp8!/b/dI0BAAAAAAAA&bo=GwJJABsCSQADACU!&rf=viewer_4)

**catkin_make**

![photo14](http://a2.qpic.cn/psb?/V10tjyIS2Dudkp/17HZ5F*PQzS7t6urvpUqYpEsBYeqySv1WQzU3bnFqag!/b/dAkBAAAAAAAA&bo=1QIHAdUCBwEDACU!&rf=viewer_4)

**source devel/setup.sh**

![photo15](http://a3.qpic.cn/psb?/V10tjyIS2Dudkp/S336bGOOC9CQb28bLhlluzM56Z0qweiE9AcFYK.3j5E!/b/dAoBAAAAAAAA&bo=0wEmANMBJgADACU!&rf=viewer_4)

#### 4. 数据下载测试 ####

2d 数据迅雷下载：

https://storage.googleapis.com/cartographer-public-data/bags/backpack_2d/cartographer_paper_deutsches_museum.bag

然后运行 lanuch 文件：

**roslaunch cartographer_ros demo_backpack_2d.launch bag_filename:=${HOME}/Downloads/cartographer_paper_deutsches_museum.bag**

![photo16](http://a2.qpic.cn/psb?/V10tjyIS2Dudkp/l2FqzW4.XgKyfExhDetfDFeiKto8fDlwE2nHbyo*4ts!/b/dH4BAAAAAAAA&bo=1wJgANcCYAADACU!&rf=viewer_4)

运行时出现了错误，这种错误的主要原因是 ros 的 catkin_ws 配置问题，因此运行 rospack profile：

![photo17](http://a1.qpic.cn/psb?/V10tjyIS2Dudkp/VW1jqYDbUt0C5aKnN0NKBSGHoJrmPRzumk6SsGUdgy8!/b/dOQAAAAAAAAA&bo=KwK4ACsCuAADACU!&rf=viewer_4)

尝试了教程中给出的两种解决方法，仍然无法运行 launch 文件。

## Experimental experience ##

cartographer 是在 ROS 的基础上进行安装，安装过程仍然很漫长。前面的步骤都顺利完成，只有在最后一步数据下载测试时出现了错误 ，无法运行 launch 文件，有待于进一步查找资料解决。
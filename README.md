## Description（DOL框架描述） ##

**Distributed Operation Layer (DOL)** 是一个为并行应用编程的软件开发框架。DOL允许指定基于Kahn进程网络计算模型的应用，描述了一个基于SystemC的仿真引擎。此外，DOL提供了基于XML规范的格式，来描述一个多处理器系统上的并行应用程序的实现，包括结合和映射。

DOL基本上由三个部分组成：

- DOL 应用程序接口
- DOL 功能仿真
- DOL 映射优化

## How to install ##

1. **使用 VMware 虚拟机安装 Ubuntu 系统**
2. **安装一些必要的环境**  
$ sudo apt-get update  
$ sudo apt-get install ant  
$ sudo apt-get install openjdk-7-jdk  
$ sudo apt-get install unzip
3. **下载文件**  
sudo wget http://www.accellera.org/images/downloads/standards/systemc/systemc-2.3.1.tgz  
sudo wget http://www.tik.ee.ethz.ch/~shapes/downloads/dol_ethz.zip
4. **解压文件**   
新建 dol 的文件夹：  
$ mkdir dol  
将 dol\_ethz.zip 解压到 dol 文件夹中：  
$ unzip dol_ethz.zip -d dol  
解压 systemc：  
$ tar -zxvf systemc-2.3.1.tgz
5. **编译 systemc**  
解压后进入 systemc-2.3.1 的目录下：  
$ cd systemc-2.3.1  
新建一个临时文件夹 obidir：  
$ mkdir obidir  
进入该文件夹 obidir：  
$ cd obidir  
运行 configure（能根据系统的环境设置一下参数，用于编译）：  
$ ../configure CXX=g++ --disable-async-updates  
编译：  
$ sudo make install  
编译完后文件目录如下：  
$ cd ..  
$ ls  
![photo1](http://a2.qpic.cn/psb?/V10tjyIS2Dudkp/Zl*QD6cz31Sq2S9u7Mkjg5D0HtOT1BmulPB.wa3L6jY!/b/dI0BAAAAAAAA&bo=YgJbAGICWwADACU!&rf=viewer_4)  
记录当前的工作路径：  
$ pwd  
![photo2](http://a2.qpic.cn/psb?/V10tjyIS2Dudkp/nFnRyzaAd99bX8wrv1loja7ZGXPc73FOaH1rC9oDCJQ!/b/dAkBAAAAAAAA&bo=VQEmAFUBJgADACU!&rf=viewer_4)  
6. **编译 dol**  
进入刚刚 dol 的文件夹：  
$ cd ../dol  
用刚刚 pwd 的结果修改 build_zip.xml 文件：  
![photo3](http://a3.qpic.cn/psb?/V10tjyIS2Dudkp/gjLcdgXFIOsbusSj*GThm9LYlLqqOOolMBgrQttsKDc!/b/dHwBAAAAAAAA&bo=0AI3ANACNwADACU!&rf=viewer_4)  
编译：  
$ ant -f build\_zip.xml all  
若成功会显示 build successful  
7. **完成安装，尝试运行第一个例子**  
进入 build/bin/main 路径下：  
$ cd build/bin/main  
运行第一个例子：  
$ ant-f runexample.xml -Dnumber=1  
成功结果如图：  
![photo4](http://a3.qpic.cn/psb?/V10tjyIS2Dudkp/LXxT5asliTjf6AamnZ6lN7L5.LJcWCabAobLcpXUl7M!/b/dAoBAAAAAAAA&bo=bQGzAW0BswEDACU!&rf=viewer_4)

## Experimental experience ##

DOL 安装过程较漫长，但由于上学期已在虚拟机装过 Ubuntu，按照实验文档一步步配置，也很顺利的安装完成。

在 github.com 上创建仓库很方便，而利用 Git 向仓库远程提交文件则需要按步骤完成。仓库可以简单理解成一个目录，这个目录里面的所有文件都可以被 Git 管理起来，每个文件的修改、删除，Git 都能跟踪，以便任何时刻都可以追踪历史，或者在将来某个时刻可以“还原”。

Markdown 这种用来写作的轻量级标记语言，使用简洁的语法代替排版，十分方便，使我们专注文字内容而省去了排版的很多麻烦，可读性高，用处很多。

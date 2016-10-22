## 实验内容 ##

**一、修改example2，让3个square模块变成2个**

1. 如何修改  
在example2.xml中修改变量N的定义，将3改为2：  
![photo1](http://p1.bqimg.com/4851/07a1e1785fe8a4da.png)
  
  通过迭代定义N个square模块、N+1条通道（连线）以及连接时，即可将3个模块变为2个，并且对应的通道和连接也随之改变。

2. 修改后的example2.dot截图  
![photo2](http://p1.bqimg.com/4851/ef7f28ad297d141a.png)
  
  如图所示，在generator和consumer之间有2个square模块。

3. 修改后的运行结果  
![photo3](http://p1.bqimg.com/4851/af12d47f71511948.png)
  
  generator生成0~19的整数  
square经过两次平方操作，得到i的4次方  
consumer输出结果

**二、修改example1，使其输出3次方数**

1. 如何修改  
在example1的square.c中修改square_fire信号处理函数：  
![photo4](http://p1.bpimg.com/4851/a15bfdd84c3660fe.png)
  
  在当前位置小于设定长度时，将运算i=i\*i改为i=i\*i*i，即可在square模块中进行3次方运算。

2. 修改后的example1.dot截图  
![photo5](http://p1.bqimg.com/4851/37bf51e7734a85e3.png)
  
  如图所示，在generator和consumer之间有1个square模块。

3. 修改后的运行结果  
![photo6](http://p1.bqimg.com/4851/08e09685dc0887bc.png)
  
  generator生成0~19的整数  
square计算得到i的3次方  
consumer输出结果

## 实验感想 ##

在xml文件中可以定义模块、模块间的通道以及连接。一定要注意每一条通道对应两个连接，分别将通道的接口与模块的接口连接起来。编写代码时应注意通道连接的模块的顺序、连接处的顺序以及各个端口号是否对应。

dot图可以直观地展现整个流程，生产者用于生产数据，消费者用于接收数据并输出，中间的模块用于计算。观察dot图可以帮助我们更好地理解中间的每一个步骤。

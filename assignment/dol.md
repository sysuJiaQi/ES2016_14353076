## 实验内容 ##

**一、修改example2，让3个square模块变成2个**

1. 如何修改  
在example2.xml中修改变量N的定义，将3改为2：  
![photo1](http://a1.qpic.cn/psb?/V10tjyIS2Dudkp/zCstlgMIvdSwSOQrAybhW9kt83dZR0B3L5Opteg4Qtg!/b/dHcBAAAAAAAA&bo=GAEYABgBGAADACU!&rf=viewer_4)
  
  通过迭代定义N个square模块、N+1条通道（连线）以及连接时，即可将3个模块变为2个，并且对应的通道和连接也随之改变。

2. 修改后的example2.dot截图  
![photo2](http://a2.qpic.cn/psb?/V10tjyIS2Dudkp/kD16mFn2pj6Nj94j4OxJywi9MuazuwPEzmv91AF9S8c!/b/dHIBAAAAAAAA&bo=bAL4AGwC.AADACU!&rf=viewer_4)
  
  如图所示，在generator和consumer之间有2个square模块。

3. 修改后的运行结果  
![photo3](http://a2.qpic.cn/psb?/V10tjyIS2Dudkp/7XcGaKi714TKDutCrJipYszioLyPKomVMfCQJHoqk3g!/b/dAwBAAAAAAAA&bo=agG9AWoBvQEDACU!&rf=viewer_4)
  
  generator生成0~19的整数  
square经过两次平方操作，得到i的4次方  
consumer输出结果

**二、修改example1，使其输出3次方数**

1. 如何修改  
在example1的square.c中修改square_fire信号处理函数：  
![photo4](http://a3.qpic.cn/psb?/V10tjyIS2Dudkp/YfDuh*g0xfxHwZ7vQi4wfxZhtWDee*0*iqUjSip95UE!/b/dHwBAAAAAAAA&bo=4gFxAOIBcQADACU!&rf=viewer_4)
  
  在当前位置小于设定长度时，将运算i=i\*i改为i=i\*i*i，即可在square模块中进行3次方运算。

2. 修改后的example1.dot截图  
![photo5](http://a1.qpic.cn/psb?/V10tjyIS2Dudkp/hAxHnRsOKTg2tlU2KeaiJGTesFnngSRR6pF4PJpiAXM!/b/dOEAAAAAAAAA&bo=AAIOAQACDgEDACU!&rf=viewer_4)
  
  如图所示，在generator和consumer之间有1个square模块。

3. 修改后的运行结果  
![photo6](http://a3.qpic.cn/psb?/V10tjyIS2Dudkp/ls8vIruHrBjTHsbXS6gw60nZama18mc7TzMVM1vOGb0!/b/dAoBAAAAAAAA&bo=agG*AWoBvwEDACU!&rf=viewer_4)
  
  generator生成0~19的整数  
square计算得到i的3次方  
consumer输出结果

## 实验感想 ##

在xml文件中可以定义模块、模块间的通道以及连接。一定要注意每一条通道对应两个连接，分别将通道的接口与模块的接口连接起来。编写代码时应注意通道连接的模块的顺序、连接处的顺序以及各个端口号是否对应。

dot图可以直观地展现整个流程，生产者用于生产数据，消费者用于接收数据并输出，中间的模块用于计算。观察dot图可以帮助我们更好地理解中间的每一个步骤。

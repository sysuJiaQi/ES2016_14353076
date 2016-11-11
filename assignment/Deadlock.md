### 一、死锁停在第几次的截图 ###

![photo1](http://a2.qpic.cn/psb?/V10tjyIS2Dudkp/68J.2EuNUxdk6oPuCn0toPYbcw1slKh9Ilq5MsTPaSY!/b/dAkBAAAAAAAA&bo=OgFkAToBZAEDACU!&rf=viewer_4)
  
如图所示，在程序运行第203次时发生死锁。

### 二、产生死锁的4个必要条件 ###

- **互斥条件**：一个资源每次只能被一个进程使用；
- **请求与保持条件**：一个进程因请求资源而阻塞时，对已获得的资源保持不放；
- **不剥夺条件**：进程已获得的资源，在未使用完之前，不能强行剥夺；
- **循环等待条件**：若干进程之间形成一种头尾相接的循环等待资源关系。

### 三、对上述程序产生死锁的解释 ###

类Deadlock继承了Runnable，它是一个线程，会在后台默默地运行，每次调度到它执行的时候，它就运行run()中的语句。而java程序从main函数开始执行，时间轴如下图所示：

![photo2](http://a1.qpic.cn/psb?/V10tjyIS2Dudkp/CUj3iHVKH3lwuKOnyPl91V9Rn4LgS2.yd4MEg96UpoM!/b/dHEBAAAAAAAA&bo=gQGQAYEBkAEDACU!&rf=viewer_4)

类A中的两个方法methodA(B b)和last()都使用了关键字synchronized，当一个线程访问类对象的一个函数时，其他线程对同一个对象的其他函数的访问也将被阻塞，类B也同理。这满足了资源互斥条件，若a为类A的一个对象，b为类B的一个对象，那么资源a或b每次只能被一个线程使用。

由于线程 t 被调度的时间不确定，可能发生主线程的a.methodA(b)和 t 线程的b.methodB(a)同时执行的情况。此时主线程占有了a资源，要执行b.last()就是在请求b资源；而 t 线程占有了b资源，要执行a.last()就是在请求a资源。这满足了循环等待条件，因此产生死锁。

产生死锁要满足上述条件，因此并不是每一次运行都会产生死锁。当运行很多次时，哪一次产生死锁停下来是随机的。

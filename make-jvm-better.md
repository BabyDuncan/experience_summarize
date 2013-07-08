# JVM 调优总结
##关于堆
### 设置选项如下 -X部分,标准配置:
>#### -Xmx 设置JVM的最大可用内存 如: -Xmx4096m
>#### -Xms 设置JVM的最小可用内存 如: -Xms4096m
>#### -Xmn 设置JVM的新生代大小  如: -Xmn2048m
>#### -Xss 设置每个线程的堆栈大小  如: -Xss128k


### -XX 部分,非官方配置,但是也是安全的配置:
>#### -XX:NewRatio 设置新生代和旧生代的比值  -XX:NewRatio=4 说明旧生代是新生代的四倍
>####  -XX:SurvivorRatio 设置新生代中Eden和survivor(2个)的比值 如果设置-XX:SurvivorRatio=4 那么  Eden/一个survivor=4 也就是说总量是6.一般把此值设置为65536 这样可以是survivor大小设置为最小.提高性能.
>#### -XX:MaxPermSize 设置持久代的大小
>#### -XX:MaxTenuringThreshold 设置垃圾的最大年龄,如果设置为0,那么新生代的对象不经过survivor,直接进入旧生代.如果设置较大,则新生代对象在survivor区域多次复制,对象在新生代被回收的几率变大.


## 关于回收器
###回收器共有以下三种:
* 串行回收器
* 并行回收器
* 并发回收器

####串行回收器 太老已经out了,不建议再使用
####并行回收器 以吞吐量为优先,可以增加jvm的吞吐量
> 并行回收器的设置如下:

>-XX:+UseParallelGC  设置新生代为并行回收 并且 -XX:ParallelGCThreads=20 并行回收线程数为20

>-XX:+UseParallelOldGC 设置旧生代为并行回收

>-XX:MaxGCPauseMillis=100 设置并行回收的最长时间

>-XX:+UseAdaptiveSizePolicy 自动调整新生代大小和回收频率以满足回收时间

#### 并发回收 以响应速度为优先,可以加快jvm的响应速度
> 并发回收器的设置:

>-XX:+UseConcMarkSweepGC 设置旧生代为并发回收

>-XX:CMSFullGCsBeforeCompaction=5 并发回收会产生碎片,所以每隔几次回收就进行一次压缩

>-XX:+UseCMSCompactAtFullCollection 使CMS也压缩,这样会影响性能,但是不会产生碎片了.

##关于辅助信息
###通过-XX 的一些设置,可以使jvm打印出很多信息,以观察jvm运行情况
#### -XX:+PrintGC 
> 输出形式：[GC 118250K->113543K(130112K), 0.0094143 secs]
> 
>    [Full GC 121376K->10414K(130112K), 0.0650971 secs] 

####-XX:+PrintGCDetails
>输出形式:[GC [DefNew: 8614K->781K(9088K), 0.0123035 secs] 118250K->113543K(130112K), 0.0124633 secs]
>
>[GC [DefNew: 8614K->8614K(9088K), 0.0000665 secs][Tenured: 112761K->10414K(121024K), 0.0433488 secs] 121376K->10414K(130112K), 0.0436268 secs] 

####-XX:+PrintGCTimeStamps 打印出gc的时间戳
####-XX:+PrintGCApplicationConcurrentTime gc过程中程序未中断的时间
#### -XX:+PrintGCApplicationStoppedTime gc过程中程序中断的时间
#### -XX:PrintHeapAtGC gc前后堆栈的详细信息
#### -Xloggc:filename 把gc相关信息记录在日志中


## JVM调优的经验总结
### 关于新生代 尽可能设置的大,使用并行收集器.
### 关于旧生代 使用并发收集器 开启对旧生代的压缩.
   
             



# JVM 调优的八条建议
* 使用64位jdk 因为64位jdk可以支持更大的内存,是程序的吞吐量更大.
* XMS和XMX 设置一样大,然后MaxPermSize和MinPermSize 设置成一样大.也就是说 设置 jvm的最大可用内存和最小可用内存一样大,然后再设置非堆区的最大值和最小值一样,这样可以减少堆区大小变化带来的消耗.
* -XX:+PrintClassHistogram-XX:+PrintGCDetails-XX:+PrintGCTimeStamps-XX:+PrintHeapAtGC-Xloggc:log/gc.log 多加入一些日志,这样可以从gc.log看出一些问题来.
* 常常使用jstack 和 jmap 查看jvm 运行情况.
* 如果使用了缓存,那么旧生代应该设置的大一些,但是localcache 不应该无限大,应该有一些淘汰策略.
* 关于垃圾回收一个是 去掉 救助空间 -XX:SurvivorRatio=65536-XX:MaxTenuringThreshold=0
还有一个是CMSInitiatingOccupancyFraction 设置为80 或者70 这样 旧生代 在被占用80% 或者70% 的时候就开始执行cms,以保证从新生代过来的对象可以顺利进入旧生代.
* 永生带会随着时间逐渐变满,那么每隔一段时间重启一次服务器还是比较不错的.
* 采用并发回收时，年轻代小一点，年老代要大，因为年老大用的是并发回收，即使时间长点也不会影响其他程序继续运行，网站不会停顿。
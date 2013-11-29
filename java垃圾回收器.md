  名词解释

    Serial：串行收集器，当进行垃圾收集时，会暂停所有线程
    Parallel：并行收集器，是串行收集器的多线程版本，多CPU下
    ParallelOld：老年代的Parallel版本
    ConcMarkSweep：简称CMS，是并发收集器，将部分操作与用户线程并发执行
    CMSIncrementalMode：CMS收集器变种，属增量式垃圾收集器，在并发标记和并发清理时交替运行垃圾收集器和用户线程
    G1：面向服务器端应用的垃圾收集器，计划未来替代CMS收集器

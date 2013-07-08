## 五个很重要的jvm命令
1. jvm 中显式的调用垃圾回收`System.gc()` 是非常危险的.所以引出了第一个命令:
> DisableExplicitGC 禁止显式调用gc    

2. jvm 内存溢出的时候,我们想知道内存溢出的瞬间,堆栈信息的快照,这样引出了第二个命令:
> HeapDumpOnOutOfMemoryError  在溢出的瞬间报讯信息快照
> 可以使用 -XX:HeapDumpPath 来选择保存的位置

3. 把自定义的类放到classpath中,如果你有这样的需要,比如修改了Integer类,然后想让jvm load到这个类,那么下一个命令就出来了.
> -Xbootclasspath 命令可以是你自定义jvm的classpath
> -Xbootclasspath/p 将其前置到现有classpath中 (preappend)
> -Xbootclasspath/a 将其后置在现有classpath中 (append)

4. 当你需要更多的信息来观察jvm的运行状态的时候,这个命令就出来了
> -verbose [:class|gc|jni] 他可以尽量多的打出class或者gc或者jni的一些日志

5. 当你需要一些更多的jvm运行参数的时候,java -X 为你提供
> BabyDuncantekiMacBook-Pro:jvm babyduncan$ java -X
 
    -Xmixed           mixed mode execution (default)
    
    -Xint             interpreted mode execution only
    
    -Xbootclasspath:<directories and zip/jar files separated by :>
                      set search path for bootstrap classes and resources
                      
    -Xbootclasspath/a:<directories and zip/jar files separated by :>
                      append to end of bootstrap class path
                      
    -Xbootclasspath/p:<directories and zip/jar files separated by :>
                      prepend in front of bootstrap class path
                      
    -Xnoclassgc       disable class garbage collection
    
    -Xloggc:<file>    log GC status to a file with time stamps
    
    -Xbatch           disable background compilation
    
    -Xms<size>        set initial Java heap size
    
    -Xmx<size>        set maximum Java heap size
    
    -Xss<size>        set java thread stack size
    
    -Xprof            output cpu profiling data
    
    -Xfuture          enable strictest checks, anticipating future default
    
    -Xrs              reduce use of OS signals by Java/VM (see documentation)
    
    -Xdock:name=<application name>
                      override default application name displayed in dock
                      
    -Xdock:icon=<path to icon file>
                      override default icon displayed in dock
                     
    -Xcheck:jni       perform additional checks for JNI functions
    
    -Xshare:off	      do not attempt to use shared class data
    
    -Xshare:auto      use shared class data if possible (default)
    
    -Xshare:on	      require using shared class data, otherwise fail.
    







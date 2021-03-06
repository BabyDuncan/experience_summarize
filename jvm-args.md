### jvm 的参数说明:

#### Heap Size
    堆区设置:
    -Xmx 最大的堆值   
    -Xms 初始化的堆值
    最佳实践: 一般设置两个数值一样大,以免堆区频繁扩展和收缩.
    
#### 年轻代
    -Xmn 最大年轻代值
    -XX:NewSize 初始化年轻代值
    最佳实践: 一般设置两个值一样大,避免年轻代频繁扩展和收缩.
    如果只设置了-Xmn 没有设置 -XX:NewSize ,那么默认 -XX:NewSize 等于-Xmn ^_^ 很人性化啊.
    
#### 年老代
    如果设置了 -Xmn 那么 年老代=堆区-年轻代
    如果没有设置 -Xmn 那么按照比例划分 比例参数为: -XX:NewRatio 默认是8 那么年老代等于堆区的九分之八
    年轻代占堆的九分之一.
    如果同时设置了 -Xmn 以及-XX:NewRatio 那么以 -Xmn 也就是减法为准.
    
#### 年轻代中得eden 以及s0 s1 也就是 from 和 to
    根据比例 按照参数 -XX:SurvivorRatio 计算得出,默认也是8 也就是说年轻代分成10份 eden占有8份 s0 和s1 各占1份.

#### 持久代
    -XX:MaxPermSize 最大持久代数值
    -XX:PermSize    初始化持久代数值
    为了避免数值动荡,一般也设置成一样的.
    
#### Thread Stack Size
    线程堆栈 以-Xss  参数设置,一般设置为256k 如果程序线程非常多,可以适量减小,保证线程数量.但是一般一个实例的线程数量应该在3000-5000之间,所以也不应该设置过小.
    
    
    

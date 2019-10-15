<code>
<h1>解决weblogic启动慢和创建域慢的方法</h1>

    创建域慢启动慢的特征：创建域到70%时，进程长时间等待（命令行创建时停止在100%处），创建域启动Weblogic的时候也是长时间停止。 
    Weblogic在Linux下启动慢的原因，发现从进程堆来看，线程挂在security相关的随机数生成上面，是由于JDK的Bug(JDK从/dev/random读取‘randomness’经常耗费10分钟或者更长的时间)。
    SecureRandom在java各种组件中使用广泛，可以可靠的产生随机数。但在大量产生随机数的场景下，性能会较低。
    这时可以使用"-Djava.security.egd=file:/dev/./urandom" 加快随机数产生过程。
    
    解决方案：后台启动并打印日志
    nohup ./startWebLogic.sh -Djava.security.egd=file:/dev/./urandom > iamhuda.log &




</code>

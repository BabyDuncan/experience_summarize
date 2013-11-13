###     use_jstatd_and_visualVM_watch_a_remote_jvm
-----------

first vim a file named jstatd.java.policy :
>   grant codebase "file:${java.home}/../lib/tools.jar" {
>
>     permission java.security.AllPermission;
>     
>   };

then :
>   nohup jstatd -J-Djava.security.policy=./jstatd.java.policy -J-Djava.rmi.server.logCalls=true > /opt/logs/jstatd.log 2>&1 &

now ,you can watch it via a visualVM jstatd connection .

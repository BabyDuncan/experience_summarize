Hi folks, 

I have a strange error using the assembly plugin on CentOs4.7. 
Obvioulsy the same checkout on windows works like a charm. 

For information my build is multi-module an two modules have an assembly. 
The first succeed and the second fails. It even fails when i call it 
in a mono module. 

I attached the offending assembly descriptor. 

Thanks in advance for any help. 

Regards, 

Raphaël 

Here the error i have: 
[INFO] Failed to create assembly: Error creating assembly archive 
source-distribution: Failed to retrieve numeric file attributes using: 
'/bin/sh -c ls -1nlaR /' 

[INFO] ------------------------------------------------------------------------ 
[INFO] Trace 
org.apache.maven.lifecycle.LifecycleExecutionException: Failed to 
create assembly: Error creating assembly archive source-distribution: 
Failed to retrieve numeric file attributes using: '/bin/sh -c ls 
-1nlaR /' 



## SOLVE

Hi I solved my problem: 
I should have not specified `<directory>/<directory>` in the descriptor. 
I should have removed that line. 


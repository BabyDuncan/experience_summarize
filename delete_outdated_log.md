### delete outdated log 
______________________________

you can use crontab to delete outdated log automatly 。

your hard disk is becoming less and less,but your log is becoming more and more .

you must delete some old log files unless you want to recieve some messages about "hd have no space" when you are hanging out . that sucks ...

use crontab to delete them 

>   /usr/bin/find /opt/logs/project/ -type d -mtime +15 |xargs rm -rf

you will enjoin it  .

no experience on crontab  ? 
>   crontab -l 

show all your contrb.

>   0 0 * * *  /usr/bin/find /opt/logs/project/ -type d -mtime +15 |xargs rm -rf

everyday 00:00 delete the outdated logs .

be careful !! souce some system params when using crontab if necessarry . crontab do not source /etc/profile or ~/.bash_profile 

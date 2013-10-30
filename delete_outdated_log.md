### delete outdated log 
______________________________

you can use crontab to delete outdated log automatly 。

your hard disk is become little and lilttle,but your log is become more and more .

you must delete some old log files unless you want to recieve some messages about "hd have no space" when you are hanging out . that sucks ...

use crontab to delete them 

>   /usr/bin/find /opt/logs/project/ -type d -mtime +15 |xargs rm -rf

you will enjoin it  .

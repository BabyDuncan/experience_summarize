performance_resin_jetty_netty
=============================
resin:
>
    ab -n 10000 -c 1000 "http://10.16.1.48:8083/"
    This is ApacheBench, Version 2.3 <$Revision: 655654 $>
    Copyright 1996 Adam Twiss, Zeus Technology Ltd, http://www.zeustech.net/
    Licensed to The Apache Software Foundation, http://www.apache.org/
    Benchmarking 10.16.1.48 (be patient)
    Completed 1000 requests
    Completed 2000 requests
    Completed 3000 requests
    Completed 4000 requests
    Completed 5000 requests
    Completed 6000 requests
    Completed 7000 requests
    Completed 8000 requests
    Completed 9000 requests
    Completed 10000 requests
    Finished 10000 requests
    Server Software:
    Server Hostname:        10.16.1.48
    Server Port:            8083
    Document Path:          /
    Document Length:        8 bytes
    Concurrency Level:      1000
    Time taken for tests:   3.255 seconds
    Complete requests:      10000
    Failed requests:        0
    Write errors:           0
    Total transferred:      861634 bytes
    HTML transferred:       80152 bytes
    Requests per second:    3072.62 [#/sec] (mean)
    Time per request:       325.455 [ms] (mean)
    Time per request:       0.325 [ms] (mean, across all concurrent requests)
    Transfer rate:          258.54 [Kbytes/sec] received
    Connection Times (ms)
                  min  mean[+/-sd] median   max
    Connect:       17   78 237.5     30    2848
    Processing:     3  157 322.8     31    2742
    Waiting:        3  137 282.1     31    2451
    Total:         41  235 402.4     63    2864
    Percentage of the requests served within a certain time (ms)
      50%     63
      66%     72
      75%    161
      80%    344
      90%    706
      95%   1009
      98%   1685
      99%   1864
     100%   2864 (longest request)

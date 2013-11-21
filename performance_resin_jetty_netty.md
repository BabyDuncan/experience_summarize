performance_resin_jetty_netty
=============================

resin:
>   

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
    Server Software:        Resin/3.1.12
    Server Hostname:        10.16.1.48
    Server Port:            8080
    Document Path:          /protocol_performance/httpPerf
    Document Length:        8 bytes
    Concurrency Level:      1000
    Time taken for tests:   7.935 seconds
    Complete requests:      10000
    Failed requests:        0
    Write errors:           0
    Total transferred:      2750275 bytes
    HTML transferred:       80008 bytes
    Requests per second:    1260.31 [#/sec] (mean)
    Time per request:       793.455 [ms] (mean)
    Time per request:       0.793 [ms] (mean, across all concurrent requests)
    Transfer rate:          338.50 [Kbytes/sec] received
    Connection Times (ms)
                  min  mean[+/-sd] median   max
    Connect:        2   20  38.8      6     812
    Processing:     7  574 1434.5     63    7857
    Waiting:        7  543 1422.2     62    7857
    Total:         13  595 1455.1     70    7920
    Percentage of the requests served within a certain time (ms)
      50%     70
      66%    103
      75%    283
      80%    419
      90%   1498
      95%   3943
      98%   6714
      99%   7006
     100%   7920 (longest request)


jetty:
>
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
    Server Software:        Jetty(8.1.14.v20131031)
    Server Hostname:        10.16.1.48
    Server Port:            8082
    Document Path:          /protocol_performance/httpPerf
    Document Length:        8 bytes
    Concurrency Level:      1000
    Time taken for tests:   5.306 seconds
    Complete requests:      10000
    Failed requests:        0
    Write errors:           0
    Total transferred:      3019978 bytes
    HTML transferred:       80016 bytes
    Requests per second:    1884.74 [#/sec] (mean)
    Time per request:       530.578 [ms] (mean)
    Time per request:       0.531 [ms] (mean, across all concurrent requests)
    Transfer rate:          555.85 [Kbytes/sec] received
    Connection Times (ms)
                  min  mean[+/-sd] median   max
    Connect:        3   19  41.3      5     250
    Processing:    10  485 274.7    439    3117
    Waiting:       10  484 273.4    439    3117
    Total:         47  503 274.9    445    3138
    Percentage of the requests served within a certain time (ms)
      50%    445
      66%    459
      75%    466
      80%    500
      90%    815
      95%   1157
      98%   1377
      99%   1592
     100%   3138 (longest request)



netty:
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
    Server Software:        netty
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

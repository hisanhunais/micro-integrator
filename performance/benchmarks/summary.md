# WSO2 Micro Integrator 4.0.0 Performance Test Results

During each release, we execute various automated performance test scenarios and publish the results.

| Test Scenarios | Description |
| --- | --- |
| Direct Proxy | Passthrough proxy service |
| CBR Proxy | Routing the message based on the content of the message body |
| XSLT Proxy | Having XSLT transformations in request and response paths |
| Direct API | Passthrough API service |
| CBR SOAP Header Proxy | Routing the message based on a SOAP header in the message payload |
| CBR Transport Header Proxy | Routing the message based on an HTTP header in the message |
| XSLT Enhanced Proxy | Having enhanced, Fast XSLT transformations in request and response paths |

Our test client is [Apache JMeter](https://jmeter.apache.org/index.html). We test each scenario for a fixed duration of
time. We split the test results into warmup and measurement parts and use the measurement part to compute the
performance metrics.

Test scenarios use a [Netty](https://netty.io/) based back-end service which echoes back any request
posted to it after a specified period of time.

We run the performance tests under different numbers of concurrent users, message sizes (payloads) and back-end service
delays.

The main performance metrics:

1. **Throughput**: The number of requests that the WSO2 Micro Integrator 4.0.0 processes during a specific time interval (e.g. per second).
2. **Response Time**: The end-to-end latency for an operation of invoking a service in WSO2 Micro Integrator 4.0.0 . The complete distribution of response times was recorded.

In addition to the above metrics, we measure the load average and several memory-related metrics.

The following are the test parameters.

| Test Parameter | Description | Values |
| --- | --- | --- |
| Scenario Name | The name of the test scenario. | Refer to the above table. |
| Heap Size | The amount of memory allocated to the application | 2G |
| Concurrent Users | The number of users accessing the application at the same time. | 100 |
| Message Size (Bytes) | The request payload size in Bytes. | 500, 1000, 10000, 100000 |
| Back-end Delay (ms) | The delay added by the Back-end service. | 0 |

The duration of each test is **360 seconds**. The warm-up period is **120 seconds**.
The measurement results are collected after the warm-up period.

The performance tests were executed on 1 AWS CloudFormation stack.


System information for WSO2 Micro Integrator 4.0.0 in 1st AWS CloudFormation stack.

| Class | Subclass | Description | Value |
| --- | --- | --- | --- |
| AWS | EC2 | AMI-ID | ami-0758a746e73c88fe3 |
| AWS | EC2 | Instance Type | c5.large |
| System | Processor | CPU(s) | 2 |
| System | Processor | Thread(s) per core | 2 |
| System | Processor | Core(s) per socket | 1 |
| System | Processor | Socket(s) | 1 |
| System | Processor | Model name | Intel(R) Xeon(R) Platinum 8275CL CPU @ 3.00GHz |
| System | Memory | BIOS | 64 KiB |
| System | Memory | System memory | 3813860 KiB |
| System | Storage | Block Device: nvme0n1 | 8G |
| Operating System | Distribution | Release | Ubuntu 18.04.5 LTS |
| Operating System | Distribution | Kernel | Linux ip-10-0-1-148 5.4.0-1047-aws #49~18.04.1-Ubuntu SMP Wed Apr 28 23:08:58 UTC 2021 x86_64 x86_64 x86_64 GNU/Linux |


The following are the measurements collected from each performance test conducted for a given combination of
test parameters.

| Measurement | Description |
| --- | --- |
| Error % | Percentage of requests with errors |
| Average Response Time (ms) | The average response time of a set of results |
| Standard Deviation of Response Time (ms) | The “Standard Deviation” of the response time. |
| 99th Percentile of Response Time (ms) | 99% of the requests took no more than this time. The remaining samples took at least as long as this |
| Throughput (Requests/sec) | The throughput measured in requests per second. |
| Average Memory Footprint After Full GC (M) | The average memory consumed by the application after a full garbage collection event. |

The following is the summary of performance test results collected for the measurement period.

|  Scenario Name | Heap Size | Concurrent Users | Message Size (Bytes) | Back-end Service Delay (ms) | Error % | Throughput (Requests/sec) | Average Response Time (ms) | Standard Deviation of Response Time (ms) | 99th Percentile of Response Time (ms) | WSO2 Micro Integrator 4.0.0 GC Throughput (%) | Average WSO2 Micro Integrator 4.0.0 Memory Footprint After Full GC (M) |
|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|
|  CBR Proxy | 2G | 100 | 500 | 0 | 0 | 3431.01 | 29.06 | 29.11 | 109 | N/A | N/A |
|  CBR Proxy | 2G | 100 | 1000 | 0 | 0 | 3069.26 | 32.5 | 39.93 | 116 | N/A | N/A |
|  CBR Proxy | 2G | 100 | 10000 | 0 | 0 | 1085.68 | 91.99 | 56.58 | 271 | N/A | N/A |
|  CBR Proxy | 2G | 100 | 100000 | 0 | 0 | 111.99 | 891.72 | 235.29 | 1679 | N/A | N/A |
|  CBR SOAP Header Proxy | 2G | 100 | 500 | 0 | 0 | 573.16 | 174.41 | 633.77 | 3167 | N/A | N/A |
|  CBR SOAP Header Proxy | 2G | 100 | 1000 | 0 | 0 | 253.09 | 395.04 | 1008.39 | 3343 | N/A | N/A |
|  CBR SOAP Header Proxy | 2G | 100 | 10000 | 0 | 0 | 209.42 | 477.4 | 1049.45 | 3295 | N/A | N/A |
|  CBR SOAP Header Proxy | 2G | 100 | 100000 | 0 | 0 | 164.71 | 606.85 | 515.34 | 3119 | N/A | N/A |
|  CBR Transport Header Proxy | 2G | 100 | 500 | 0 | 0 | 213.32 | 468.7 | 1009.75 | 3039 | N/A | N/A |
|  CBR Transport Header Proxy | 2G | 100 | 1000 | 0 | 0 | 95.53 | 1046.67 | 1441.3 | 3327 | N/A | N/A |
|  CBR Transport Header Proxy | 2G | 100 | 10000 | 0 | 0 | 99.85 | 1001.41 | 1372.01 | 3327 | N/A | N/A |
|  CBR Transport Header Proxy | 2G | 100 | 100000 | 0 | 0 | 1127.19 | 88.47 | 75.23 | 244 | N/A | N/A |
|  Direct API | 2G | 100 | 500 | 0 | 0 | 4152.84 | 24.01 | 35.91 | 110 | N/A | N/A |
|  Direct API | 2G | 100 | 1000 | 0 | 0 | 4132.46 | 24.13 | 41.42 | 110 | N/A | N/A |
|  Direct API | 2G | 100 | 10000 | 0 | 0 | 3383.21 | 29.46 | 60.11 | 116 | N/A | N/A |
|  Direct API | 2G | 100 | 100000 | 0 | 0 | 1284 | 77.63 | 28.72 | 166 | N/A | N/A |
|  Direct Proxy | 2G | 100 | 500 | 0 | 0 | 4273.5 | 23.32 | 34.06 | 105 | 91.25 | 229.164 |
|  Direct Proxy | 2G | 100 | 1000 | 0 | 0 | 4276.95 | 23.31 | 36.13 | 106 | N/A | N/A |
|  Direct Proxy | 2G | 100 | 10000 | 0 | 0 | 3653.9 | 27.27 | 32.26 | 111 | N/A | N/A |
|  Direct Proxy | 2G | 100 | 100000 | 0 | 0 | 1607.99 | 61.99 | 23.62 | 141 | N/A | N/A |
|  XSLT Enhanced Proxy | 2G | 100 | 500 | 0 | 100 | 0.67 | 120064 | 0 | 120319 | N/A | N/A |
|  XSLT Enhanced Proxy | 2G | 100 | 1000 | 0 | 100 | 0.67 | 120064 | 0 | 120319 | N/A | N/A |
|  XSLT Enhanced Proxy | 2G | 100 | 10000 | 0 | 0 | 542.49 | 184.24 | 70.37 | 365 | N/A | N/A |
|  XSLT Enhanced Proxy | 2G | 100 | 100000 | 0 | 0 | 79.16 | 1259.27 | 287.81 | 1935 | N/A | N/A |
|  XSLT Proxy | 2G | 100 | 500 | 0 | 0 | 1411.76 | 48.69 | 244.01 | 153 | N/A | N/A |
|  XSLT Proxy | 2G | 100 | 1000 | 0 | 0 | 1587.86 | 59.41 | 270.46 | 188 | N/A | N/A |
|  XSLT Proxy | 2G | 100 | 10000 | 0 | 0 | 365.11 | 273.77 | 151.6 | 707 | N/A | N/A |
|  XSLT Proxy | 2G | 100 | 100000 | 0 | 0 | 32.76 | 3029.44 | 541.57 | 4511 | N/A | N/A |

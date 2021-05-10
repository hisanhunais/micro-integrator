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
| Concurrent Users | The number of users accessing the application at the same time. | 200 |
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
| Operating System | Distribution | Kernel | Linux ip-10-0-1-175 5.4.0-1047-aws #49~18.04.1-Ubuntu SMP Wed Apr 28 23:08:58 UTC 2021 x86_64 x86_64 x86_64 GNU/Linux |


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
|  CBR Proxy | 2G | 200 | 500 | 0 | 0 | 3454.44 | 57.79 | 44.52 | 176 | N/A | N/A |
|  CBR Proxy | 2G | 200 | 1000 | 0 | 0 | 3089.65 | 64.6 | 53.79 | 193 | N/A | N/A |
|  CBR Proxy | 2G | 200 | 10000 | 0 | 0 | 1090.2 | 183.38 | 93.9 | 453 | N/A | N/A |
|  CBR Proxy | 2G | 200 | 100000 | 0 | 0 | 85.82 | 2318.41 | 890.44 | 4415 | N/A | N/A |
|  CBR SOAP Header Proxy | 2G | 200 | 500 | 0 | 0 | 499.5 | 400.28 | 947.51 | 3279 | N/A | N/A |
|  CBR SOAP Header Proxy | 2G | 200 | 1000 | 0 | 0 | 208.4 | 958.38 | 1457.75 | 3631 | N/A | N/A |
|  CBR SOAP Header Proxy | 2G | 200 | 10000 | 0 | 0 | 157.78 | 1267.04 | 1545.24 | 3711 | N/A | N/A |
|  CBR SOAP Header Proxy | 2G | 200 | 100000 | 0 | 0 | 62.75 | 3146.22 | 1658.92 | 7743 | N/A | N/A |
|  CBR Transport Header Proxy | 2G | 200 | 500 | 0 | 0 | 152.27 | 1313.2 | 1609.59 | 6047 | N/A | N/A |
|  CBR Transport Header Proxy | 2G | 200 | 1000 | 0 | 0 | 70.13 | 2828.78 | 2389.87 | 11839 | N/A | N/A |
|  CBR Transport Header Proxy | 2G | 200 | 10000 | 0 | 0 | 76.36 | 2587.96 | 1974.08 | 8895 | N/A | N/A |
|  CBR Transport Header Proxy | 2G | 200 | 100000 | 0 | 0 | 1099.44 | 181.58 | 123.17 | 365 | N/A | N/A |
|  Direct API | 2G | 200 | 500 | 0 | 0 | 4143.66 | 48.15 | 55.45 | 164 | N/A | N/A |
|  Direct API | 2G | 200 | 1000 | 0 | 0 | 4159.28 | 47.96 | 53.23 | 159 | N/A | N/A |
|  Direct API | 2G | 200 | 10000 | 0 | 0 | 3531.24 | 56.48 | 40.63 | 171 | N/A | N/A |
|  Direct API | 2G | 200 | 100000 | 0 | 0 | 1277.39 | 156.28 | 40.14 | 265 | N/A | N/A |
|  Direct Proxy | 2G | 200 | 500 | 0 | 0 | 4208.93 | 47.4 | 49.99 | 162 | 90.69 | 269.919 |
|  Direct Proxy | 2G | 200 | 1000 | 0 | 0 | 4290.51 | 46.5 | 54.52 | 150 | N/A | N/A |
|  Direct Proxy | 2G | 200 | 10000 | 0 | 0 | 3683.73 | 54.14 | 49.92 | 162 | N/A | N/A |
|  Direct Proxy | 2G | 200 | 100000 | 0 | 0 | 1538.73 | 129.69 | 39.37 | 233 | N/A | N/A |
|  XSLT Enhanced Proxy | 2G | 200 | 500 | 0 | 100 | 1.33 | 120064 | 0 | 120319 | N/A | N/A |
|  XSLT Enhanced Proxy | 2G | 200 | 1000 | 0 | 100 | 1.33 | 120064 | 0 | 120319 | N/A | N/A |
|  XSLT Enhanced Proxy | 2G | 200 | 10000 | 0 | 0 | 562.21 | 355.7 | 107.52 | 631 | N/A | N/A |
|  XSLT Enhanced Proxy | 2G | 200 | 100000 | 0 | 0 | 78.53 | 2532.39 | 383.87 | 3567 | N/A | N/A |
|  XSLT Proxy | 2G | 200 | 500 | 0 | 0 | 2027.27 | 98.45 | 61.02 | 281 | N/A | N/A |
|  XSLT Proxy | 2G | 200 | 1000 | 0 | 0 | 1693.15 | 117.72 | 65.23 | 311 | N/A | N/A |
|  XSLT Proxy | 2G | 200 | 10000 | 0 | 0 | 365.28 | 546.87 | 246.59 | 1255 | N/A | N/A |
|  XSLT Proxy | 2G | 200 | 100000 | 0 | 0 | 28.99 | 6777.25 | 1301.65 | 9535 | N/A | N/A |

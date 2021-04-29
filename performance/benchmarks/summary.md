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
| Concurrent Users | The number of users accessing the application at the same time. | 100, 200, 500, 1000 |
| Message Size (Bytes) | The request payload size in Bytes. | 500, 1000, 10000, 100000 |
| Back-end Delay (ms) | The delay added by the Back-end service. | 0 |

The duration of each test is **360 seconds**. The warm-up period is **120 seconds**.
The measurement results are collected after the warm-up period.

The performance tests were executed on 1 AWS CloudFormation stack.


System information for WSO2 Micro Integrator 4.0.0 in 1st AWS CloudFormation stack.

| Class | Subclass | Description | Value |
| --- | --- | --- | --- |
| AWS | EC2 | AMI-ID | ami-0747bdcabd34c712a |
| AWS | EC2 | Instance Type | c5.large |
| System | Processor | CPU(s) | 2 |
| System | Processor | Thread(s) per core | 2 |
| System | Processor | Core(s) per socket | 1 |
| System | Processor | Socket(s) | 1 |
| System | Processor | Model name | Intel(R) Xeon(R) Platinum 8124M CPU @ 3.00GHz |
| System | Memory | BIOS | 64 KiB |
| System | Memory | System memory | 3785188 KiB |
| System | Storage | Block Device: nvme0n1 | 8G |
| Operating System | Distribution | Release | Ubuntu 18.04.5 LTS |
| Operating System | Distribution | Kernel | Linux ip-10-0-1-247 5.4.0-1045-aws #47~18.04.1-Ubuntu SMP Tue Apr 13 15:58:14 UTC 2021 x86_64 x86_64 x86_64 GNU/Linux |


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
|  CBR Proxy | 2G | 100 | 500 | 0 | 0 | 710.2 | 140.71 | 532.66 | 2927 | N/A | N/A |
|  CBR Proxy | 2G | 100 | 1000 | 0 | 0 | 792.02 | 126.17 | 481.98 | 2863 | N/A | N/A |
|  CBR Proxy | 2G | 100 | 10000 | 0 | 0 | 892.92 | 111.87 | 96.74 | 341 | N/A | N/A |
|  CBR Proxy | 2G | 100 | 100000 | 0 | 0 | 100.15 | 995.92 | 272.82 | 2039 | N/A | N/A |
|  CBR Proxy | 2G | 200 | 500 | 0 | 0 | 364.47 | 548.52 | 1097.32 | 3279 | N/A | N/A |
|  CBR Proxy | 2G | 200 | 1000 | 0 | 0 | 552.02 | 362.17 | 859.21 | 3151 | N/A | N/A |
|  CBR Proxy | 2G | 200 | 10000 | 0 | 0 | 870.63 | 229.64 | 153.33 | 567 | N/A | N/A |
|  CBR Proxy | 2G | 200 | 100000 | 0 | 0 | 79.89 | 2491.21 | 863.12 | 4703 | N/A | N/A |
|  CBR Proxy | 2G | 500 | 500 | 0 | 0 | 231.47 | 2156.97 | 2065.43 | 9727 | N/A | N/A |
|  CBR Proxy | 2G | 500 | 1000 | 0 | 0 | 367.57 | 1359.74 | 1693.41 | 6431 | N/A | N/A |
|  CBR Proxy | 2G | 500 | 10000 | 0 | 0 | 787.37 | 634.46 | 271.86 | 1199 | N/A | N/A |
|  CBR Proxy | 2G | 500 | 100000 | 0 | 0 | 39.15 | 12343.38 | 3292.79 | 20095 | N/A | N/A |
|  CBR Proxy | 2G | 1000 | 500 | 0 | 0 | 178.51 | 5580.84 | 4199.06 | 21887 | N/A | N/A |
|  CBR Proxy | 2G | 1000 | 1000 | 0 | 0 | 227.95 | 4360.72 | 4018.42 | 19583 | N/A | N/A |
|  CBR Proxy | 2G | 1000 | 10000 | 0 | 0 | 552.46 | 1804.83 | 985.94 | 4319 | N/A | N/A |
|  CBR Proxy | 2G | 1000 | 100000 | 0 | 100 | 4.52 | 120064 | 0 | 120319 | N/A | N/A |
|  Direct Proxy | 2G | 100 | 500 | 0 | 0 | 4042.59 | 24.65 | 39.73 | 110 | 91.55 | 272.148 |
|  Direct Proxy | 2G | 100 | 1000 | 0 | 0 | 4095.63 | 24.32 | 39.91 | 108 | N/A | N/A |
|  Direct Proxy | 2G | 100 | 10000 | 0 | 0 | 3484.76 | 28.59 | 31.03 | 114 | N/A | N/A |
|  Direct Proxy | 2G | 100 | 100000 | 0 | 0 | 1526.96 | 65.28 | 27.17 | 147 | N/A | N/A |
|  Direct Proxy | 2G | 200 | 500 | 0 | 0 | 4177.88 | 47.75 | 52.85 | 156 | N/A | N/A |
|  Direct Proxy | 2G | 200 | 1000 | 0 | 0 | 4138.52 | 48.21 | 58.99 | 157 | N/A | N/A |
|  Direct Proxy | 2G | 200 | 10000 | 0 | 0 | 3558.28 | 55.99 | 39.15 | 164 | N/A | N/A |
|  Direct Proxy | 2G | 200 | 100000 | 0 | 0 | 1450.84 | 137.55 | 42.07 | 248 | N/A | N/A |
|  Direct Proxy | 2G | 500 | 500 | 0 | 0 | 4143.75 | 120.49 | 91.61 | 307 | N/A | N/A |
|  Direct Proxy | 2G | 500 | 1000 | 0 | 0 | 4125.67 | 121.05 | 94.18 | 319 | N/A | N/A |
|  Direct Proxy | 2G | 500 | 10000 | 0 | 0 | 1705.77 | 292.89 | 655.53 | 3375 | N/A | N/A |
|  Direct Proxy | 2G | 500 | 100000 | 0 | 0 | 1138.19 | 439.03 | 102.43 | 695 | N/A | N/A |
|  Direct Proxy | 2G | 1000 | 500 | 0 | 0 | 102.6 | 9486.42 | 8050.22 | 38399 | N/A | N/A |
|  Direct Proxy | 2G | 1000 | 1000 | 0 | 0.02 | 75.97 | 9787.47 | 8977.07 | 42495 | N/A | N/A |
|  Direct Proxy | 2G | 1000 | 10000 | 0 | 0 | 229.36 | 4293.01 | 3431.74 | 15743 | N/A | N/A |
|  Direct Proxy | 2G | 1000 | 100000 | 0 | 0 | 1093.53 | 911.45 | 162.96 | 1311 | N/A | N/A |

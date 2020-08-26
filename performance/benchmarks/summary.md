# WSO2 Micro Integrator 1.2.0 Performance Test Results

During each release, we execute various automated performance test scenarios and publish the results.

| Test Scenarios | Description |
| --- | --- |
| XSLT Enhanced Proxy | Having enhanced, Fast XSLT transformations in request and response paths |

Our test client is [Apache JMeter](https://jmeter.apache.org/index.html). We test each scenario for a fixed duration of
time. We split the test results into warmup and measurement parts and use the measurement part to compute the
performance metrics.

Test scenarios use a [Netty](https://netty.io/) based back-end service which echoes back any request
posted to it after a specified period of time.

We run the performance tests under different numbers of concurrent users, message sizes (payloads) and back-end service
delays.

The main performance metrics:

1. **Throughput**: The number of requests that the WSO2 Micro Integrator 1.2.0 processes during a specific time interval (e.g. per second).
2. **Response Time**: The end-to-end latency for an operation of invoking a service in WSO2 Micro Integrator 1.2.0 . The complete distribution of response times was recorded.

In addition to the above metrics, we measure the load average and several memory-related metrics.

The following are the test parameters.

| Test Parameter | Description | Values |
| --- | --- | --- |
| Scenario Name | The name of the test scenario. | Refer to the above table. |
| Heap Size | The amount of memory allocated to the application | 2G |
| Concurrent Users | The number of users accessing the application at the same time. | 100, 200 |
| Message Size (Bytes) | The request payload size in Bytes. | 500, 1000, 10000, 100000, 200000, 500000, 1000000 |
| Back-end Delay (ms) | The delay added by the Back-end service. | 0 |

The duration of each test is **900 seconds**. The warm-up period is **300 seconds**.
The measurement results are collected after the warm-up period.

The performance tests were executed on 1 AWS CloudFormation stack.


System information for WSO2 Micro Integrator 1.2.0 in 1st AWS CloudFormation stack.

| Class | Subclass | Description | Value |
| --- | --- | --- | --- |
| AWS | EC2 | AMI-ID | ami-0bcc094591f354be2 |
| AWS | EC2 | Instance Type | c5.large |
| System | Processor | CPU(s) | 2 |
| System | Processor | Thread(s) per core | 2 |
| System | Processor | Core(s) per socket | 1 |
| System | Processor | Socket(s) | 1 |
| System | Processor | Model name | Intel(R) Xeon(R) Platinum 8124M CPU @ 3.00GHz |
| System | Memory | BIOS | 64 KiB |
| System | Memory | System memory | 3785216 KiB |
| System | Storage | Block Device: nvme0n1 | 8G |
| Operating System | Distribution | Release | Ubuntu 18.04.5 LTS |
| Operating System | Distribution | Kernel | Linux ip-10-0-1-187 5.3.0-1032-aws #34~18.04.2-Ubuntu SMP Fri Jul 24 10:06:28 UTC 2020 x86_64 x86_64 x86_64 GNU/Linux |


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

|  Scenario Name | Heap Size | Concurrent Users | Message Size (Bytes) | Back-end Service Delay (ms) | Error % | Throughput (Requests/sec) | Average Response Time (ms) | Standard Deviation of Response Time (ms) | 99th Percentile of Response Time (ms) | WSO2 Micro Integrator 1.2.0 GC Throughput (%) | Average WSO2 Micro Integrator 1.2.0 Memory Footprint After Full GC (M) |
|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|
|  XSLT Enhanced Proxy | 2G | 100 | 500 | 0 | 0 | 2812.06 | 35.48 | 41.41 | 146 | 93.32 | 231.029 |
|  XSLT Enhanced Proxy | 2G | 100 | 1000 | 0 | 0 | 2573.76 | 38.77 | 31.75 | 157 | N/A | N/A |
|  XSLT Enhanced Proxy | 2G | 100 | 10000 | 0 | 0 | 585.5 | 170.71 | 62.67 | 335 | N/A | N/A |
|  XSLT Enhanced Proxy | 2G | 100 | 100000 | 0 | 0 | 76.59 | 1303.78 | 281.31 | 1975 | N/A | N/A |
|  XSLT Enhanced Proxy | 2G | 100 | 200000 | 0 | 0 | 38.55 | 2583.98 | 520.77 | 3775 | N/A | N/A |
|  XSLT Enhanced Proxy | 2G | 100 | 500000 | 0 | 0 | 15.14 | 6567.61 | 1067.73 | 9023 | N/A | N/A |
|  XSLT Enhanced Proxy | 2G | 100 | 1000000 | 0 | 100 | 0.76 | 120064 | 0 | 120319 | N/A | N/A |
|  XSLT Enhanced Proxy | 2G | 200 | 500 | 0 | 0 | 2789.58 | 71.6 | 70.06 | 273 | N/A | N/A |
|  XSLT Enhanced Proxy | 2G | 200 | 1000 | 0 | 0 | 2538.81 | 78.68 | 68.43 | 303 | N/A | N/A |
|  XSLT Enhanced Proxy | 2G | 200 | 10000 | 0 | 0 | 583.42 | 343.01 | 108.85 | 619 | N/A | N/A |
|  XSLT Enhanced Proxy | 2G | 200 | 100000 | 0 | 0 | 74.06 | 2690.7 | 422.35 | 3775 | N/A | N/A |
|  XSLT Enhanced Proxy | 2G | 200 | 200000 | 0 | 0 | 36.87 | 5390.21 | 818.19 | 7359 | N/A | N/A |
|  XSLT Enhanced Proxy | 2G | 200 | 500000 | 0 | 0 | 14.48 | 13647.56 | 2093.64 | 18303 | N/A | N/A |
|  XSLT Enhanced Proxy | 2G | 200 | 1000000 | 0 | 100 | 1.51 | 120064 | 0 | 120319 | N/A | N/A |

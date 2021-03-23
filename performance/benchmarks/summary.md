# WSO2 Micro Integrator 4.0.0-alpha Performance Test Results

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

1. **Throughput**: The number of requests that the WSO2 Micro Integrator 4.0.0-alpha processes during a specific time interval (e.g. per second).
2. **Response Time**: The end-to-end latency for an operation of invoking a service in WSO2 Micro Integrator 4.0.0-alpha . The complete distribution of response times was recorded.

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


System information for WSO2 Micro Integrator 4.0.0-alpha in 1st AWS CloudFormation stack.

| Class | Subclass | Description | Value |
| --- | --- | --- | --- |
| AWS | EC2 | AMI-ID | ami-013f17f36f8b1fefb |
| AWS | EC2 | Instance Type | c5.large |
| System | Processor | CPU(s) | 2 |
| System | Processor | Thread(s) per core | 2 |
| System | Processor | Core(s) per socket | 1 |
| System | Processor | Socket(s) | 1 |
| System | Processor | Model name | Intel(R) Xeon(R) Platinum 8275CL CPU @ 3.00GHz |
| System | Memory | BIOS | 64 KiB |
| System | Memory | System memory | 3813908 KiB |
| System | Storage | Block Device: nvme0n1 | 8G |
| Operating System | Distribution | Release | Ubuntu 18.04.5 LTS |
| Operating System | Distribution | Kernel | Linux ip-10-0-1-140 5.4.0-1038-aws #40~18.04.1-Ubuntu SMP Sat Feb 6 01:56:56 UTC 2021 x86_64 x86_64 x86_64 GNU/Linux |


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

|  Scenario Name | Heap Size | Concurrent Users | Message Size (Bytes) | Back-end Service Delay (ms) | Error % | Throughput (Requests/sec) | Average Response Time (ms) | Standard Deviation of Response Time (ms) | 99th Percentile of Response Time (ms) | WSO2 Micro Integrator 4.0.0-alpha GC Throughput (%) | Average WSO2 Micro Integrator 4.0.0-alpha Memory Footprint After Full GC (M) |
|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|
|  XSLT Enhanced Proxy | 2G | 100 | 500 | 0 | 0 | 2183.54 | 45.5 | 44.74 | 185 | 95.26 | 146.784 |
|  XSLT Enhanced Proxy | 2G | 100 | 1000 | 0 | 0 | 1995.32 | 50.01 | 178.79 | 199 | N/A | N/A |
|  XSLT Enhanced Proxy | 2G | 100 | 10000 | 0 | 0 | 614.92 | 162.47 | 58.27 | 311 | N/A | N/A |
|  XSLT Enhanced Proxy | 2G | 100 | 100000 | 0 | 0 | 82.23 | 1211.79 | 267.58 | 1831 | N/A | N/A |
|  XSLT Enhanced Proxy | 2G | 200 | 500 | 0 | 0 | 2248.66 | 88.81 | 66.96 | 313 | N/A | N/A |
|  XSLT Enhanced Proxy | 2G | 200 | 1000 | 0 | 0 | 1930.16 | 99 | 185.28 | 333 | N/A | N/A |
|  XSLT Enhanced Proxy | 2G | 200 | 10000 | 0 | 0 | 629.43 | 317.58 | 99.72 | 575 | N/A | N/A |
|  XSLT Enhanced Proxy | 2G | 200 | 100000 | 0 | 0 | 81.09 | 2448.84 | 385.38 | 3503 | N/A | N/A |
|  XSLT Enhanced Proxy | 2G | 500 | 500 | 0 | 0 | 2249.55 | 222.13 | 117.58 | 619 | N/A | N/A |
|  XSLT Enhanced Proxy | 2G | 500 | 1000 | 0 | 0 | 2009.8 | 248.62 | 124.66 | 667 | N/A | N/A |
|  XSLT Enhanced Proxy | 2G | 500 | 10000 | 0 | 0 | 624.27 | 799.51 | 204.66 | 1343 | N/A | N/A |
|  XSLT Enhanced Proxy | 2G | 500 | 100000 | 0 | 0 | 77.04 | 6361.63 | 557.37 | 7775 | N/A | N/A |
|  XSLT Enhanced Proxy | 2G | 1000 | 500 | 0 | 0 | 2173.78 | 459.65 | 187 | 1063 | N/A | N/A |
|  XSLT Enhanced Proxy | 2G | 1000 | 1000 | 0 | 0 | 1952.31 | 511.76 | 194.84 | 1103 | N/A | N/A |
|  XSLT Enhanced Proxy | 2G | 1000 | 10000 | 0 | 0 | 601.98 | 1653.19 | 316.85 | 2527 | N/A | N/A |
|  XSLT Enhanced Proxy | 2G | 1000 | 100000 | 0 | 0 | 74.9 | 12859.93 | 750.04 | 14655 | N/A | N/A |

# WSO2 Micro Integrator 4.0.0-alpha Performance Test Results

During each release, we execute various automated performance test scenarios and publish the results.

| Test Scenarios | Description |
| --- | --- |
| XSLT Proxy | Having XSLT transformations in request and response paths |
| Direct API | Passthrough API service |

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
| AWS | EC2 | AMI-ID | ami-03eaf3b9c3367e75c |
| AWS | EC2 | Instance Type | c5.large |
| System | Processor | CPU(s) | 2 |
| System | Processor | Thread(s) per core | 2 |
| System | Processor | Core(s) per socket | 1 |
| System | Processor | Socket(s) | 1 |
| System | Processor | Model name | Intel(R) Xeon(R) Platinum 8124M CPU @ 3.00GHz |
| System | Memory | BIOS | 64 KiB |
| System | Memory | System memory | 3785200 KiB |
| System | Storage | Block Device: nvme0n1 | 8G |
| Operating System | Distribution | Release | Ubuntu 18.04.5 LTS |
| Operating System | Distribution | Kernel | Linux ip-10-0-1-17 5.4.0-1041-aws #43~18.04.1-Ubuntu SMP Sat Mar 20 15:47:52 UTC 2021 x86_64 x86_64 x86_64 GNU/Linux |


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
|  Direct API | 2G | 100 | 500 | 0 | 0 | 3396.72 | 29.34 | 40.89 | 205 | N/A | N/A |
|  Direct API | 2G | 100 | 1000 | 0 | 0 | 3851.83 | 25.86 | 38.04 | 148 | N/A | N/A |
|  Direct API | 2G | 100 | 10000 | 0 | 0 | 3478.46 | 28.63 | 29.47 | 118 | N/A | N/A |
|  Direct API | 2G | 100 | 100000 | 0 | 0 | 1507.53 | 66.11 | 28.08 | 156 | N/A | N/A |
|  Direct API | 2G | 200 | 500 | 0 | 0 | 4149.47 | 48.08 | 61.23 | 165 | N/A | N/A |
|  Direct API | 2G | 200 | 1000 | 0 | 0 | 4149.48 | 48.06 | 56.68 | 161 | N/A | N/A |
|  Direct API | 2G | 200 | 10000 | 0 | 0 | 1549.25 | 128.96 | 453.26 | 3151 | N/A | N/A |
|  XSLT Proxy | 2G | 100 | 500 | 0 | 0 | 1956.28 | 50.99 | 40.49 | 167 | 94.38 | 162.405 |
|  XSLT Proxy | 2G | 100 | 1000 | 0 | 0 | 1686.52 | 59.16 | 39.5 | 179 | N/A | N/A |
|  XSLT Proxy | 2G | 100 | 10000 | 0 | 0 | 359.57 | 277.87 | 152.09 | 715 | N/A | N/A |
|  XSLT Proxy | 2G | 100 | 100000 | 0 | 0 | 32.17 | 3084.89 | 575.13 | 4703 | N/A | N/A |
|  XSLT Proxy | 2G | 200 | 500 | 0 | 0 | 2097.03 | 95.17 | 55.97 | 250 | N/A | N/A |
|  XSLT Proxy | 2G | 200 | 1000 | 0 | 0 | 1675.91 | 119.16 | 68.28 | 307 | N/A | N/A |
|  XSLT Proxy | 2G | 200 | 10000 | 0 | 0 | 351.98 | 567.85 | 255.17 | 1295 | N/A | N/A |
|  XSLT Proxy | 2G | 200 | 100000 | 0 | 0 | 27 | 7234.9 | 1373.03 | 10175 | N/A | N/A |
|  XSLT Proxy | 2G | 500 | 500 | 0 | 0 | 2002.61 | 249.53 | 118.89 | 559 | N/A | N/A |
|  XSLT Proxy | 2G | 500 | 1000 | 0 | 0 | 1639.94 | 304.75 | 140.56 | 683 | N/A | N/A |
|  XSLT Proxy | 2G | 500 | 10000 | 0 | 0 | 316.68 | 1573.13 | 414.86 | 2767 | N/A | N/A |
|  XSLT Proxy | 2G | 500 | 100000 | 0 | 0 | 15.94 | 29028.66 | 4886.85 | 41727 | N/A | N/A |
|  XSLT Proxy | 2G | 1000 | 500 | 0 | 0 | 1743.87 | 572.66 | 194.09 | 1095 | N/A | N/A |
|  XSLT Proxy | 2G | 1000 | 1000 | 0 | 0 | 1484.47 | 672.73 | 230.87 | 1351 | N/A | N/A |
|  XSLT Proxy | 2G | 1000 | 10000 | 0 | 0 | 275.06 | 3598.13 | 902.08 | 5695 | N/A | N/A |
|  XSLT Proxy | 2G | 1000 | 100000 | 0 | 82.93 | 5.42 | 116773.27 | 12576.25 | 156671 | N/A | N/A |

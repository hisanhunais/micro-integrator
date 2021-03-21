# WSO2 Micro Integrator 4.0.0-alpha Performance Test Results

During each release, we execute various automated performance test scenarios and publish the results.

| Test Scenarios | Description |
| --- | --- |
| XSLT Proxy | Having XSLT transformations in request and response paths |

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
| System | Processor | Model name | Intel(R) Xeon(R) Platinum 8124M CPU @ 3.00GHz |
| System | Memory | BIOS | 64 KiB |
| System | Memory | System memory | 3785236 KiB |
| System | Storage | Block Device: nvme0n1 | 8G |
| Operating System | Distribution | Release | Ubuntu 18.04.5 LTS |
| Operating System | Distribution | Kernel | Linux ip-10-0-1-193 5.4.0-1038-aws #40~18.04.1-Ubuntu SMP Sat Feb 6 01:56:56 UTC 2021 x86_64 x86_64 x86_64 GNU/Linux |


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
|  XSLT Proxy | 2G | 100 | 500 | 0 | 0 | 1701.53 | 53.59 | 184.34 | 175 | 94.67 | 156.019 |
|  XSLT Proxy | 2G | 100 | 1000 | 0 | 0 | 1579.87 | 63.05 | 200.04 | 199 | N/A | N/A |
|  XSLT Proxy | 2G | 100 | 10000 | 0 | 0 | 281.82 | 294.29 | 448.86 | 755 | N/A | N/A |
|  XSLT Proxy | 2G | 100 | 100000 | 0 | 0 | 30.68 | 3239.1 | 582.18 | 4799 | N/A | N/A |
|  XSLT Proxy | 2G | 200 | 500 | 0 | 0 | 1960.04 | 101.78 | 66.99 | 287 | N/A | N/A |
|  XSLT Proxy | 2G | 200 | 1000 | 0 | 0 | 1573.71 | 126.9 | 75.98 | 349 | N/A | N/A |
|  XSLT Proxy | 2G | 200 | 10000 | 0 | 0 | 334.06 | 598.01 | 272.8 | 1375 | N/A | N/A |
|  XSLT Proxy | 2G | 200 | 100000 | 0 | 0 | 26.69 | 7370.54 | 1382.91 | 10239 | N/A | N/A |
|  XSLT Proxy | 2G | 500 | 500 | 0 | 0 | 1898.93 | 263.16 | 125.88 | 627 | N/A | N/A |
|  XSLT Proxy | 2G | 500 | 1000 | 0 | 0 | 1546.48 | 323.17 | 148.66 | 783 | N/A | N/A |
|  XSLT Proxy | 2G | 500 | 10000 | 0 | 0 | 297.01 | 1675.52 | 510.94 | 3071 | N/A | N/A |
|  XSLT Proxy | 2G | 500 | 100000 | 0 | 0 | 15.43 | 30237.47 | 5200.5 | 43263 | N/A | N/A |
|  XSLT Proxy | 2G | 1000 | 500 | 0 | 0 | 1618.71 | 616.84 | 228.14 | 1311 | N/A | N/A |
|  XSLT Proxy | 2G | 1000 | 1000 | 0 | 0 | 1421 | 702.66 | 264.85 | 1551 | N/A | N/A |
|  XSLT Proxy | 2G | 1000 | 10000 | 0 | 0 | 264.24 | 3749.52 | 954.54 | 6079 | N/A | N/A |
|  XSLT Proxy | 2G | 1000 | 100000 | 0 | 82.9 | 5.98 | 117564.34 | 12037.37 | 141311 | N/A | N/A |

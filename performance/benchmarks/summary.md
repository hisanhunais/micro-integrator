# WSO2 Micro Integrator 4.0.0-beta Performance Test Results

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

1. **Throughput**: The number of requests that the WSO2 Micro Integrator 4.0.0-beta processes during a specific time interval (e.g. per second).
2. **Response Time**: The end-to-end latency for an operation of invoking a service in WSO2 Micro Integrator 4.0.0-beta . The complete distribution of response times was recorded.

In addition to the above metrics, we measure the load average and several memory-related metrics.

The following are the test parameters.

| Test Parameter | Description | Values |
| --- | --- | --- |
| Scenario Name | The name of the test scenario. | Refer to the above table. |
| Heap Size | The amount of memory allocated to the application | 1G |
| Concurrent Users | The number of users accessing the application at the same time. | 100, 200, 500, 1000 |
| Message Size (Bytes) | The request payload size in Bytes. | 500, 1000, 10000, 100000 |
| Back-end Delay (ms) | The delay added by the Back-end service. | 0 |

The duration of each test is **360 seconds**. The warm-up period is **120 seconds**.
The measurement results are collected after the warm-up period.

The performance tests were executed on 1 AWS CloudFormation stack.


System information for WSO2 Micro Integrator 4.0.0-beta in 1st AWS CloudFormation stack.

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
| System | Memory | System memory | 3785192 KiB |
| System | Storage | Block Device: nvme0n1 | 8G |
| Operating System | Distribution | Release | Ubuntu 18.04.5 LTS |
| Operating System | Distribution | Kernel | Linux ip-10-0-1-31 5.4.0-1041-aws #43~18.04.1-Ubuntu SMP Sat Mar 20 15:47:52 UTC 2021 x86_64 x86_64 x86_64 GNU/Linux |


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

|  Scenario Name | Heap Size | Concurrent Users | Message Size (Bytes) | Back-end Service Delay (ms) | Error % | Throughput (Requests/sec) | Average Response Time (ms) | Standard Deviation of Response Time (ms) | 99th Percentile of Response Time (ms) | WSO2 Micro Integrator 4.0.0-beta GC Throughput (%) | Average WSO2 Micro Integrator 4.0.0-beta Memory Footprint After Full GC (M) |
|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|
|  XSLT Proxy | 1G | 100 | 500 | 0 | 0 | 1494.12 | 51.18 | 181.47 | 164 | 92.68 | 197.246 |
|  XSLT Proxy | 1G | 100 | 1000 | 0 | 0 | 1613.07 | 61.64 | 49.13 | 191 | N/A | N/A |
|  XSLT Proxy | 1G | 100 | 10000 | 0 | 0 | 347.02 | 287.67 | 157.82 | 751 | N/A | N/A |
|  XSLT Proxy | 1G | 100 | 100000 | 0 | 0 | 25.6 | 3874.59 | 664.09 | 5215 | N/A | N/A |
|  XSLT Proxy | 1G | 200 | 500 | 0 | 0 | 1926.43 | 103.69 | 80.91 | 295 | N/A | N/A |
|  XSLT Proxy | 1G | 200 | 1000 | 0 | 0 | 1596.21 | 125.13 | 79.38 | 343 | N/A | N/A |
|  XSLT Proxy | 1G | 200 | 10000 | 0 | 0 | 317.93 | 628.02 | 306.4 | 1519 | N/A | N/A |
|  XSLT Proxy | 1G | 200 | 100000 | 0 | 0 | 18.35 | 10579.46 | 1675.44 | 14143 | N/A | N/A |
|  XSLT Proxy | 1G | 500 | 500 | 0 | 0 | 1761.01 | 283.77 | 174.11 | 1167 | N/A | N/A |
|  XSLT Proxy | 1G | 500 | 1000 | 0 | 0 | 1447.22 | 345.34 | 191.58 | 1215 | N/A | N/A |
|  XSLT Proxy | 1G | 500 | 10000 | 0 | 0 | 258.38 | 1926.8 | 685.76 | 3679 | N/A | N/A |
|  XSLT Proxy | 1G | 500 | 100000 | 0 | 100 | 2.59 | 122132.23 | 13539.25 | 231423 | N/A | N/A |

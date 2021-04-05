# WSO2 Micro Integrator 4.0.0-beta Performance Test Results

During each release, we execute various automated performance test scenarios and publish the results.

| Test Scenarios | Description |
| --- | --- |
| Direct API | Passthrough API service |

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
| Heap Size | The amount of memory allocated to the application | 2G |
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
| System | Memory | System memory | 3785200 KiB |
| System | Storage | Block Device: nvme0n1 | 8G |
| Operating System | Distribution | Release | Ubuntu 18.04.5 LTS |
| Operating System | Distribution | Kernel | Linux ip-10-0-1-13 5.4.0-1041-aws #43~18.04.1-Ubuntu SMP Sat Mar 20 15:47:52 UTC 2021 x86_64 x86_64 x86_64 GNU/Linux |


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
|  Direct API | 2G | 100 | 500 | 0 | 0 | 3784.99 | 26.33 | 31.8 | 119 | 92.97 | 170.106 |
|  Direct API | 2G | 100 | 1000 | 0 | 0 | 3829.26 | 26.02 | 24.54 | 117 | N/A | N/A |
|  Direct API | 2G | 100 | 10000 | 0 | 0 | 3232.59 | 30.83 | 38.18 | 124 | N/A | N/A |
|  Direct API | 2G | 100 | 100000 | 0 | 0 | 1449.04 | 68.8 | 35.05 | 154 | N/A | N/A |
|  Direct API | 2G | 200 | 500 | 0 | 0 | 3872.87 | 51.5 | 51.06 | 188 | N/A | N/A |
|  Direct API | 2G | 200 | 1000 | 0 | 0 | 3869.83 | 51.57 | 51.89 | 186 | N/A | N/A |
|  Direct API | 2G | 200 | 10000 | 0 | 0 | 3263.45 | 61.13 | 55.64 | 189 | N/A | N/A |
|  Direct API | 2G | 200 | 100000 | 0 | 0 | 1404.44 | 142.09 | 42.02 | 259 | N/A | N/A |
|  Direct API | 2G | 500 | 500 | 0 | 0 | 3836.61 | 130.13 | 88.1 | 375 | N/A | N/A |
|  Direct API | 2G | 500 | 1000 | 0 | 0 | 3837.44 | 130.13 | 85.3 | 359 | N/A | N/A |
|  Direct API | 2G | 500 | 10000 | 0 | 0 | 3252.85 | 153.51 | 91.27 | 363 | N/A | N/A |
|  Direct API | 2G | 500 | 100000 | 0 | 0 | 1301.2 | 384.07 | 81.53 | 607 | N/A | N/A |
|  Direct API | 2G | 1000 | 500 | 0 | 0 | 2145.75 | 463.96 | 727.17 | 3775 | N/A | N/A |

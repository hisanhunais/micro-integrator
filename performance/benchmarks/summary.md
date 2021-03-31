# WSO2 Micro Integrator 4.0.0-alpha Performance Test Results

During each release, we execute various automated performance test scenarios and publish the results.

| Test Scenarios | Description |
| --- | --- |
| Direct HTTPS API | Passthrough API HTTPS service |

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
| System | Processor | Model name | Intel(R) Xeon(R) Platinum 8275CL CPU @ 3.00GHz |
| System | Memory | BIOS | 64 KiB |
| System | Memory | System memory | 3813864 KiB |
| System | Storage | Block Device: nvme0n1 | 8G |
| Operating System | Distribution | Release | Ubuntu 18.04.5 LTS |
| Operating System | Distribution | Kernel | Linux ip-10-0-1-236 5.4.0-1041-aws #43~18.04.1-Ubuntu SMP Sat Mar 20 15:47:52 UTC 2021 x86_64 x86_64 x86_64 GNU/Linux |


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
|  Direct HTTPS API | 2G | 100 | 500 | 0 | 0 | 3810.74 | 26.15 | 27.2 | 109 | 93.24 | 194.776 |
|  Direct HTTPS API | 2G | 100 | 1000 | 0 | 0 | 3728.09 | 26.73 | 24.05 | 106 | N/A | N/A |
|  Direct HTTPS API | 2G | 100 | 10000 | 0 | 0 | 2278.76 | 43.78 | 28.99 | 117 | N/A | N/A |
|  Direct HTTPS API | 2G | 100 | 100000 | 0 | 0 | 466.42 | 214.15 | 26.33 | 297 | N/A | N/A |
|  Direct HTTPS API | 2G | 200 | 500 | 0 | 0 | 3886.53 | 51.36 | 49.89 | 159 | N/A | N/A |
|  Direct HTTPS API | 2G | 200 | 1000 | 0 | 0 | 3767.89 | 52.97 | 36.62 | 159 | N/A | N/A |
|  Direct HTTPS API | 2G | 200 | 10000 | 0 | 0 | 2251.16 | 88.7 | 40.97 | 186 | N/A | N/A |
|  Direct HTTPS API | 2G | 200 | 100000 | 0 | 0 | 452.61 | 441.71 | 44.27 | 559 | N/A | N/A |
|  Direct HTTPS API | 2G | 500 | 500 | 0 | 0 | 3824.58 | 130.53 | 94.61 | 321 | N/A | N/A |
|  Direct HTTPS API | 2G | 500 | 1000 | 0 | 0 | 3720.44 | 134.21 | 85.96 | 327 | N/A | N/A |
|  Direct HTTPS API | 2G | 500 | 10000 | 0 | 0 | 2224.62 | 224.5 | 76.36 | 385 | N/A | N/A |
|  Direct HTTPS API | 2G | 500 | 100000 | 0 | 0 | 440.98 | 1130.85 | 83.52 | 1335 | N/A | N/A |
|  Direct HTTPS API | 2G | 1000 | 500 | 0 | 0 | 3804.32 | 262.62 | 136.88 | 575 | N/A | N/A |
|  Direct HTTPS API | 2G | 1000 | 1000 | 0 | 0 | 3709.14 | 269.26 | 122.33 | 575 | N/A | N/A |
|  Direct HTTPS API | 2G | 1000 | 10000 | 0 | 0 | 1828.04 | 546.36 | 122.29 | 839 | N/A | N/A |

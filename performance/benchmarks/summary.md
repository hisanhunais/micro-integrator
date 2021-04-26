# WSO2 Micro Integrator 4.0.0 Performance Test Results

During each release, we execute various automated performance test scenarios and publish the results.

| Test Scenarios | Description |
| --- | --- |
| Direct Proxy | Passthrough proxy service |
| Direct API | Passthrough API service |
| CBR Transport Header Proxy | Routing the message based on an HTTP header in the message |

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
| Concurrent Users | The number of users accessing the application at the same time. | 1000 |
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
| System | Memory | System memory | 3785196 KiB |
| System | Storage | Block Device: nvme0n1 | 8G |
| Operating System | Distribution | Release | Ubuntu 18.04.5 LTS |
| Operating System | Distribution | Kernel | Linux ip-10-0-1-116 5.4.0-1045-aws #47~18.04.1-Ubuntu SMP Tue Apr 13 15:58:14 UTC 2021 x86_64 x86_64 x86_64 GNU/Linux |


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
|  CBR Transport Header Proxy | 2G | 1000 | 500 | 0 | 0 | 4031.34 | 247.87 | 157.3 | 571 | N/A | N/A |
|  CBR Transport Header Proxy | 2G | 1000 | 1000 | 0 | 0 | 4007.81 | 249.15 | 181.46 | 575 | N/A | N/A |
|  CBR Transport Header Proxy | 2G | 1000 | 10000 | 0 | 0 | 3267.19 | 304.22 | 198.82 | 595 | N/A | N/A |
|  Direct API | 2G | 1000 | 500 | 0 | 0 | 4026.45 | 248.21 | 140.47 | 551 | N/A | N/A |
|  Direct API | 2G | 1000 | 1000 | 0 | 0 | 4020.36 | 248.48 | 146.52 | 575 | N/A | N/A |
|  Direct API | 2G | 1000 | 10000 | 0 | 0 | 3366.19 | 296.68 | 153.81 | 599 | N/A | N/A |
|  Direct API | 2G | 1000 | 100000 | 0 | 0 | 1296.99 | 769.17 | 129.04 | 1135 | N/A | N/A |
|  Direct Proxy | 2G | 1000 | 500 | 0 | 0 | 3991.26 | 250.21 | 181.16 | 579 | 89.46 | 318.866 |
|  Direct Proxy | 2G | 1000 | 1000 | 0 | 0 | 4073.85 | 245.25 | 167.18 | 555 | N/A | N/A |
|  Direct Proxy | 2G | 1000 | 10000 | 0 | 0 | 3453.64 | 289.44 | 136.76 | 579 | N/A | N/A |
|  Direct Proxy | 2G | 1000 | 100000 | 0 | 0 | 1313.46 | 759.84 | 123.36 | 1103 | N/A | N/A |

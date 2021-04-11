# WSO2 Micro Integrator 4.0.0-beta Performance Test Results

During each release, we execute various automated performance test scenarios and publish the results.

| Test Scenarios | Description |
| --- | --- |
| CBR Proxy | Routing the message based on the content of the message body |

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
| System | Memory | System memory | 3785192 KiB |
| System | Storage | Block Device: nvme0n1 | 8G |
| Operating System | Distribution | Release | Ubuntu 18.04.5 LTS |
| Operating System | Distribution | Kernel | Linux ip-10-0-1-8 5.4.0-1041-aws #43~18.04.1-Ubuntu SMP Sat Mar 20 15:47:52 UTC 2021 x86_64 x86_64 x86_64 GNU/Linux |


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
|  CBR Proxy | 2G | 100 | 500 | 0 | 0 | 3240.65 | 30.75 | 38.09 | 117 | 93.67 | 200.118 |
|  CBR Proxy | 2G | 100 | 1000 | 0 | 0 | 2958.82 | 33.69 | 39.61 | 119 | N/A | N/A |
|  CBR Proxy | 2G | 100 | 10000 | 0 | 0 | 1053.23 | 94.79 | 57.73 | 277 | N/A | N/A |
|  CBR Proxy | 2G | 100 | 100000 | 0 | 0 | 110.72 | 901.24 | 221.93 | 1511 | N/A | N/A |
|  CBR Proxy | 2G | 200 | 500 | 0 | 0 | 3304.56 | 60.38 | 53.79 | 185 | N/A | N/A |
|  CBR Proxy | 2G | 200 | 1000 | 0 | 0 | 2980.33 | 66.96 | 56.51 | 197 | N/A | N/A |
|  CBR Proxy | 2G | 200 | 10000 | 0 | 0 | 1026.15 | 194.75 | 102.68 | 501 | N/A | N/A |
|  CBR Proxy | 2G | 200 | 100000 | 0 | 0 | 81.2 | 2449.56 | 921.8 | 4735 | N/A | N/A |
|  CBR Proxy | 2G | 500 | 500 | 0 | 0 | 3244.9 | 153.87 | 95.99 | 387 | N/A | N/A |
|  CBR Proxy | 2G | 500 | 1000 | 0 | 0 | 2943.77 | 169.65 | 104.98 | 421 | N/A | N/A |
|  CBR Proxy | 2G | 500 | 10000 | 0 | 0 | 939.32 | 531.92 | 200.65 | 1063 | N/A | N/A |
|  CBR Proxy | 2G | 500 | 100000 | 0 | 0 | 42.23 | 11480.64 | 3926.59 | 19327 | N/A | N/A |
|  CBR Proxy | 2G | 1000 | 500 | 0 | 0 | 2769.52 | 360.68 | 162.35 | 819 | N/A | N/A |
|  CBR Proxy | 2G | 1000 | 1000 | 0 | 0 | 2863.82 | 348.92 | 169.2 | 811 | N/A | N/A |
|  CBR Proxy | 2G | 1000 | 10000 | 0 | 0 | 748.49 | 1331.05 | 524.38 | 3071 | N/A | N/A |
|  CBR Proxy | 2G | 1000 | 100000 | 0 | 100 | 4.68 | 127274.24 | 19437.35 | 186367 | N/A | N/A |

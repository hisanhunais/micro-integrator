# WSO2 Micro Integrator 4.0.0-beta Performance Test Results

During each release, we execute various automated performance test scenarios and publish the results.

| Test Scenarios | Description |
| --- | --- |
| Direct Proxy | Passthrough proxy service |

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
| Operating System | Distribution | Kernel | Linux ip-10-0-1-171 5.4.0-1041-aws #43~18.04.1-Ubuntu SMP Sat Mar 20 15:47:52 UTC 2021 x86_64 x86_64 x86_64 GNU/Linux |


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
|  Direct Proxy | 2G | 100 | 500 | 0 | 0 | 3856.08 | 25.84 | 39.53 | 119 | 92.37 | 219.172 |
|  Direct Proxy | 2G | 100 | 1000 | 0 | 0 | 3948.46 | 25.23 | 32.14 | 113 | N/A | N/A |
|  Direct Proxy | 2G | 100 | 10000 | 0 | 0 | 3339.48 | 29.83 | 35.48 | 116 | N/A | N/A |
|  Direct Proxy | 2G | 100 | 100000 | 0 | 0 | 1507.53 | 66.11 | 31.41 | 149 | N/A | N/A |
|  Direct Proxy | 2G | 200 | 500 | 0 | 0 | 3959.85 | 50.38 | 59.37 | 179 | N/A | N/A |
|  Direct Proxy | 2G | 200 | 1000 | 0 | 0 | 3973.93 | 50.19 | 55.97 | 178 | N/A | N/A |
|  Direct Proxy | 2G | 200 | 10000 | 0 | 0 | 3380.49 | 58.88 | 51.08 | 180 | N/A | N/A |
|  Direct Proxy | 2G | 200 | 100000 | 0 | 0 | 1440.69 | 138.49 | 45.63 | 252 | N/A | N/A |
|  Direct Proxy | 2G | 500 | 500 | 0 | 0 | 3994.09 | 125.02 | 86.71 | 347 | N/A | N/A |
|  Direct Proxy | 2G | 500 | 1000 | 0 | 0 | 3949.34 | 126.42 | 98.64 | 349 | N/A | N/A |
|  Direct Proxy | 2G | 500 | 10000 | 0 | 0 | 2984.36 | 167.34 | 134.89 | 643 | N/A | N/A |

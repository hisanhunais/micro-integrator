# WSO2 Micro Integrator 4.0.0-alpha Performance Test Results

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

1. **Throughput**: The number of requests that the WSO2 Micro Integrator 4.0.0-alpha processes during a specific time interval (e.g. per second).
2. **Response Time**: The end-to-end latency for an operation of invoking a service in WSO2 Micro Integrator 4.0.0-alpha . The complete distribution of response times was recorded.

In addition to the above metrics, we measure the load average and several memory-related metrics.

The following are the test parameters.

| Test Parameter | Description | Values |
| --- | --- | --- |
| Scenario Name | The name of the test scenario. | Refer to the above table. |
| Heap Size | The amount of memory allocated to the application | 2G |
| Concurrent Users | The number of users accessing the application at the same time. | 100, 200, 500 |
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
| System | Memory | System memory | 3785192 KiB |
| System | Storage | Block Device: nvme0n1 | 8G |
| Operating System | Distribution | Release | Ubuntu 18.04.5 LTS |
| Operating System | Distribution | Kernel | Linux ip-10-0-1-71 5.4.0-1041-aws #43~18.04.1-Ubuntu SMP Sat Mar 20 15:47:52 UTC 2021 x86_64 x86_64 x86_64 GNU/Linux |


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
|  Direct Proxy | 2G | 100 | 500 | 0 | 0 | 3871.96 | 25.75 | 36.38 | 116 | 92.09 | 203.339 |
|  Direct Proxy | 2G | 100 | 1000 | 0 | 0 | 3892.53 | 25.62 | 37.34 | 115 | N/A | N/A |
|  Direct Proxy | 2G | 100 | 10000 | 0 | 0 | 3326.57 | 29.96 | 36.42 | 119 | N/A | N/A |
|  Direct Proxy | 2G | 100 | 100000 | 0 | 0 | 1464.86 | 68.06 | 30.13 | 148 | N/A | N/A |
|  Direct Proxy | 2G | 200 | 500 | 0 | 0 | 3958.73 | 50.41 | 58.39 | 180 | N/A | N/A |
|  Direct Proxy | 2G | 200 | 1000 | 0 | 0 | 3984.08 | 50.09 | 48.57 | 176 | N/A | N/A |
|  Direct Proxy | 2G | 200 | 10000 | 0 | 0 | 3396.51 | 58.76 | 49.22 | 184 | N/A | N/A |
|  Direct Proxy | 2G | 200 | 100000 | 0 | 0 | 1420.02 | 140.52 | 41.77 | 252 | N/A | N/A |
|  Direct Proxy | 2G | 500 | 500 | 0 | 0 | 3964.84 | 125.97 | 89.32 | 355 | N/A | N/A |
|  Direct Proxy | 2G | 500 | 1000 | 0 | 0 | 3960.15 | 125.9 | 93.33 | 355 | N/A | N/A |
|  Direct Proxy | 2G | 500 | 10000 | 0 | 0 | 3093.65 | 161.48 | 125.78 | 623 | N/A | N/A |

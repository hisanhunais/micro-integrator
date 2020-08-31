# WSO2 Micro Integrator 1.2.0 Performance Test Results

During each release, we execute various automated performance test scenarios and publish the results.

| Test Scenarios | Description |
| --- | --- |
| Clone & Aggregate With 2 Backend Proxy | Clone payload and send to 2 backends and aggregate the response back |
| Clone & Aggregate With 4 Backend Proxy | Clone payload and send to 4 backends and aggregate the response back |

Our test client is [Apache JMeter](https://jmeter.apache.org/index.html). We test each scenario for a fixed duration of
time. We split the test results into warmup and measurement parts and use the measurement part to compute the
performance metrics.

Test scenarios use a [Netty](https://netty.io/) based back-end service which echoes back any request
posted to it after a specified period of time.

We run the performance tests under different numbers of concurrent users, message sizes (payloads) and back-end service
delays.

The main performance metrics:

1. **Throughput**: The number of requests that the WSO2 Micro Integrator 1.2.0 processes during a specific time interval (e.g. per second).
2. **Response Time**: The end-to-end latency for an operation of invoking a service in WSO2 Micro Integrator 1.2.0 . The complete distribution of response times was recorded.

In addition to the above metrics, we measure the load average and several memory-related metrics.

The following are the test parameters.

| Test Parameter | Description | Values |
| --- | --- | --- |
| Scenario Name | The name of the test scenario. | Refer to the above table. |
| Heap Size | The amount of memory allocated to the application | 2G |
| Concurrent Users | The number of users accessing the application at the same time. | 500 |
| Message Size (Bytes) | The request payload size in Bytes. | 500, 1000, 10000, 100000 |
| Back-end Delay (ms) | The delay added by the Back-end service. | 0 |

The duration of each test is **360 seconds**. The warm-up period is **120 seconds**.
The measurement results are collected after the warm-up period.

The performance tests were executed on 1 AWS CloudFormation stack.


System information for WSO2 Micro Integrator 1.2.0 in 1st AWS CloudFormation stack.

| Class | Subclass | Description | Value |
| --- | --- | --- | --- |
| AWS | EC2 | AMI-ID | ami-0bcc094591f354be2 |
| AWS | EC2 | Instance Type | c5.large |
| System | Processor | CPU(s) | 2 |
| System | Processor | Thread(s) per core | 2 |
| System | Processor | Core(s) per socket | 1 |
| System | Processor | Socket(s) | 1 |
| System | Processor | Model name | Intel(R) Xeon(R) Platinum 8124M CPU @ 3.00GHz |
| System | Memory | BIOS | 64 KiB |
| System | Memory | System memory | 3785232 KiB |
| System | Storage | Block Device: nvme0n1 | 8G |
| Operating System | Distribution | Release | Ubuntu 18.04.5 LTS |
| Operating System | Distribution | Kernel | Linux ip-10-0-1-123 5.3.0-1032-aws #34~18.04.2-Ubuntu SMP Fri Jul 24 10:06:28 UTC 2020 x86_64 x86_64 x86_64 GNU/Linux |


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

|  Scenario Name | Heap Size | Concurrent Users | Message Size (Bytes) | Back-end Service Delay (ms) | Error % | Throughput (Requests/sec) | Average Response Time (ms) | Standard Deviation of Response Time (ms) | 99th Percentile of Response Time (ms) | WSO2 Micro Integrator 1.2.0 GC Throughput (%) | Average WSO2 Micro Integrator 1.2.0 Memory Footprint After Full GC (M) |
|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|
|  Clone & Aggregate With 4 Backend Proxy | 2G | 500 | 500 | 0 | 0 | 1192.8 | 418.84 | 170.14 | 851 | N/A | N/A |
|  Clone & Aggregate With 4 Backend Proxy | 2G | 500 | 1000 | 0 | 0 | 945.91 | 528.54 | 213.46 | 1103 | N/A | N/A |
|  Clone & Aggregate With 4 Backend Proxy | 2G | 500 | 10000 | 0 | 0 | 134.86 | 3678.02 | 1251.61 | 6431 | N/A | N/A |
|  Clone & Aggregate With 4 Backend Proxy | 2G | 500 | 100000 | 0 | 100 | 3.09 | 120064 | 0 | 120319 | N/A | N/A |
|  Clone & Aggregate With 2 Backend Proxy | 2G | 500 | 500 | 0 | 0 | 1303.12 | 383.6 | 180.35 | 807 | 89.12 | 221.872 |
|  Clone & Aggregate With 2 Backend Proxy | 2G | 500 | 1000 | 0 | 0 | 1065 | 468.99 | 188.23 | 999 | N/A | N/A |
|  Clone & Aggregate With 2 Backend Proxy | 2G | 500 | 10000 | 0 | 0 | 150.25 | 3307.42 | 1111.11 | 5823 | N/A | N/A |
|  Clone & Aggregate With 2 Backend Proxy | 2G | 500 | 100000 | 0 | 100 | 3.38 | 120060.42 | 149.23 | 120319 | N/A | N/A |

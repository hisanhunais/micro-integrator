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
| Concurrent Users | The number of users accessing the application at the same time. | 500, 1000 |
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
| System | Memory | System memory | 3785216 KiB |
| System | Storage | Block Device: nvme0n1 | 8G |
| Operating System | Distribution | Release | Ubuntu 18.04.5 LTS |
| Operating System | Distribution | Kernel | Linux ip-10-0-1-216 5.3.0-1032-aws #34~18.04.2-Ubuntu SMP Fri Jul 24 10:06:28 UTC 2020 x86_64 x86_64 x86_64 GNU/Linux |


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
|  Clone & Aggregate With 4 Backend Proxy | 2G | 500 | 500 | 0 | 100 | 24039.33 | 17.84 | 23.87 | 138 | N/A | N/A |
|  Clone & Aggregate With 4 Backend Proxy | 2G | 500 | 1000 | 0 | 100 | 23962.72 | 17.84 | 22.93 | 128 | N/A | N/A |
|  Clone & Aggregate With 4 Backend Proxy | 2G | 500 | 10000 | 0 | 100 | 23771.67 | 18.05 | 24.12 | 137 | N/A | N/A |
|  Clone & Aggregate With 4 Backend Proxy | 2G | 500 | 100000 | 0 | 100 | 24015.03 | 17.89 | 23.14 | 131 | N/A | N/A |
|  Clone & Aggregate With 4 Backend Proxy | 2G | 1000 | 500 | 0 | 100 | 22603.12 | 37.5 | 39.02 | 205 | N/A | N/A |
|  Clone & Aggregate With 4 Backend Proxy | 2G | 1000 | 1000 | 0 | 100 | 22927.34 | 36.56 | 38.28 | 201 | N/A | N/A |
|  Clone & Aggregate With 4 Backend Proxy | 2G | 1000 | 10000 | 0 | 100 | 23104.14 | 36.37 | 35.07 | 185 | N/A | N/A |
|  Clone & Aggregate With 4 Backend Proxy | 2G | 1000 | 100000 | 0 | 100 | 22917.44 | 36.7 | 36.95 | 194 | N/A | N/A |
|  Clone & Aggregate With 2 Backend Proxy | 2G | 500 | 500 | 0 | 0 | 1258.7 | 397.05 | 171.67 | 847 | 90.45 | 169.427 |
|  Clone & Aggregate With 2 Backend Proxy | 2G | 500 | 1000 | 0 | 0 | 1051.59 | 475.15 | 183.38 | 979 | N/A | N/A |
|  Clone & Aggregate With 2 Backend Proxy | 2G | 500 | 10000 | 0 | 0 | 146.79 | 3379.77 | 1097.2 | 5823 | N/A | N/A |
|  Clone & Aggregate With 2 Backend Proxy | 2G | 500 | 100000 | 0 | 100 | 3.01 | 122479.36 | 7981.67 | 152575 | N/A | N/A |
|  Clone & Aggregate With 2 Backend Proxy | 2G | 1000 | 500 | 0 | 100 | 22856.82 | 36.84 | 36.98 | 194 | N/A | N/A |
|  Clone & Aggregate With 2 Backend Proxy | 2G | 1000 | 1000 | 0 | 100 | 23080.35 | 36.65 | 36.58 | 197 | N/A | N/A |
|  Clone & Aggregate With 2 Backend Proxy | 2G | 1000 | 10000 | 0 | 100 | 23031.02 | 36.31 | 37.45 | 202 | N/A | N/A |
|  Clone & Aggregate With 2 Backend Proxy | 2G | 1000 | 100000 | 0 | 100 | 22980.81 | 36.61 | 37.81 | 198 | N/A | N/A |

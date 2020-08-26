# WSO2 Micro Integrator 1.2.0 Performance Test Results

During each release, we execute various automated performance test scenarios and publish the results.

| Test Scenarios | Description |
| --- | --- |
| CBR SOAP Header Proxy | Routing the message based on a SOAP header in the message payload |

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
| Concurrent Users | The number of users accessing the application at the same time. | 100, 200 |
| Message Size (Bytes) | The request payload size in Bytes. | 500, 1000, 10000, 100000, 200000, 500000, 1000000 |
| Back-end Delay (ms) | The delay added by the Back-end service. | 0 |

The duration of each test is **60 seconds**. The warm-up period is **30 seconds**.
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
| Operating System | Distribution | Kernel | Linux ip-10-0-1-52 5.3.0-1032-aws #34~18.04.2-Ubuntu SMP Fri Jul 24 10:06:28 UTC 2020 x86_64 x86_64 x86_64 GNU/Linux |


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
|  CBR SOAP Header Proxy | 2G | 100 | 500 | 0 | 0 | 2478.46 | 30.4 | 23.67 | 128 | 95.34 | 28.4 |
|  CBR SOAP Header Proxy | 2G | 100 | 1000 | 0 | 0 | 2765.92 | 27.23 | 27.37 | 126 | N/A | N/A |
|  CBR SOAP Header Proxy | 2G | 100 | 10000 | 0 | 0 | 1466.98 | 51.39 | 33.09 | 168 | N/A | N/A |
|  CBR SOAP Header Proxy | 2G | 100 | 100000 | 0 | 0 | 203.39 | 371.07 | 137.13 | 739 | N/A | N/A |
|  CBR SOAP Header Proxy | 2G | 100 | 200000 | 0 | 0 | 97.55 | 773.28 | 231.06 | 1335 | N/A | N/A |
|  CBR SOAP Header Proxy | 2G | 100 | 500000 | 0 | 0 | 27.46 | 2732.34 | 1375.96 | 5919 | N/A | N/A |
|  CBR SOAP Header Proxy | 2G | 100 | 1000000 | 0 | 0 | 8.91 | 8032.41 | 2665.22 | 12863 | N/A | N/A |
|  CBR SOAP Header Proxy | 2G | 200 | 500 | 0 | 0 | 2772.94 | 54.18 | 48.18 | 229 | N/A | N/A |
|  CBR SOAP Header Proxy | 2G | 200 | 1000 | 0 | 0 | 2705.97 | 55.61 | 47.28 | 232 | N/A | N/A |
|  CBR SOAP Header Proxy | 2G | 200 | 10000 | 0 | 0 | 1312.33 | 114.54 | 71.61 | 333 | N/A | N/A |
|  CBR SOAP Header Proxy | 2G | 200 | 100000 | 0 | 0 | 171.34 | 876.35 | 388.12 | 2223 | N/A | N/A |
|  CBR SOAP Header Proxy | 2G | 200 | 200000 | 0 | 0 | 65.88 | 2301.66 | 1108.35 | 4991 | N/A | N/A |
|  CBR SOAP Header Proxy | 2G | 200 | 500000 | 0 | 0 | 16.98 | 8448.95 | 3086.35 | 13183 | N/A | N/A |
|  CBR SOAP Header Proxy | 2G | 200 | 1000000 | 0 | 94.68 | 0.26 | 265269.11 | 231302.05 | 700415 | N/A | N/A |

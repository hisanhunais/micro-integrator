# WSO2 Micro Integrator 4.0.0 Performance Test Results

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

1. **Throughput**: The number of requests that the WSO2 Micro Integrator 4.0.0 processes during a specific time interval (e.g. per second).
2. **Response Time**: The end-to-end latency for an operation of invoking a service in WSO2 Micro Integrator 4.0.0 . The complete distribution of response times was recorded.

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


System information for WSO2 Micro Integrator 4.0.0 in 1st AWS CloudFormation stack.

| Class | Subclass | Description | Value |
| --- | --- | --- | --- |
| AWS | EC2 | AMI-ID | ami-04bdd81ca5f1191d5 |
| AWS | EC2 | Instance Type | c5.large |
| System | Processor | CPU(s) | 2 |
| System | Processor | Thread(s) per core | 2 |
| System | Processor | Core(s) per socket | 1 |
| System | Processor | Socket(s) | 1 |
| System | Processor | Model name | Intel(R) Xeon(R) Platinum 8275CL CPU @ 3.00GHz |
| System | Memory | BIOS | 64 KiB |
| System | Memory | System Memory | 4 GiB |
| System | Storage | Block Device: nvme0n1 | 8G |
| Operating System | Distribution | Release | Ubuntu 18.04.5 LTS |
| Operating System | Distribution | Kernel | Linux ip-10-0-1-150 5.4.0-1055-aws #58~18.04.1-Ubuntu SMP Wed Jul 28 03:04:50 UTC 2021 x86_64 x86_64 x86_64 GNU/Linux |


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
|  CBR SOAP Header Proxy | 2G | 100 | 500 | 0 | 0 | 3452.08 | 28.87 | 31.48 | 113 | 93.56 | 167.992 |
|  CBR SOAP Header Proxy | 2G | 100 | 1000 | 0 | 0 | 3299.98 | 30.21 | 32.62 | 112 | N/A | N/A |
|  CBR SOAP Header Proxy | 2G | 100 | 10000 | 0 | 0 | 1521.07 | 65.6 | 42.06 | 201 | N/A | N/A |
|  CBR SOAP Header Proxy | 2G | 100 | 100000 | 0 | 0 | 209.68 | 476.68 | 157.5 | 871 | N/A | N/A |
|  CBR SOAP Header Proxy | 2G | 200 | 500 | 0 | 0 | 3582.67 | 55.7 | 39.05 | 175 | N/A | N/A |
|  CBR SOAP Header Proxy | 2G | 200 | 1000 | 0 | 0 | 3330.62 | 59.92 | 49.51 | 185 | N/A | N/A |
|  CBR SOAP Header Proxy | 2G | 200 | 10000 | 0 | 0 | 1491.74 | 133.89 | 72.93 | 347 | N/A | N/A |
|  CBR SOAP Header Proxy | 2G | 200 | 100000 | 0 | 0 | 162.39 | 1228.71 | 482.52 | 2879 | N/A | N/A |
|  CBR SOAP Header Proxy | 2G | 500 | 500 | 0 | 0 | 3492.68 | 143.01 | 92.84 | 369 | N/A | N/A |
|  CBR SOAP Header Proxy | 2G | 500 | 1000 | 0 | 0 | 3306.38 | 151.01 | 82.14 | 385 | N/A | N/A |
|  CBR SOAP Header Proxy | 2G | 500 | 10000 | 0 | 0 | 1416.36 | 353.05 | 148.23 | 743 | N/A | N/A |
|  CBR SOAP Header Proxy | 2G | 500 | 100000 | 0 | 0 | 99.33 | 5008.19 | 1705.56 | 9535 | N/A | N/A |
|  CBR SOAP Header Proxy | 2G | 1000 | 500 | 0 | 0 | 2977.6 | 335.54 | 158.48 | 743 | N/A | N/A |
|  CBR SOAP Header Proxy | 2G | 1000 | 1000 | 0 | 0 | 3177.62 | 314.39 | 168.27 | 751 | N/A | N/A |
|  CBR SOAP Header Proxy | 2G | 1000 | 10000 | 0 | 0 | 1221.1 | 817.09 | 308.15 | 2063 | N/A | N/A |
|  CBR SOAP Header Proxy | 2G | 1000 | 100000 | 0 | 0 | 34.25 | 28454.08 | 7262.68 | 41215 | N/A | N/A |

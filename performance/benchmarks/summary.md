# WSO2 Micro Integrator 4.0.0-beta Performance Test Results

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
| Operating System | Distribution | Kernel | Linux ip-10-0-1-81 5.4.0-1041-aws #43~18.04.1-Ubuntu SMP Sat Mar 20 15:47:52 UTC 2021 x86_64 x86_64 x86_64 GNU/Linux |


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
|  CBR SOAP Header Proxy | 2G | 100 | 500 | 0 | 0 | 3340.18 | 29.84 | 32.6 | 117 | 93.34 | 168.817 |
|  CBR SOAP Header Proxy | 2G | 100 | 1000 | 0 | 0 | 3146.24 | 31.68 | 40.58 | 119 | N/A | N/A |
|  CBR SOAP Header Proxy | 2G | 100 | 10000 | 0 | 0 | 1449.91 | 68.83 | 43.22 | 208 | N/A | N/A |
|  CBR SOAP Header Proxy | 2G | 100 | 100000 | 0 | 0 | 200.16 | 499.29 | 154.92 | 891 | N/A | N/A |
|  CBR SOAP Header Proxy | 2G | 200 | 500 | 0 | 0 | 3410.96 | 58.49 | 46.71 | 183 | N/A | N/A |
|  CBR SOAP Header Proxy | 2G | 200 | 1000 | 0 | 0 | 3168.78 | 62.98 | 58.13 | 192 | N/A | N/A |
|  CBR SOAP Header Proxy | 2G | 200 | 10000 | 0 | 0 | 1425.78 | 140.11 | 71.75 | 353 | N/A | N/A |
|  CBR SOAP Header Proxy | 2G | 200 | 100000 | 0 | 0 | 154.95 | 1287.81 | 505.42 | 2975 | N/A | N/A |
|  CBR SOAP Header Proxy | 2G | 500 | 500 | 0 | 0 | 3365.49 | 148.36 | 80.49 | 375 | N/A | N/A |
|  CBR SOAP Header Proxy | 2G | 500 | 1000 | 0 | 0 | 3131.34 | 159.45 | 92.67 | 393 | N/A | N/A |
|  CBR SOAP Header Proxy | 2G | 500 | 10000 | 0 | 0 | 1350.19 | 370.33 | 144.03 | 767 | N/A | N/A |
|  CBR SOAP Header Proxy | 2G | 500 | 100000 | 0 | 0 | 89.76 | 5520.12 | 2070.35 | 10495 | N/A | N/A |
|  CBR SOAP Header Proxy | 2G | 1000 | 500 | 0 | 0 | 2813.36 | 354.9 | 157.49 | 787 | N/A | N/A |
|  CBR SOAP Header Proxy | 2G | 1000 | 1000 | 0 | 0 | 3044.67 | 327.93 | 155.78 | 735 | N/A | N/A |
|  CBR SOAP Header Proxy | 2G | 1000 | 10000 | 0 | 0 | 1164.86 | 857.29 | 317.57 | 2159 | N/A | N/A |
|  CBR SOAP Header Proxy | 2G | 1000 | 100000 | 0 | 0 | 30.82 | 30019.7 | 6477.38 | 39935 | N/A | N/A |

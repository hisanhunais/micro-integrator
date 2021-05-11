# WSO2 Micro Integrator 4.0.0 Performance Test Results

During each release, we execute various automated performance test scenarios and publish the results.

| Test Scenarios | Description |
| --- | --- |
| Direct Proxy | Passthrough proxy service |
| CBR Proxy | Routing the message based on the content of the message body |
| XSLT Proxy | Having XSLT transformations in request and response paths |
| Direct API | Passthrough API service |
| CBR SOAP Header Proxy | Routing the message based on a SOAP header in the message payload |
| CBR Transport Header Proxy | Routing the message based on an HTTP header in the message |
| XSLT Enhanced Proxy | Having enhanced, Fast XSLT transformations in request and response paths |

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
| Concurrent Users | The number of users accessing the application at the same time. | 100 |
| Message Size (Bytes) | The request payload size in Bytes. | 500, 1000, 10000, 100000 |
| Back-end Delay (ms) | The delay added by the Back-end service. | 0 |

The duration of each test is **360 seconds**. The warm-up period is **120 seconds**.
The measurement results are collected after the warm-up period.

The performance tests were executed on 1 AWS CloudFormation stack.


System information for WSO2 Micro Integrator 4.0.0 in 1st AWS CloudFormation stack.

| Class | Subclass | Description | Value |
| --- | --- | --- | --- |
| AWS | EC2 | AMI-ID | ami-0758a746e73c88fe3 |
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
| Operating System | Distribution | Kernel | Linux ip-10-0-1-174 5.4.0-1047-aws #49~18.04.1-Ubuntu SMP Wed Apr 28 23:08:58 UTC 2021 x86_64 x86_64 x86_64 GNU/Linux |


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
|  CBR Proxy | 2G | 100 | 500 | 0 | 0 | 3157.97 | 31.57 | 39 | 117 | N/A | N/A |
|  CBR Proxy | 2G | 100 | 1000 | 0 | 0 | 2849.52 | 35 | 39.88 | 119 | N/A | N/A |
|  CBR Proxy | 2G | 100 | 10000 | 0 | 0 | 1011.93 | 98.68 | 60.01 | 287 | N/A | N/A |
|  CBR Proxy | 2G | 100 | 100000 | 0 | 0 | 105.42 | 946.95 | 238.69 | 1783 | N/A | N/A |
|  CBR SOAP Header Proxy | 2G | 100 | 500 | 0 | 0 | 1657.15 | 60.26 | 278.27 | 201 | N/A | N/A |
|  CBR SOAP Header Proxy | 2G | 100 | 1000 | 0 | 0 | 204.7 | 488.46 | 1042.05 | 3023 | N/A | N/A |
|  CBR SOAP Header Proxy | 2G | 100 | 10000 | 0 | 0 | 242.93 | 411.53 | 902.72 | 2927 | N/A | N/A |
|  CBR SOAP Header Proxy | 2G | 100 | 100000 | 0 | 0 | 181.88 | 549.15 | 167.3 | 959 | N/A | N/A |
|  CBR Transport Header Proxy | 2G | 100 | 500 | 0 | 0 | 423.6 | 236 | 725.69 | 2895 | N/A | N/A |
|  CBR Transport Header Proxy | 2G | 100 | 1000 | 0 | 0 | 101.91 | 981.21 | 1417.31 | 3423 | N/A | N/A |
|  CBR Transport Header Proxy | 2G | 100 | 10000 | 0 | 0 | 139.71 | 715.62 | 1225 | 3263 | N/A | N/A |
|  CBR Transport Header Proxy | 2G | 100 | 100000 | 0 | 0 | 1134.07 | 87.93 | 41.1 | 225 | N/A | N/A |
|  Direct API | 2G | 100 | 500 | 0 | 0 | 3816.52 | 26.12 | 39.61 | 118 | N/A | N/A |
|  Direct API | 2G | 100 | 1000 | 0 | 0 | 3799.7 | 26.23 | 41.89 | 117 | N/A | N/A |
|  Direct API | 2G | 100 | 10000 | 0 | 0 | 3149.79 | 31.65 | 44.07 | 124 | N/A | N/A |
|  Direct API | 2G | 100 | 100000 | 0 | 0 | 1322.14 | 75.4 | 26.58 | 164 | N/A | N/A |
|  Direct Proxy | 2G | 100 | 500 | 0 | 0 | 3982.68 | 25.02 | 34.9 | 112 | 91.52 | 212.698 |
|  Direct Proxy | 2G | 100 | 1000 | 0 | 0 | 3946.24 | 25.26 | 37.29 | 113 | N/A | N/A |
|  Direct Proxy | 2G | 100 | 10000 | 0 | 0 | 3321.49 | 30.01 | 35.48 | 119 | N/A | N/A |
|  Direct Proxy | 2G | 100 | 100000 | 0 | 0 | 1408.22 | 70.77 | 24.1 | 154 | N/A | N/A |
|  XSLT Enhanced Proxy | 2G | 100 | 500 | 0 | 100 | 0.67 | 120064 | 0 | 120319 | N/A | N/A |
|  XSLT Enhanced Proxy | 2G | 100 | 1000 | 0 | 100 | 0.67 | 120064 | 0 | 120319 | N/A | N/A |
|  XSLT Enhanced Proxy | 2G | 100 | 10000 | 0 | 0 | 513.69 | 194.54 | 71.38 | 383 | N/A | N/A |
|  XSLT Enhanced Proxy | 2G | 100 | 100000 | 0 | 0 | 73.81 | 1351.29 | 288.65 | 2023 | N/A | N/A |
|  XSLT Proxy | 2G | 100 | 500 | 0 | 0 | 1898.39 | 52.58 | 40.53 | 170 | N/A | N/A |
|  XSLT Proxy | 2G | 100 | 1000 | 0 | 0 | 1545.49 | 64.61 | 201.68 | 198 | N/A | N/A |
|  XSLT Proxy | 2G | 100 | 10000 | 0 | 0 | 343.75 | 289.87 | 156.54 | 743 | N/A | N/A |
|  XSLT Proxy | 2G | 100 | 100000 | 0 | 0 | 31.01 | 3196.54 | 570.1 | 4703 | N/A | N/A |

# WSO2 Micro Integrator 4.0.0 Performance Test Results

During each release, we execute various automated performance test scenarios and publish the results.

| Test Scenarios | Description |
| --- | --- |
| XSLT Proxy | Having XSLT transformations in request and response paths |

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
| AWS | EC2 | AMI-ID | ami-0747bdcabd34c712a |
| AWS | EC2 | Instance Type | c5.large |
| System | Processor | CPU(s) | 2 |
| System | Processor | Thread(s) per core | 2 |
| System | Processor | Core(s) per socket | 1 |
| System | Processor | Socket(s) | 1 |
| System | Processor | Model name | Intel(R) Xeon(R) Platinum 8124M CPU @ 3.00GHz |
| System | Memory | BIOS | 64 KiB |
| System | Memory | System memory | 3785188 KiB |
| System | Storage | Block Device: nvme0n1 | 8G |
| Operating System | Distribution | Release | Ubuntu 18.04.5 LTS |
| Operating System | Distribution | Kernel | Linux ip-10-0-1-160 5.4.0-1045-aws #47~18.04.1-Ubuntu SMP Tue Apr 13 15:58:14 UTC 2021 x86_64 x86_64 x86_64 GNU/Linux |


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
|  XSLT Proxy | 2G | 100 | 500 | 0 | 0 | 1951.95 | 51.12 | 251.24 | 169 | 94.29 | 162.25 |
|  XSLT Proxy | 2G | 100 | 1000 | 0 | 0 | 1138.34 | 60.99 | 273.87 | 188 | N/A | N/A |
|  XSLT Proxy | 2G | 100 | 10000 | 0 | 0 | 357.81 | 279.37 | 149.29 | 703 | N/A | N/A |
|  XSLT Proxy | 2G | 100 | 100000 | 0 | 0 | 31.96 | 3110.22 | 563.7 | 4607 | N/A | N/A |
|  XSLT Proxy | 2G | 200 | 500 | 0 | 0 | 2023.99 | 98.66 | 65.72 | 265 | N/A | N/A |
|  XSLT Proxy | 2G | 200 | 1000 | 0 | 0 | 1633.91 | 122.23 | 73.2 | 329 | N/A | N/A |
|  XSLT Proxy | 2G | 200 | 10000 | 0 | 0 | 349.88 | 570.96 | 240.76 | 1255 | N/A | N/A |
|  XSLT Proxy | 2G | 200 | 100000 | 0 | 0 | 27.62 | 7086.33 | 1398.22 | 10175 | N/A | N/A |
|  XSLT Proxy | 2G | 500 | 500 | 0 | 0 | 1955.44 | 255.54 | 126.4 | 591 | N/A | N/A |
|  XSLT Proxy | 2G | 500 | 1000 | 0 | 0 | 1615.31 | 309.45 | 137.18 | 727 | N/A | N/A |
|  XSLT Proxy | 2G | 500 | 10000 | 0 | 0 | 314.02 | 1586.14 | 427.51 | 2831 | N/A | N/A |
|  XSLT Proxy | 2G | 500 | 100000 | 0 | 0 | 13.47 | 33984.15 | 5411.55 | 48383 | N/A | N/A |
|  XSLT Proxy | 2G | 1000 | 500 | 0 | 0 | 1679.94 | 594.27 | 217.98 | 1223 | N/A | N/A |
|  XSLT Proxy | 2G | 1000 | 1000 | 0 | 0 | 1424.3 | 701.05 | 257.15 | 1495 | N/A | N/A |
|  XSLT Proxy | 2G | 1000 | 10000 | 0 | 0 | 273.98 | 3615.65 | 845.76 | 5631 | N/A | N/A |
|  XSLT Proxy | 2G | 1000 | 100000 | 0 | 100 | 5.6 | 120765.57 | 2697.2 | 136191 | N/A | N/A |

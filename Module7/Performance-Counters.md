# Important Performance Counters

| Resource  | Counter                | Description                                                                                                                                                           | Threshold                    |
| --------- | ---------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------- |
| Processor | % Processor time       | This is the percentage of total elapsed time that the processor was busy executing.                                                                                   | < 60%                        |
| Processor | % Privileged time      | This measures the percentage of elapsed time the processor spent executing in kernel mode.                                                                            | < 20%                        |
| Processor | % User time            | The percentage of elapsed time the processor spent executing any user application code.                                                                               | < 50 %                       |
| Processor | Processor Queue Length | This is the number of threads that are ready to execute but waiting for a core to become available                                                                    | < 2 ~ 3                      |
| Memory    | Available MBs          | The total amount of available memory on the system.                                                                                                                   | At least keep about 10% free |
| Memory    | Pages/sec              | This is actually the sum of "Pages Input/sec" and "Pages Output/sec" counters which is the rate at which pages are being read and written as a result of pages faults | < 20                         |
| Physical Disk | % Idle Time                   | This is a measure of the percentage of time that the disk was idle. ie. there are no pending disk requests from the operating system waiting to be completed. | This value to be as high as possible  |
| Physical Disk | Disk Reads/sec & Disk Writes/sec | These counters each measure the total number of IO requests completed per second.   | This value to be as less as possible                         |
| Physical Disk | Avg. Disk Queue Length |The average number of both read and write requests that were queued for the selected disk during the sample interval.  | <=2*TotalNumberOfDisks                        |
| Network | Bytes total/sec  | This counter measures the number of bytes being transferred through your network  | < 75% (i.e. 75MB/s for a 100MB/s network adaptor)                        |

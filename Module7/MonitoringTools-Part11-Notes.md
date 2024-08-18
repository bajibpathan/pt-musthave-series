## Load Test Analysis using Dynatrace

### Before - Load Test

- Ensure all the servers/services are monitored and are healthy.
- Validate the Dashboard to confirm all the tiles have the data
- Compare SLAs with current Production metrics

### During - Load Test

- Monitor the servers/services health.

### After - Load Test

- Capture Server(s) OS Health metrics (CPU / Memory / Disk / Network)
- Validate Services response times, throughput, failures
- Compare the results with previous tests / Production metrics

### How to troubleshoot using Dynatrace?

Issues identified in the load tests are two types

- Application Issues
- Transaction response times high
- Throughput requirements deviation
- Transaction failures
- Infrastructure Issues

For Application Issues start your analysis from Services under Application Observability.

For Infrastrcture Issues start your analysis from Host under Infrastrcture Observability.

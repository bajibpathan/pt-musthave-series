## Dynatrace JMeter Integration

### Why do we need to Integrate?

- Correlation of Metrics
- Improved Collaboration

### JMeter Integration Process

- Tag the transactions
  - Within JMeter, use the HTTP Header Manager to add custom HTTP request headers. You can use any custom HTTP headers to pass context information.
    Header example: x-dynatrace-test
    Header value: LSN=Script_Name;TSN=Transaction_Name;
- Create a request Attribute
  - In Dynatrace, configure the extraction rules for the custom HTTP Headers via Settings > Server-side service monitoring > Request attributes.
- Run your load test from JMeter.
  - The requests and distributed traces will be tagged in Dynatrace with the configured request attributes

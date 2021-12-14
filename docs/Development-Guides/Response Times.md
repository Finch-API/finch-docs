# Response Times

API response times depend on a variety of factors including but not limited to the endpoint, the employment system, and the size of the company. 

## Average response times

The following table represents the average latencies per endpoint for a company with 50-100 employees.

Endpoint | Average Latency | Notes
-------|-------------|-----
`/company` | 5 seconds | The response times will vary per system.
`/directory` | 10 seconds | The response times will vary per system and by the size of the company.
`/individual` | 15 seconds | The response times will vary per system and by the size of the company.
`/employment` | 15 seconds | The response times will vary per system and by the size of the company.
`/payment` | 20 seconds** | The response times will vary per system, the size of the company, and the requested time period.
`/pay-statement` | 20 seconds** | The response times will vary per system, the size of the company, and the requested time period.

**For a two-month time period

<!-- theme: info -->
> The above average latencies can be expected immediately after a user grants your application access to their employment system. Future API requests will take roughly the same time however there may be additional latency on occasion as Finch refreshes its session with the employment system.
---
stoplight-id: f7af2039f9a7b
---

# Data Syncs

Finch syncs data with automated providers on a 24 hour cadence, and with assisted providers on a 7 day cadence; Finch API responses will return data from the most recent successful sync. Performing data syncs in this way ensures that latency for all Finch API requests should remain under 200ms.

After an employer authorizes your application through Finch Connect, Finch will enqueue an initial data fetch job which will fetch all relevant data for the employer connection. For automated providers, if you attempt to request data before the initial sync has completed, Finch will request live data from the provider*. Live request latencies may range from several seconds to minutes for large batch sizes. Once the initial data sync has completed, Finch API responses will return the synced data.

You can use several Finch response headers to determine the freshness of the data you receive:

Response Header | Description
-------|--------------
`Finch-Data-Retrieved` |	The date/time that the data was retrieved from the employment system.
`Finch-Last-Attempted-Update-Date` | The date/time that Finch last attempted to sync the data for this endpoint.
`Finch-Last-Attempted-Update-Result` | The result of Finch’s last attempted update. Possible values:<br />`success`: The last attempt succeeded<br />`error`: The last attempt errored<br />`partial_error`: (batch requests only) The last attempt succeeded for some items in the batch and failed for others.

**ADP Workforce Now connections will not return live data before a data sync has completed. Until the first data sync completes, Finch will return a 202 response for ADP WFN requests. Your application should be prepared to handle 202 responses. Once the first data sync has completed, Finch will begin returning the most recently synced data.*

### Batch requests
For batch endpoints (`/employment`, `/individual`, `/pay-statement`) Finch syncs all of the data for the connection in one atomic operation. This ensures that all items in the batch response you receive are from the same data sync.

### Pay statements
Finch currently fetches pay statements from the start of 2020.

Because there is significantly more pay statement data than payment data, it may be the case that individual pay statements take much longer to fetch than payments. Therefore if you have received a `payment_id` from the `/payment` endpoint, and try to use it in a `/pay-statement` request, it is possible the pay statement has not been fetched yet. In this case, Finch will return a 202 in the **body** of the `/pay-statement` request. The response will look like this:
```json
{
  "responses": [
    {
      "payment_id": "9c8626e3-6d97-48a0-883c-f4c65e736321",
      "code": 202,
      "body": {
        "code": 202,
        "name": "accepted",
        "finch_code": "data_sync_in_progress",
        "message": "The pay statements for this payment are being fetched. Please check back later."
      }
    },
    ...
  ]
}

```
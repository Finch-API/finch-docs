# Headers

## Request Headers

Every request to Finch's API requires the following headers—
Header | Description
-------|-------------
`Authorization` | Bearer authorization header, which is formed by concatenating the word “Bearer” with the access token, separated by a space.
`Finch-API-Version` | Header used to specify the version for a given API request. Current version is **2020-09-17**.

***

## Response Headers

Finch’s additional response headers provide information about the data contained in responses.

Header | Description
-------|--------------
`Finch-Request-Id` |	Each response from Finch's API has a unique request identifier. If you need to contact us about a specific request, providing the request identifier will ensure the fastest possible resolution.
`Finch-Data-Retrieved` |	The date/time in ISO-8601 format that the data was retrieved from the employment system.
`Finch-Last-Attempted-Update-Date` | The date/time in ISO-8601 format that Finch last attempted to update this data.
`Finch-Last-Attempted-Update-Result` | The result of Finch’s last attempted update. Possible values:<br />`success`: the last attempt succeeded<br />`error`: the last attempt errored<br />`partial_error`: (batch requests only) the last attempt succeeded for some items in the batch and failed for others.
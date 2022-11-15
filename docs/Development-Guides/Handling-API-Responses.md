# Handling API Responses

## Finch IDs

All IDs (UUIDs) returned by Finch endpoints are fixed for the same underlying employment system account. They will not change even if you have multiple `access_token`s for the company, a different payroll admin from a company logs in, etc.

## Null Values

API responses can return `null` values for some fields. This can happen for a few different reasons—

1. The employment system does not support the field.
2. The field is supported by the employment system but the data has not been filled in by the payroll administrator of a company.
3. Finch was not able to infer a reasonable value (for example, the categorization of a tax).

<!-- theme: success -->
> Ensure your Finch integration is resilient to `null` values.
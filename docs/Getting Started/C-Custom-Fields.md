# Getting Custom Fields

To fetch custom fields, you can hit any of our standard endpoints (`company`, `individual`, `employment`, `payment`, `pay-statement`) and simply append `/custom-fields` to the end of the endpoint name (e.g. `employment/custom-fields`). The data returned will be either an object containing all of the custom fields for your application, as in the case of `/company`, or an array of objects in a batch response, as in the case of `/employment` or `/individual`. Please see the API documentation for more information. 

There are two types of endpoints in the **Custom Fields** product:
- `/{endpoint}/custom-fields` returns the custom fields that have been built for your application. This endpoint will mirror the standard `{endpoint}` in structure e.g. the custom fields counterpart for `POST /employment` will be `POST /employment/custom-fields`.
- `/{endpoint}/custom-fields/meta` provides information about the custom fields that are available for the input `{endpoint}` for your application. 
Possible `{endpoint}` values: `company`, `directory`, `individual`, `employment`, `payment`, `pay-statement`.
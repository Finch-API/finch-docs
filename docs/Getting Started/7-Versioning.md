# Versioning

We periodically release new, dated versions of the API whenever we make breaking changes. Although we try to only make backwards compatible changes, but sometimes we have to make a breaking change to iterate on the API.

**We consider the following changes backwards compatible**
- Adding new API endpoints
- Adding new optional parameters to existing endpoints
- Adding new data elements to existing responses
- Adding new `error`

Our current version is **2020-09-17**

The [`Finch-API-Version` header](5-Headers.md) must be set for every single request to our API.
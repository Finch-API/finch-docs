# API Versioning

We periodically release new, dated versions of the API whenever we make breaking changes. Although we try to only make backward-compatible changes, sometimes we have to make a breaking change to iterate on the API.

**We consider the following changes backward compatible**

- Adding new API endpoints
- Adding new optional parameters to existing endpoints
- Adding new data elements to existing responses
- Adding new **`error`**

Our current version is **2020-09-17**

<!-- theme: info -->
> As mentioned above we only increment the version for breaking changes, so this may be an older date. That doesn't mean API changes haven't occured, merely that they were backwards compatible. 

The `Finch-API-Version` header must be set for every single request to our API.
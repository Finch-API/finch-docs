---
stoplight-id: sl9n3gphljf2w
---

# Request Forwarding

## Enabling Custom Data Requests

Request Forwarding is a passthrough API feature that enables you to issue raw requests directly against an integration. With Request Forwarding, you have the ability to access any functionality that is natively supported by an integration. You’ll be able to access data elements that are outside of Finch’s existing API structure and standard data model. You’ll also be able to write data elements that are outside the scope of what is supported through one of Finch’s standardized APIs.

*Request Forwarding is available for customers in our Scale tier. Please reach out to a Finch representative for more details on eligibility.*

### How it Works

**Standard Finch API Request**

Requests to one of Finch’s standard API endpoints go through a data transformation layer to ensure that you have a consistent request and response structure to work with, regardless of the system you’re extracting data from.

<!-- focus: false -->
![finch_standard_api.png](../../assets/images/finch_standard_api.png)

**Finch Request Forwarding**

Request Forwarding bypasses the data transformation layer, giving you access to the raw data exposed by an integration and leaving the data mapping fully in your control.

<!-- focus: false -->
![finch_request_forwarding.png](../../assets/images/finch_request_forwarding.png)

For more details on making requests using Request Forwarding, please refer to the API reference for `/forward`.

### Using Request Forwarding

You can watch a video demonstration that exhibits how to use the /forward API for [accessing deeper data sets](https://www.loom.com/share/81f86fa4a2fc4c13b42bb153e66dba06?sid=5ba4e1df-840a-40f6-b2f7-4abbb71eb01c) within an employment system.

For more details on making requests using Request Forwarding, please refer to the API reference for `/forward`.

### Supported Integrations

> Request Forwarding is only supported for connections that were established via the API-based auth method.

API documentation for the systems that are currently supported by Request Forwarding are referenced below.

* **Bamboo**: [API Documentation](https://documentation.bamboohr.com/reference)
* **Gusto:** [API Documentation](https://docs.gusto.com/app-integrations/reference)
* **HiBob:** [API Documentation](https://apidocs.hibob.com/reference)
* **Personio:** [API Documentation](https://developer.personio.de/reference)
* **Trinet**: [API Documentation](https://developers.trinet.com/explore-trinet-apis)
* **UKG Pro:** [API Documentation](https://developer.ukg.com/hcm/reference/welcome-to-the-pro-developer-hub)

For specifics on how to make requests using Request Forwarding, please refer to the API reference for `/forward`.

### Why Request Forwarding?

For each supported integration, Finch provides a standardized set of API endpoints and data models. However, if you require additional information outside this standard model, Request Forwarding enables your application to read or write specific fields from provider-supported API endpoints. This supplements the standardized endpoints and fields without needing to handle the complexities of building and managing a separate integration yourself for accessing non-standardized fields.

For example, consider a situation where Finch’s data model supports 95% of the fields your application needs. Instead of having to build a direct integration with the provider to get the other 5% of fields you need, you can look to Request Forwarding. After all, building and maintaining a single integration is the reason you chose Finch in the first place! With Request Forwarding, you could gain access to the other 5% of the data you need.

When using Request Forwarding, Finch leverages the existing connection that was established via Finch Connect, forwards the request to the provider, and then forwards the provider’s response back to your application. It is important to note that Request Forwarding does not alter requests or responses, it simply forwards them between you and the provider while Finch manages credentials and authentication for you.

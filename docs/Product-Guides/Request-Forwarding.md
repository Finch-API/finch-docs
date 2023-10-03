---
stoplight-id: sl9n3gphljf2w
---

# Request Forwarding

## Enabling Custom Data Requests

Request Forwarding is a passthrough API feature that enables you to issue raw requests directly against an integration. With Request Forwarding, you have the ability to access any functionality that is natively supported by an integration, including data elements that are outside of Finch’s existing API structure and standard data model. You’ll also be able to write data elements that are outside the scope of what is supported through one of Finch’s standardized APIs.

### How it Works

**Standard Finch API Request**

Requests to one of Finch’s standard API endpoints go through a data transformation layer to ensure that you have a consistent request and response structure to work with, regardless of the system you’re extracting data from.

<!-- focus: false -->
![finch_standard_api.png](../../assets/images/finch_standard_api.png)

**Finch Request Forwarding**

Request Forwarding bypasses the data transformation layer, giving you access to the raw data exposed by an integration and leaving the data mapping fully in your control.

<!-- focus: false -->
![finch_request_forwarding.png](../../assets/images/finch_request_forwarding.png)

### Using Request Forwarding

You can [watch a video demonstration](https://www.loom.com/share/15ca7fb93c2d43b9a052362fd3368e37?sid=07e1313d-011b-4c73-9c78-d05ec0f9ab9d) that exhibits how to use the /forward API for accessing deeper data sets within an employment system.

For more details on making requests using Request Forwarding, please refer to the API reference for [`/forward`](https://developer.tryfinch.com/docs/reference/dwnn4o21afzyr-request-forwarding).

### Supported Integrations

> Request Forwarding is only supported for connections that were established via the API-based auth method.

API documentation for the systems that are currently supported by Request Forwarding are referenced below.

* **BambooHR**: [API Documentation](https://documentation.bamboohr.com/reference)
* **Gusto:** [API Documentation](https://docs.gusto.com/app-integrations/reference)
* **HiBob:** [API Documentation](https://apidocs.hibob.com/reference)
* **Paycom:** [API Documentation](https://drive.google.com/file/d/1aC9C4W1mZo4oFxNIZUtS1zkfJ4tH6WjD/view?usp=sharing)
* **Personio:** [API Documentation](https://developer.personio.de/reference)
* **TriNet**: [API Documentation](https://developers.trinet.com/explore-trinet-apis)
* **UKG Pro:** [API Documentation](https://developer.ukg.com/hcm/reference/welcome-to-the-pro-developer-hub)

### Why Request Forwarding?

For each supported integration, Finch provides a standardized set of API endpoints and data models. However, if you require additional information outside this standard model, Request Forwarding enables your application to read or write specific fields from provider-supported API endpoints. This supplements Finch's standardized endpoints and fields without you needing to handle the complexities of building and managing a separate integration yourself for accessing non-standardized fields.

For example, consider a situation where Finch’s data model supports 95% of the fields your application needs. Instead of having to build a direct integration with the provider to get the other 5% of fields you need, you can look to Request Forwarding. After all, building and maintaining a single integration is the reason you chose Finch in the first place! With Request Forwarding, you can gain access to the other 5% of the data you need.

When using Request Forwarding, Finch leverages the existing connection that was established via Finch Connect, forwards the request to the provider, and then forwards the provider’s response back to your application. It is important to note that Request Forwarding does not alter requests or responses, it simply forwards them between you and the provider while Finch manages credentials and authentication for you.

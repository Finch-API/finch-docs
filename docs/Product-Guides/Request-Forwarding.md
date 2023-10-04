---
stoplight-id: sl9n3gphljf2w
---

# Request Forwarding

## Enabling Custom Data Requests

Request Forwarding is a passthrough API feature that enables you to issue raw requests directly against an employment system's API. With Request Forwarding, you have the ability to access any functionality that is natively supported by an integration, including data elements that are outside of Finch’s existing API structure and standard data model. You’ll also be able to write data elements that are outside the scope of what is supported through one of Finch’s standardized APIs.

*Request Forwarding is available for customers in our Scale tier. Please reach out to a Finch representative for more details on eligibility.*

### Using Request Forwarding

You can [watch a video demonstration](https://www.loom.com/share/15ca7fb93c2d43b9a052362fd3368e37) that exhibits how to use the /forward API for accessing deeper data sets within an employment system.

For more details on making requests using Request Forwarding, please refer to the API reference for [`/forward`](https://developer.tryfinch.com/docs/reference/dwnn4o21afzyr-request-forwarding).

### How it Works

**Standard Finch API Request**

Requests to one of Finch’s standard API endpoints go through a data transformation layer to ensure that you have a consistent request and response structure to work with, regardless of the system you’re extracting data from.

<!-- focus: false -->
![finch_standard_api.png](../../assets/images/finch_standard_api.png)

**Finch Request Forwarding**

Request Forwarding bypasses the data transformation layer, giving you access to the raw data exposed by an integration and leaving the data mapping fully in your control.

<!-- focus: false -->
![finch_request_forwarding.png](../../assets/images/finch_request_forwarding.png)

### Why Request Forwarding?

For each supported integration, Finch provides a standardized set of API endpoints and data models. However, if you require additional information outside these standard models, Request Forwarding enables your application to read or write specific fields from provider-supported API endpoints. This supplements Finch's standardized endpoints and fields without you needing to handle the complexities of building and managing a separate integration yourself for accessing non-standardized fields.

For example, consider a situation where Finch’s data model supports 95% of the fields your application needs. Instead of having to build a direct integration with the provider to get the other 5% of fields you need, you can look to Request Forwarding. After all, building and maintaining a single integration is the reason you chose Finch in the first place! With Request Forwarding, you can gain access to the other 5% of the data you need.

When using Request Forwarding, Finch leverages the existing connection that was established via Finch Connect, forwards the request to the provider, and then forwards the provider’s response back to your application. It is important to note that Request Forwarding does not alter requests or responses, it simply forwards them between you and the provider while Finch manages credentials and authentication for you.

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

### Usage Example of Request Forwarding

A simple example use case for using Request Forwarding is to access the termination details for an inactive individual in an HRIS system. Finch's [/employment data model](https://developer.tryfinch.com/docs/reference/1ba5cdec4c979-employment) includes information related to an individual's employment, such as their name, title, department, start and end date, and employment status, but does not include information specific to their termination, such as the reason for their termination.

In this example, we illustrate how to use Request Forwarding with an active **Personio** connection to access the **termination reason** for an inactive individual by the name of **Myriam Smith**.

**Step 1:** Make a request to Finch's /directory endpoint to gather details of this company's employee directory.

Request:
```bash
curl --location 'https://api.tryfinch.com/employer/directory' \
--header 'Authorization: Bearer {{FINCH_ACCESS_TOKEN}}' \
--header 'Content-Type: application/json' \
--header 'Finch-API-Version: 2020-09-17'
```

Response:
```bash
{
    "paging": {
        "count": 148,
        "offset": 0
    },
    "individuals": [
        {
            "id": "ed535ff8-6f61-4756-8cb9-edba67c87766",
            "first_name": "Yajaira",
            "last_name": "Borton",
            "middle_name": null,
            "department": {
                "name": "HR"
            },
            "manager": {
                "id": "03ab76b5-d158-4c7f-aaf6-a82894e66790"
            },
            "is_active": true
        },
        [...]
        {
            "id": "51834db6-94e4-4e34-bc5d-76bc8456fb55",
            "first_name": "Myriam",
            "last_name": "Smith",
            "middle_name": null,
            "department": {
                "name": "Customer Service"
            },
            "manager": {
                "id": "8b59db87-1b44-4a84-82f4-763885e2b99b"
            },
            "is_active": false
        }
    ]
}
```

**Step 2:** Using the individual's unique ID, make a request to Finch's /employment endpoint to gather holistic detail on their employment.

Request:

```bash
curl --location 'https://api.tryfinch.com/employer/employment' \
--header 'Authorization: Bearer {{FINCH_ACCESS_TOKEN}}' \
--header 'Content-Type: application/json' \
--header 'Finch-API-Version: 2020-09-17' \
--data '{
  "requests": [
    { "individual_id": "51834db6-94e4-4e34-bc5d-76bc8456fb55" }
  ]
}
'
```

Response:

```bash
{
    "responses": [
        {
            "individual_id": "51834db6-94e4-4e34-bc5d-76bc8456fb55",
            "code": 200,
            "body": {
                "id": "51834db6-94e4-4e34-bc5d-76bc8456fb55",
                "first_name": "Myriam",
                "last_name": "Smith",
                "middle_name": null,
                "title": "IT-Customer Service Manager",
                "employment": {
                    "type": "employee",
                    "subtype": null
                },
                "manager": {
                    "id": "8b59db87-1b44-4a84-82f4-763885e2b99b"
                },
                "department": {
                    "name": "Customer Service"
                },
                "start_date": "2014-11-01",
                "end_date": "2020-11-30",
                "is_active": false,
                "class_code": null,
                "location": null,
                "income": {
                    "unit": "monthly",
                    "amount": 412500,
                    "currency": "SEK",
                    "effective_date": null
                },
                "income_history": null,
                "custom_fields": [
                    {
                        "name": "Trainings",
                        "value": "Data security training,Product training"
                    },
                    {
                        "name": "Marital status",
                        "value": "single"
                    },
                    {
                        "name": "Language Skills",
                        "value": "English,German"
                    }
                ],
                "source_id": "12907776"
            }
        }
    ]
}
```

**Step 3:** Using the `source_id` field in Finch's /employment response, use Request Forwarding ([/forward](https://developer.tryfinch.com/docs/reference/dwnn4o21afzyr-request-forwarding)) to access additional details directly from Personio's API, including this individual's `termination_reason`.

Request:

```bash
curl --location 'https://api.tryfinch.com/forward' \
--header 'Authorization: Bearer {{FINCH_ACCESS_TOKEN}}' \
--header 'Content-Type: application/json' \
--header 'Finch-API-Version: 2020-09-17' \
--data '{
  "method": "GET",
  "route": "/company/employees/12907776",
  "headers": null,
  "params": null,
  "data": null
}
'
```

Response:

```bash
{
    "request": {
        "headers": null,
        "method": "GET",
        "route": "/company/employees/12907776",
        "data": null,
        "params": null
    },
    "headers": {
        "date": "Wed, 04 Oct 2023 20:21:27 GMT",
        "content-type": "application/json",
        "transfer-encoding": "chunked",
        "connection": "close",
        "x-is-preview": "false",
        "x-is-shadow": "false",
        "vary": "Accept-Encoding, Origin",
        "cache-control": "no-cache, private",
        "authorization": "Bearer papi-BPzkN1v8FufvCBidgBhh4GqI1BDfjkXRevmNo8GM1s-BCPGj2LJn1QEs8xOF2pKBhGfOI2pr5-UmimqDN6PyLw-MTI0Mzc0",
        "x-frame-options": "DENY",
        "content-security-policy": "frame-ancestors 'none'",
        "strict-transport-security": "max-age=31536000",
        "x-xss-protection": "1; mode=block",
        "x-content-type-options": "nosniff"
    },
    "statusCode": 200,
    "data": "{\"success\":true,\"data\":{\"type\":\"Employee\",\"attributes\":{\"id\":{\"label\":\"ID\",\"value\":12907776,\"type\":\"integer\",\"universal_id\":\"id\"},\"first_name\":{\"label\":\"First name\",\"value\":\"Myriam\",\"type\":\"standard\",\"universal_id\":\"first_name\"},\"last_name\":{\"label\":\"Last name\",\"value\":\"Smith\",\"type\":\"standard\",\"universal_id\":\"last_name\"},\"email\":{\"label\":\"Email\",\"value\":\"myriam.smith@demo-sample.com\",\"type\":\"standard\",\"universal_id\":\"email\"},\"gender\":{\"label\":\"Gender\",\"value\":\"female\",\"type\":\"standard\",\"universal_id\":\"gender\"},\"status\":{\"label\":\"Status\",\"value\":\"inactive\",\"type\":\"standard\",\"universal_id\":\"status\"},\"position\":{\"label\":\"Position\",\"value\":\"IT-Customer Service Manager\",\"type\":\"standard\",\"universal_id\":\"position\"},\"supervisor\":{\"label\":\"Supervisor\",\"value\":{\"type\":\"Employee\",\"attributes\":{\"id\":{\"label\":\"ID\",\"value\":12907741,\"type\":\"integer\",\"universal_id\":\"id\"},\"first_name\":{\"label\":\"First name\",\"value\":\"Max\",\"type\":\"standard\",\"universal_id\":\"first_name\"},\"last_name\":{\"label\":\"Last name\",\"value\":\"Schmiedel\",\"type\":\"standard\",\"universal_id\":\"last_name\"},\"email\":{\"label\":\"Email\",\"value\":\"max.schmiedel@demo-sample.com\",\"type\":\"standard\",\"universal_id\":\"email\"}}},\"type\":\"standard\",\"universal_id\":\"supervisor\"},\"employment_type\":{\"label\":\"Employment type\",\"value\":\"internal\",\"type\":\"standard\",\"universal_id\":\"employment_type\"},\"weekly_working_hours\":{\"label\":\"Weekly hours\",\"value\":\"40\",\"type\":\"standard\",\"universal_id\":\"weekly_working_hours\"},\"hire_date\":{\"label\":\"Hire date\",\"value\":\"2014-11-01T00:00:00+01:00\",\"type\":\"date\",\"universal_id\":\"hire_date\"},\"contract_end_date\":{\"label\":\"Contract ends\",\"value\":null,\"type\":\"date\",\"universal_id\":\"contract_end_date\"},\"termination_date\":{\"label\":\"Termination date\",\"value\":\"2020-11-30T00:00:00+01:00\",\"type\":\"date\",\"universal_id\":\"termination_date\"},\"termination_type\":{\"label\":\"Termination type\",\"value\":\"employee-quit\",\"type\":\"standard\",\"universal_id\":\"termination_type\"},\"termination_reason\":{\"label\":\"Termination reason\",\"value\":\"employee-quit\",\"type\":\"standard\",\"universal_id\":\"termination_reason\"},\"probation_period_end\":{\"label\":\"Probation period end\",\"value\":\"2015-04-30T00:00:00+02:00\",\"type\":\"date\",\"universal_id\":\"probation_period_end\"},\"created_at\":{\"label\":\"Created at\",\"value\":\"2020-09-21T10:48:14+02:00\",\"type\":\"date\",\"universal_id\":\"created_at\"},\"last_modified_at\":{\"label\":\"Last modified\",\"value\":\"2022-12-09T17:34:50+01:00\",\"type\":\"date\",\"universal_id\":\"last_modified_at\"},\"subcompany\":{\"label\":\"Subcompany\",\"value\":{\"type\":\"Subcompany\",\"attributes\":{\"id\":127825,\"name\":\"Subsidiary SE\"}},\"type\":\"standard\",\"universal_id\":\"subcompany\"},\"office\":{\"label\":\"Office\",\"value\":{\"type\":\"Office\",\"attributes\":{\"id\":1466964,\"name\":\"Gothenburg\"}},\"type\":\"standard\",\"universal_id\":\"office\"},\"department\":{\"label\":\"Department\",\"value\":{\"type\":\"Department\",\"attributes\":{\"id\":3853110,\"name\":\"Customer Service\"}},\"type\":\"standard\",\"universal_id\":\"department\"},\"cost_centers\":{\"label\":\"Cost center\",\"value\":[{\"type\":\"CostCenter\",\"attributes\":{\"id\":730214,\"name\":\"Cost center 2\",\"percentage\":100}}],\"type\":\"standard\",\"universal_id\":\"cost_centers\"},\"holiday_calendar\":{\"label\":\"Public holidays\",\"value\":{\"type\":\"HolidayCalendar\",\"attributes\":{\"id\":2015,\"name\":\"Sweden public holidays\",\"country\":null,\"state\":null}},\"type\":\"standard\",\"universal_id\":\"holiday_calendar\"},\"absence_entitlement\":{\"label\":\"Absence entitlement\",\"value\":[{\"type\":\"TimeOffType\",\"attributes\":{\"id\":2135006,\"name\":\"Paid Vacation UK\",\"category\":\"paid_vacation\",\"entitlement\":0}},{\"type\":\"TimeOffType\",\"attributes\":{\"id\":2135005,\"name\":\"Paid Vacation SE\",\"category\":\"paid_vacation\",\"entitlement\":0}},{\"type\":\"TimeOffType\",\"attributes\":{\"id\":2135004,\"name\":\"Paid Vacation NL\",\"category\":\"paid_vacation\",\"entitlement\":0}}],\"type\":\"standard\",\"universal_id\":\"absence_entitlement\"},\"work_schedule\":{\"label\":\"Work schedule\",\"value\":{\"type\":\"WorkSchedule\",\"attributes\":{\"id\":1248089,\"name\":\"Full-time, 40 hours without time tracking, (mon,tue,wed,thu,fri)\",\"valid_from\":null,\"monday\":\"08:00\",\"tuesday\":\"08:00\",\"wednesday\":\"08:00\",\"thursday\":\"08:00\",\"friday\":\"08:00\",\"saturday\":\"00:00\",\"sunday\":\"00:00\"}},\"type\":\"standard\",\"universal_id\":\"work_schedule\"},\"fix_salary\":{\"label\":\"Fixed salary\",\"value\":4125,\"type\":\"decimal\",\"universal_id\":\"fix_salary\",\"currency\":\"SEK\"},\"fix_salary_interval\":{\"label\":\"Salary interval\",\"value\":\"monthly\",\"type\":\"standard\",\"universal_id\":\"fix_salary_interval\"},\"hourly_salary\":{\"label\":\"Hourly salary\",\"value\":0,\"type\":\"decimal\",\"universal_id\":\"hourly_salary\",\"currency\":\"SEK\"},\"vacation_day_balance\":{\"label\":\"Vacation day balance\",\"value\":0,\"type\":\"decimal\",\"universal_id\":\"vacation_day_balance\"},\"last_working_day\":{\"label\":\"Last day of work\",\"value\":null,\"type\":\"date\",\"universal_id\":\"last_working_day\"},\"profile_picture\":{\"label\":\"Profile Picture\",\"value\":\"https://api.personio.de/v1/company/employees/12907776/profile-picture\",\"type\":\"standard\",\"universal_id\":\"profile_picture\"},\"team\":{\"label\":\"Team\",\"value\":{\"type\":\"Team\",\"attributes\":{\"id\":1674017,\"name\":\"Customer Service\"}},\"type\":\"standard\",\"universal_id\":\"team\"},\"dynamic_6726179\":{\"label\":\"Type of Visa\",\"value\":\"\",\"type\":\"standard\",\"universal_id\":null},\"dynamic_6726181\":{\"label\":\"Employee ID\",\"value\":\"11617\",\"type\":\"standard\",\"universal_id\":null},\"dynamic_6726182\":{\"label\":\"National Insurance Number\",\"value\":\"99999999999\",\"type\":\"standard\",\"universal_id\":null},\"dynamic_6726188\":{\"label\":\"Holder of bank account\",\"value\":\"Myriam Smith\",\"type\":\"standard\",\"universal_id\":null},\"dynamic_6726191\":{\"label\":\"Emergency contact name\",\"value\":\"Sabina Smith\",\"type\":\"standard\",\"universal_id\":null},\"dynamic_6726195\":{\"label\":\"Address\",\"value\":\"Kössö Bryggväg 33\",\"type\":\"standard\",\"universal_id\":null},\"dynamic_6726165\":{\"label\":\"Birthday\",\"value\":\"1988-05-10T00:00:00+02:00\",\"type\":\"date\",\"universal_id\":\"date_of_birth\"},\"dynamic_6726173\":{\"label\":\"Trainings\",\"value\":\"Data security training,Product training\",\"type\":\"tags\",\"universal_id\":null},\"dynamic_6726180\":{\"label\":\"Visa expiry date\",\"value\":null,\"type\":\"date\",\"universal_id\":null},\"dynamic_6726189\":{\"label\":\"IBAN\",\"value\":\"SE45 5000 0000 0583 9825 7490\",\"type\":\"standard\",\"universal_id\":null},\"dynamic_6726193\":{\"label\":\"Marital status\",\"value\":\"single\",\"type\":\"list\",\"universal_id\":null},\"dynamic_6726197\":{\"label\":\"City\",\"value\":\"Gothenburg\",\"type\":\"standard\",\"universal_id\":null},\"dynamic_6726203\":{\"label\":\"Company car\",\"value\":\"\",\"type\":\"list\",\"universal_id\":null},\"dynamic_6726175\":{\"label\":\"Language Skills\",\"value\":\"English,German\",\"type\":\"tags\",\"universal_id\":null},\"dynamic_6726186\":{\"label\":\"Type of health insurance\",\"value\":\"compulsory\",\"type\":\"list\",\"universal_id\":null},\"dynamic_6726190\":{\"label\":\"BIC\",\"value\":\"XXAADEFF\",\"type\":\"standard\",\"universal_id\":null},\"dynamic_6726192\":{\"label\":\"Emergency contact phone number\",\"value\":\"(+49) 1601234567\",\"type\":\"standard\",\"universal_id\":null},\"dynamic_6726196\":{\"label\":\"Postcode\",\"value\":\"405 10\",\"type\":\"standard\",\"universal_id\":null},\"dynamic_6726204\":{\"label\":\"Laptop model\",\"value\":\"\",\"type\":\"list\",\"universal_id\":null},\"dynamic_6726166\":{\"label\":\"LinkedIn\",\"value\":\"https://www.linkedin.com/\",\"type\":\"link\",\"universal_id\":null},\"dynamic_6726176\":{\"label\":\"First Aider\",\"value\":\"no\",\"type\":\"list\",\"universal_id\":null},\"dynamic_6726187\":{\"label\":\"Name of health insurance\",\"value\":\"Example Insurance\",\"type\":\"standard\",\"universal_id\":null},\"dynamic_6726194\":{\"label\":\"Personal email\",\"value\":\"Myriam@Smith.com\",\"type\":\"standard\",\"universal_id\":null},\"dynamic_6726171\":{\"label\":\"Emergency contact relationship to the employee\",\"value\":\"mother\",\"type\":\"list\",\"universal_id\":null},\"dynamic_6726198\":{\"label\":\"Main or secondary occupation\",\"value\":\"main occupation\",\"type\":\"list\",\"universal_id\":null},\"dynamic_6726202\":{\"label\":\"Nationality\",\"value\":\"Swedish\",\"type\":\"list\",\"universal_id\":null},\"dynamic_6726199\":{\"label\":\"Child allowance\",\"value\":\"0\",\"type\":\"list\",\"universal_id\":null},\"dynamic_6726170\":{\"label\":\"Salary type\",\"value\":\"fix salary\",\"type\":\"list\",\"universal_id\":null},\"dynamic_6726168\":{\"label\":\"Notice period\",\"value\":\"3 months to end of month\",\"type\":\"standard\",\"universal_id\":null},\"dynamic_6726169\":{\"label\":\"Occupation type\",\"value\":\"permanent employment\",\"type\":\"list\",\"universal_id\":null}}}}"
}
```

The /forward API response includes details of the original `request`, alongside the forwarded response details from Personio's API. The response body that was retrieved from Personio is provided in raw format in the `data` response field. Myriam's **termination_reason** can be extracted from here.

```js
{
  label: 'Termination reason',
  value: 'employee-quit',
  type: 'standard',
  universal_id: 'termination_reason'
}
```

To recap, we've illustrated an example of how to use Request Forwarding to complement Finch's standardized data models, providing you with the most comprehensive view of the data you need, without having to incur the burden of managing an additional integration, all using a single Finch access token.

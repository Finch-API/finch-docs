# Individual

## Create Deduction

**Info**: Add an individual to a company's deduction.

### Request

**Example request**
```shell
curl https://api.tryfinch.com/employer/deduction/individual/create \
-X "POST" \
-H "Authorization: Bearer {token}" \
-H "Finch-API-Version: 2020-09-17" \
-H "Content-Type: application/json" \
-D '{
  "deduction_id": "7adbeaf0-9f98-48c1-935b-26a521f1aa8d",
  "individual_id": "af015567-858a-4355-aa63-5617ff341592",
  "employee_deduction": {
    "amount": 10000,
    "type": "fixed"
  },
  "company_contribution": {
    "amount": 10000,
    "type": "fixed"
  }
}'
```

**Request body parameters**

Parameter | Type | Required | Description
----------|------|----------|-------------
`deduction_id` | `string` | true | A unique Finch `id` (UUID v4) for the deduction.
`individual_id` | `string` | true | A unique Finch `id` (UUID v4) for the individual.
`employee_deduction` | `object` | true | An object representing the employee deduction.
`employee_deduction.amount` | `integer` | true | If the type is `fixed`, the deduction amount as an integer in cents. Otherwise, if the type is `percent`, the percentage as an integer from 0 (0%) - 10000 (100%).
`employee_deduction.type` | `string` | true | Specify if the deduction is a fixed amount or percentage of the paycheck. Options: `fixed` or `percent`.
`company_contribution` | `object` | false | An object representing the company contribution. **Note:** Required for `401k_pre_tax` deduction.
`company_contribution.amount` | `integer` | true | If the type is `fixed`, the contribution amount as an integer in cents. Otherwise, if the type is `percent`, the percentage as an integer from 0 (0%) - 10000 (100%).
`company_contribution.type` | `string` | true | Specify if the contribution is a fixed amount or percentage of the paycheck. Options: `fixed` or `percent`.

### Response

**Example response**
```json
{
  "status": "success"
}
```

**Response body**

Parameter | Type | Description
----------|------|-------------
`status` | `string` | If the request is successful, Finch will return “success” (HTTP 200 status).

***

## Get Deduction

**Info**: Retrieve the configuration of an individual's deduction.

### Request

**Example request**
```shell
curl https://api.tryfinch.com/employer/deduction/individual/get \
-X "POST" \
-H "Authorization: Bearer {token}" \
-H "Finch-API-Version: 2020-09-17" \
-H "Content-Type: application/json" \
-D '{
  "deduction_id": "7adbeaf0-9f98-48c1-935b-26a521f1aa8d",
  "individual_id": "af015567-858a-4355-aa63-5617ff341592"
}'
```

**Request body parameters**

Parameter | Type | Required | Description
----------|------|----------|-------------
`deduction_id` | `string` | true | A unique Finch `id` (UUID v4) for the deduction.
`individual_id` | `string` | true | A unique Finch `id` (UUID v4) for the individual.

### Response

**Example response**
```json
{
  "deduction_id": "7adbeaf0-9f98-48c1-935b-26a521f1aa8d",
  "individual_id": "af015567-858a-4355-aa63-5617ff341592",
  "employee_deduction": {
    "amount": 10000,
    "type": "fixed"
  },
  "company_contribution": {
    "amount": 10000,
    "type": "fixed"
  }
}
```

**Response body**

Parameter | Type | Description
----------|------|-------------
`deduction_id` | `string` | A unique Finch `id` (UUID v4) for the deduction.
`individual_id` | `string` | A unique Finch `id` (UUID v4) for the individual.
`employee_deduction` | `object` | An object representing the employee deduction.
`employee_deduction.amount` | `integer` | If the type is `fixed`, the deduction amount as an integer in cents. Otherwise, if the type is `percent`, the percentage as an integer from 0 (0%) - 10000 (100%).
`employee_deduction.type` | `string` | Specify if the deduction is a fixed amount or percentage of the paycheck. Options: `fixed` or `percent`.
`company_contribution` | `object` | An object representing the company contribution.
`company_contribution.amount` | `integer` | If the type is `fixed`, the contribution amount as an integer in cents. Otherwise, if the type is `percent`, the percentage as an integer from 0 (0%) - 10000 (100%).
`company_contribution.type` | `string` | Specify if the contribution is a fixed amount or percentage of the paycheck. Options: `fixed` or `percent`.

***

## Delete Deduction

**Info**: Remove an individual from a deduction.

### Request

**Example request**
```shell
curl https://api.tryfinch.com/employer/deduction/individual/delete \
-X "POST" \
-H "Authorization: Bearer {token}" \
-H "Finch-API-Version: 2020-09-17" \
-H "Content-Type: application/json" \
-D '{
  "deduction_id": "7adbeaf0-9f98-48c1-935b-26a521f1aa8d",
  "individual_id": "af015567-858a-4355-aa63-5617ff341592"
}'
```

**Request body parameters**

Parameter | Type | Required | Description
----------|------|----------|-------------
`deduction_id` | `string` |  true | A unique Finch `id` (UUID v4) for the deduction.
`individual_id` | `string` | true | A unique Finch `id` (UUID v4) for the individual.

### Response

**Example response**
```json
{
  "status": "success"
}
```

**Response body**

Parameter | Type | Description
----------|------|-------------
`status` | `string` | If the request is successful, Finch will return “success” (HTTP 200 status).





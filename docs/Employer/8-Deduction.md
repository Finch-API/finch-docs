# Deduction

**Info**: Manage and process deductions on individuals within a company.

**Product**: `deduction`

***

## Create a deduction

**URL**: `https://api.tryfinch.com/employer/deduction/create`

**Example request**
```shell
curl https://api.tryfinch.com/employer/deduction/create \
-X "POST" \
-H "Authorization: Basic base64({client_id}:{client_secret})']" \
-H "Finch-API-Version: 2020-09-17" \
-H "Content-Type: application/json" \
-d '{
    "type": "post_tax",
    "frequency": "one_time",
    "name": "One Time Post Tax Deduction"
}'
```

**Request body parameters**

Parameter | Type | Required | Description
----------|------|----------|-------------
`type` | `string` | true | The type of deduction. Options: `post_tax`, `medical_pre_tax`, `vision_pre_tax`, `dental_pre_tax`, `hsa_pre_tax`, `fsa_pre_tax`, `fsa_dependent_pre_tax`, `401k_pre_tax`, `403b_pre_tax`, and `457_pre_tax`.
`frequency` | `string` | true | The frequency to run this deduction with. Options: `one_time` (run on the next pay run) and `recurring` (run on every pay run).
`name` | `string` | true | The name or short description of the deduction.

**Example response**
```json
{
    "deduction_id": "20aa7cf2-949d-4d4e-9c01-499b59501ded",
}
```

**Response body**

Parameter | Type | Description
----------|------|-------------
`deduction_id` | `string` | A unique Finch `id` (UUID v4) for the deduction.

***

## Run a deduction

**URL**: `https://api.tryfinch.com/employer/deduction/run`

**Example request**
```shell
curl https://api.tryfinch.com/employer/deduction/run \
-X "POST" \
-H "Authorization: Bearer <token>" \
-H "Finch-API-Version: 2020-09-17" \
-H "Content-Type: application/json" \
-d '{
    "deduction_id": "<deduction_id",
    "individual_id": "<individual_id>",
    "amount": {
       "type": "fixed",
       "value": "1000",
     },
}'
```

**Request body parameters**

Parameter | Type | Required | Description
----------|------|----------|-------------
`deduction_id` | `string` | true | The unique Finch `id` of the deduction to run.
`individual_id` | `string` | true | The stable Finch `id` of the individual to process the deduction on.
`amount` | `object` | true | The amount object.
`amount.type` | `string` | true | Specify if the deduction is a fixed amount or percentage of the paycheck. Options: `fixed` or `percent`.
`amount.value` | `integer` | true | If the type is `fixed`, the deduction amount as an integer in cents. Otherwise, if the type is `percent`, the percentage as an integer from 0 - 100.

**Example response**

```json
{
  "status": "success"
}
```

** Response body**


Name | Type | Description
-----|------|-------------
`status` | `string` | If the request is successful, Finch will return “success” (HTTP 200 status).

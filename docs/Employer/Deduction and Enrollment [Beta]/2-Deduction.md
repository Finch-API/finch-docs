# Deduction

**URL**: `https://api.tryfinch.com/employer/deduction`

***

## Create Deduction

**Info**: Create company deductions

#### Request

**Example request**
```shell
curl https://api.tryfinch.com/employer/deduction \
-X "POST" \
-H "Authorization: Bearer {token}" \
-H "Finch-API-Version: 2020-09-17" \
-H "Content-Type: application/json" \
-D '{
  "name": "401(k) Deduction",
  "type": "401k_pre_tax",
  "frequency": "recurring"
}'
```

**Request body parameters**

Parameter | Type | Required | Description
----------|------|----------|-------------
`name` | `string` | true | The name or short description of the deduction.
`type` | `string` | true | The type of deduction. Options: `post_tax`, `medical_pre_tax`, `vision_pre_tax`, `dental_pre_tax`, `hsa_pre_tax`, `fsa_pre_tax`, `fsa_dependent_pre_tax`, `roth_401k_pre_tax`, `401k_pre_tax`, `403b_pre_tax`, and `457_pre_tax`.
`frequency` | `string` | true | The frequency to run this deduction with. Options: `one_time` (run on the next pay run) and `recurring` (run on every pay run).

#### Response

**Example response**
```json
{
  "id": "7adbeaf0-9f98-48c1-935b-26a521f1aa8d"
}
```

**Response body**

Parameter | Type | Description
----------|------|-------------
`id` | `string` | A unique Finch `id` (UUID v4) for the deduction.

***

## Get Deductions

**Info**: Get all company deductions

#### Request

**Example request**
```shell
curl https://api.tryfinch.com/employer/deduction \
-X "GET" \
-H "Authorization: Bearer {token}" \
-H "Finch-API-Version: 2020-09-17" \
-H "Content-Type: application/json"
```

#### Response

**Example response**
```json
[{
  "id": "7adbeaf0-9f98-48c1-935b-26a521f1aa8d",
  "name": "401(k) Deduction",
  "type": "401k_pre_tax",
  "frequency": "recurring"
}]
```

**Response body**

Parameter | Type | Description
----------|------|-------------
`id` | `string` | A unique Finch `id` (UUID v4) for the deduction.
`name` | `string` | The name or short description of the deduction.
`type` | `string` | The type of deduction. Options: `post_tax`, `medical_pre_tax`, `vision_pre_tax`, `dental_pre_tax`, `hsa_pre_tax`, `fsa_pre_tax`, `fsa_dependent_pre_tax`, `roth_401k_pre_tax`, `401k_pre_tax`, `403b_pre_tax`, and `457_pre_tax`.
`frequency` | `string` | The frequency to run this deduction with. Options: `one_time` (run on the next pay run) and `recurring` (run on every pay run).

***

## Delete Deduction

**Info**: Delete a company deductions

#### Request

**Example request**
```shell
curl https://api.tryfinch.com/employer/deduction \
-X "DELETE" \
-H "Authorization: Bearer {token}" \
-H "Finch-API-Version: 2020-09-17" \
-H "Content-Type: application/json" \
-D '{
  "id": "7adbeaf0-9f98-48c1-935b-26a521f1aa8d"
}'
```

**Request body parameters**

Parameter | Type | Required | Description
----------|------|----------|-------------
`id` | `string` |  true | A unique Finch `id` (UUID v4) for the deduction.

#### Response

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




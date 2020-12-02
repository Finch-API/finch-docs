# Company

## Create Company Deduction

**Info**: Configure a company-wide deduction

### Request

**Example request**
```shell
curl https://api.tryfinch.com/employer/company/deduction/create \
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
`type` | `string` | true | The type of deduction. Options: `post_tax`, `401k_pre_tax`.
`frequency` | `string` | true | The frequency to run this deduction with. Options: `one_time` (run on the next pay run) and `recurring` (run on every pay run).

### Response

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

## List Company Deductions

**Info**: List the configured company-wide deductions

### Request

**Example request**
```shell
curl https://api.tryfinch.com/employer/company/deduction/list \
-X "POST" \
-H "Authorization: Bearer {token}" \
-H "Finch-API-Version: 2020-09-17" \
-H "Content-Type: application/json"
```

### Response

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
`type` | `string` | The type of deduction. Options: `post_tax`, `401k_pre_tax`.
`frequency` | `string` | The frequency to run this deduction with. Options: `one_time` (run on the next pay run) and `recurring` (run on every pay run).





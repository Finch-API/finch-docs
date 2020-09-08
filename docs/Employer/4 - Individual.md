# Individual

**Info**: Read employee data, excluding income and employment data

**URL**: `POST https://api.tryfinch.com/v1.0/employer/directory`

**Product**: `individual`

**Request Body Parameters**

Parameter | Type | Required | Description
----------|------|----------|-------------
`individual_ids[]` | `array` | true | Array of individual ids.

**Response Body**

Name | Type | Description
-----|------|--------------
`individuals[]`
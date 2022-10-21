# Compatibility

Finch's API tries to maintain parity between all [providers](./Providers.md). However, every now and then, a provider may not support a specific data field (for example: job titles). This section outlines the compatibility of each data field per Automated API Integration and any other miscellaneous information that's important to know.

## Supported Data Fields

---

<!-- theme: info -->

> <strong><span style="color:green">✓</span></strong> — supported
>
> <strong><span style="color:red">x</span></strong> — not supported by Finch

<!--
type: tab
title: HRIS
-->

### Company
![company.png](https://stoplight.io/api/v1/projects/cHJqOjEzNjY0/images/KJn3cQAW5mw)


<p><i>* Only available by inferring from entity.type</i><br>
<i>** account_number is mask and only shows the last 4 digits</i></p>

### Directory
![directory.png](https://stoplight.io/api/v1/projects/cHJqOjEzNjY0/images/Nfdo8FPyDCE)


<p><i>* Initial only</i></p>

### Individual
![individual.png](https://stoplight.io/api/v1/projects/cHJqOjEzNjY0/images/y2Sg2796qJE)


<p><i>* Initial only</i><br>
<i>** No work email available</i></p>

### Employment
![employment.png](https://stoplight.io/api/v1/projects/cHJqOjEzNjY0/images/eF5QpbJau34)


<p><i>* Initial only</i><br>
<i>** Requires customer to be at highest package tier, ADP Run Pro</i></br>
<i>*** These fields are not provided for contractors</i></p>

### Payment
![payment.png](https://stoplight.io/api/v1/projects/cHJqOjEzNjY0/images/aIOil0UBh3A)


### Pay Statement
![pay-statement.png](https://stoplight.io/api/v1/projects/cHJqOjEzNjY0/images/cPQrrgoojtc)


<p><i>* 401k Match cannot be set on Justworks</i>
<p><i>** Paychex Flex only exposes the previous 24 months of pay data</i></p>

<!--
type: tab
title: ATS
-->

### Candidates
Field Name | Lever
---- | -----
`id` | <strong><span style="color:green">✓</span></strong>
`first_name` | <strong><span style="color:red">x</span></strong>
`last_name` | <strong><span style="color:red">x</span></strong>
`full_name` | <strong><span style="color:green">✓</span></strong>
`emails` | <strong><span style="color:green">✓</span></strong>
`emails[].data` | <strong><span style="color:green">✓</span></strong>
`emails[].type` | <strong><span style="color:green">✓</span></strong>
`phone_numbers` | <strong><span style="color:green">✓</span></strong>
`phone_numbers[].type`| <strong><span style="color:green">✓</span></strong>
`phone_numbers[].data`| <strong><span style="color:green">✓</span></strong>
`created_at` | <strong><span style="color:green">✓</span></strong>
`last_activity_at` | <strong><span style="color:green">✓</span></strong>
`application_ids` | <strong><span style="color:green">✓</span></strong>

*Opportunity leads are excluded from Candidates for Lever

### Applications
Field Name | Lever
---- | -----
`id` | <strong><span style="color:green">✓</span></strong>
`candidate_id` | <strong><span style="color:green">✓</span></strong>
`job_id` | <strong><span style="color:green">✓</span></strong>
`offer_id` | <strong><span style="color:green">✓</span></strong>
`stage` | <strong><span style="color:green">✓</span></strong>
`stage.id` | <strong><span style="color:green">✓</span></strong>
`stage.name` | <strong><span style="color:green">✓</span></strong>
`rejected_at` | <strong><span style="color:green">✓</span></strong>
`rejected_reason`| <strong><span style="color:green">✓</span></strong>
`rejected_reason.text`| <strong><span style="color:green">✓</span></strong>

### Jobs
Field Name | Lever
---- | -----
`id` | <strong><span style="color:green">✓</span></strong>
`name` | <strong><span style="color:green">✓</span></strong>
`status` | <strong><span style="color:green">✓</span></strong>
`department` | <strong><span style="color:green">✓</span></strong>
`department.name` | <strong><span style="color:green">✓</span></strong>
`created_at` | <strong><span style="color:green">✓</span></strong>
`closed_at` | <strong><span style="color:green">✓</span></strong>
`hiring_team` | <strong><span style="color:green">✓</span></strong>
`hiring_team.hiring_managers`| <strong><span style="color:green">✓</span></strong>
`hiring_team.recruiters`| <strong><span style="color:red">x</span></strong>

### Stages
Field Name | Lever
---- | -----
`id` | <strong><span style="color:green">✓</span></strong>
`job_id` | <strong><span style="color:red">x</span></strong>
`name` |<strong><span style="color:green">✓</span></strong>


### Offers
Field Name | Lever
---- | -----
`id` | <strong><span style="color:green">✓</span></strong>
`application_id` | <strong><span style="color:green">✓</span></strong>
`candidate_id` |<strong><span style="color:green">✓</span></strong>
`job_id` | <strong><span style="color:green">✓</span></strong>
`created_at` | <strong><span style="color:green">✓</span></strong>
`updated_at` | <strong><span style="color:red">x</span></strong>
`status`| <strong><span style="color:green">✓</span></strong>

<!-- type: tab-end -->

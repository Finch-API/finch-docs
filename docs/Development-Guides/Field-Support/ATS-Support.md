---
stoplight-id: wt41jy5q4l5z9
---

# ATS Field Support

### Lever
<!--
type: tab
title: API
-->
<details>
<summary><strong style="display:inline">Candidates</strong></summary>

Field Name | Support
---- | -----
`id` | <strong><span style="color:green">✓</span></strong>
`first_name` |
`last_name` |
`full_name` | <strong><span style="color:green">✓</span></strong>
`emails.data` | <strong><span style="color:green">✓</span></strong>
`emails.type` | <strong><span style="color:green">✓</span></strong>
`phone_numbers.type`| <strong><span style="color:green">✓</span></strong>
`phone_numbers.data`| <strong><span style="color:green">✓</span></strong>
`created_at` | <strong><span style="color:green">✓</span></strong>
`last_activity_at` | <strong><span style="color:green">✓</span></strong>
`application_ids` | <strong><span style="color:green">✓</span></strong>

*Opportunity leads are excluded from Candidates for Lever

</details>


<details>
<summary><strong style="display:inline">Applications</strong></summary>

Field Name | Support
---- | -----
`id` | <strong><span style="color:green">✓</span></strong>
`candidate_id` | <strong><span style="color:green">✓</span></strong>
`job_id` | <strong><span style="color:green">✓</span></strong>
`offer_id` | <strong><span style="color:green">✓</span></strong>
`stage` | <strong><span style="color:green">✓</span></strong>
`stage.id` | <strong><span style="color:green">✓</span></strong>
`stage.name` | <strong><span style="color:green">✓</span></strong>
`rejected_at` | <strong><span style="color:green">✓</span></strong>
`rejected_reason.text`| <strong><span style="color:green">✓</span></strong>

</details>

<details>
<summary><strong style="display:inline">Jobs</strong></summary>

Field Name | Support
---- | -----
`id` | <strong><span style="color:green">✓</span></strong>
`name` | <strong><span style="color:green">✓</span></strong>
`status` | <strong><span style="color:green">✓</span></strong>
`department` | <strong><span style="color:green">✓</span></strong>
`department.name` | <strong><span style="color:green">✓</span></strong>
`created_at` | <strong><span style="color:green">✓</span></strong>
`closed_at` | <strong><span style="color:green">✓</span></strong>
`hiring_team.hiring_managers`| <strong><span style="color:green">✓</span></strong>
`hiring_team.recruiters`| <strong><span style="color:red">x</span></strong>

</details>

<details>
<summary><strong style="display:inline">Stages</strong></summary>

Field Name | Support
---- | -----
`id` | <strong><span style="color:green">✓</span></strong>
`job_id` | <strong><span style="color:red">x</span></strong>
`name` |<strong><span style="color:green">✓</span></strong>

</details>


<details>
<summary><strong style="display:inline">Offers</strong></summary>

Field Name | Support
---- | -----
`id` | <strong><span style="color:green">✓</span></strong>
`application_id` | <strong><span style="color:green">✓</span></strong>
`candidate_id` |<strong><span style="color:green">✓</span></strong>
`job_id` | <strong><span style="color:green">✓</span></strong>
`created_at` | <strong><span style="color:green">✓</span></strong>
`updated_at` | <strong><span style="color:red">x</span></strong>
`status`| <strong><span style="color:green">✓</span></strong>

</details>

<!-- type: tab-end -->

### Greenhouse

<!--
type: tab
title: API
-->
<details>
<summary><strong style="display:inline">Candidates</strong></summary>

Field Name | Support
---- | -----
`id` | <strong><span style="color:green">✓</span></strong>
`first_name` |
`last_name` |
`full_name` | <strong><span style="color:green">✓</span></strong>
`emails.data` | <strong><span style="color:green">✓</span></strong>
`emails.type` | <strong><span style="color:green">✓</span></strong>
`phone_numbers.type`| <strong><span style="color:green">✓</span></strong>
`phone_numbers.data`| <strong><span style="color:green">✓</span></strong>
`created_at` | <strong><span style="color:green">✓</span></strong>
`last_activity_at` | <strong><span style="color:green">✓</span></strong>
`application_ids` | <strong><span style="color:green">✓</span></strong>

</details>

<details>
<summary><strong style="display:inline">Applications</strong></summary>

Field Name | Support
---- | -----
`id` | <strong><span style="color:green">✓</span></strong>
`candidate_id` | <strong><span style="color:green">✓</span></strong>
`job_id` | <strong><span style="color:green">✓</span></strong>
`offer_id` | <strong><span style="color:green">✓</span></strong>
`stage` | <strong><span style="color:green">✓</span></strong>
`stage.id` | <strong><span style="color:green">✓</span></strong>
`stage.name` | <strong><span style="color:green">✓</span></strong>
`rejected_at` | <strong><span style="color:green">✓</span></strong>
`rejected_reason.text`| <strong><span style="color:green">✓</span></strong>

</details>

<details>
<summary><strong style="display:inline">Jobs</strong></summary>

Field Name | Support
---- | -----
`id` | <strong><span style="color:green">✓</span></strong>
`name` | <strong><span style="color:green">✓</span></strong>
`status` | <strong><span style="color:green">✓</span></strong>
`department.name` | <strong><span style="color:green">✓</span></strong>
`created_at` | <strong><span style="color:green">✓</span></strong>
`closed_at` | <strong><span style="color:green">✓</span></strong>
`hiring_team.hiring_managers`| <strong><span style="color:green">✓</span></strong>
`hiring_team.recruiters`| <strong><span style="color:red">x</span></strong>

</details>

<details>
<summary><strong style="display:inline">Stages</strong></summary>

Field Name | Support
---- | -----
`id` | <strong><span style="color:green">✓</span></strong>
`job_id` | <strong><span style="color:red">x</span></strong>
`name` |<strong><span style="color:green">✓</span></strong>

</details>


<details>
<summary><strong style="display:inline">Offers</strong></summary>

Field Name | Support
---- | -----
`id` | <strong><span style="color:green">✓</span></strong>
`application_id` | <strong><span style="color:green">✓</span></strong>
`candidate_id` |<strong><span style="color:green">✓</span></strong>
`job_id` | <strong><span style="color:green">✓</span></strong>
`created_at` | <strong><span style="color:green">✓</span></strong>
`updated_at` | <strong><span style="color:red">x</span></strong>
`status`| <strong><span style="color:green">✓</span></strong>

</details>

<!-- type: tab-end -->

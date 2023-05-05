---
stoplight-id: wt41jy5q4l5z9
---

# ATS-Support

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
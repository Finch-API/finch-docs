---
stoplight-id: v3jzmsxospemd
---

# Gusto Field Support

<!-- theme: info -->

> <strong><span style="color:green">✓</span></strong> — supported
>
> <strong><span style="color:red">✗</span></strong> — not supported by Finch
>
> <strong><span>⚪️</span></strong> — not supported by provider system


### Company
Field Name | Support Status
--- | :-:
`id` | <strong><span style="color:green">✓</span></strong>
`legal_name` | <strong><span style="color:green">✓</span></strong>
`entity` | <strong><span style="color:green">✓</span></strong>
`entity.type` | <strong><span style="color:green">✓</span></strong>
`entity.subtype` | <strong><span style="color:green">✓</span></strong>
`primary_email` | <strong><span style="color:green">✓</span></strong>
`primary_phone_number` | <strong><span style="color:green">✓</span></strong>
`ein` | <strong><span style="color:green">✓</span></strong>
`departments`| <strong><span style="color:green">✓</span></strong>
`departments[].name`| <strong><span style="color:green">✓</span></strong>
`departments[].parent`| <strong><span style="color:green">✓</span></strong>
`departments[].parent.name`| <strong><span style="color:green">✓</span></strong>
`locations`| <strong><span style="color:green">✓</span></strong>
`locations.line1`| <strong><span style="color:green">✓</span></strong>
`locations.line2`| <strong><span style="color:green">✓</span></strong>
`locations.city`| <strong><span style="color:green">✓</span></strong>
`locations.state`| <strong><span style="color:green">✓</span></strong>
`locations.postal_code`| <strong><span style="color:green">✓</span></strong>
`locations.country`| <strong><span style="color:green">✓</span></strong>
`accounts`| <strong><span style="color:green">✓</span></strong>
`accounts[].routing_number`| <strong><span style="color:green">✓</span></strong>
`accounts[].account_name`| <strong><span style="color:red">✗</span></strong>
`accounts[].institution_name`| <strong><span style="color:green">✓</span></strong>
`accounts[].account_type`| <strong><span style="color:green">✓</span></strong>
`accounts[].account_number`| <strong><span style="color:green">✓</span></strong>

**Notes**
- `account_number` is masked in Gusto. Finch will only display the last four digits.

### Directory
Field Name | Support Status
---- | -----
`individuals[].id` | <strong><span style="color:green">✓</span></strong>
`individuals[].first_name` | <strong><span style="color:green">✓</span></strong>
`individuals[].middle_name` | <strong><span style="color:green">✓</span></strong>
`individuals[].last_name` | <strong><span style="color:green">✓</span></strong>
`individuals[].manager` | <strong><span style="color:green">✓</span></strong>
`individuals[].manager.id` | <strong><span style="color:green">✓</span></strong>
`individuals[].department`| <strong><span style="color:green">✓</span></strong>
`individuals[].department.name` | <strong><span style="color:green">✓</span></strong>
`individuals[].is_active` | <strong><span style="color:green">✓</span></strong>

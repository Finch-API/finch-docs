---
stoplight-id: 0517ab806dda4
---

# Census & Pay Support

Finch's API tries to maintain parity between all [providers](./Providers.md). However, every now and then, a provider may not support a specific data field (for example: job titles). This section outlines the compatibility of each data field per Automated API Integration and any other miscellaneous information that's important to know.

### ADP Workforce Now
<!--
type: tab
title: Credentials
-->
<details>
<summary><strong style="display:inline">Company</strong></summary>


  Field | Support
  ---- | -----
  `id` | <strong><span style="color:green">✓</span></strong>
  `legal_name` | <strong><span style="color:green">✓</span></strong>
  `entity.type` | <strong><span style="color:green">✓</span></strong>
  `entity.subtype` | <strong><span style="color:green">✓</span></strong>
  `primary_email` | <strong><span style="color:green">✓</span></strong>
  `primary_phone_number` | <strong><span style="color:green">✓</span></strong>
  `ein` | <strong><span style="color:green">✓</span></strong>
  `departments[]` | <strong><span style="color:green">✓</span></strong>
  `departments[].parent`| <strong><span style="color:green">✓</span></strong>
  `departments[].parent.name`| <strong><span style="color:green">✓</span></strong>
  `locations[].line1` |
  `locations[].line2` |
  `locations[].city` |
  `locations[].state` |
  `locations[].postal_code` |
  `locations[].country` |
  `accounts[].routing_number` |
  `accounts[].account_name` |
  `accounts[].institution_name` |
  `accounts[].account_type` |
  `accounts[].account_number` |

</details>

<details>
<summary><strong style="display:inline">Directory</strong></summary>

  Field | Support
  --- | ---
  `id` | <strong><span style="color:green">✓</span></strong>
  `first_name` | <strong><span style="color:green">✓</span></strong>
  `middle_name` | <strong><span style="color:green">✓</span></strong>
  `last_name` | <strong><span style="color:green">✓</span></strong>
  `manager.id` | <strong><span style="color:green">✓</span></strong>
  `department.name` | <strong><span style="color:green">✓</span></strong>
  `is_active` | <strong><span style="color:green">✓</span></strong>

</details>

<details>
<summary><strong style="display:inline">Individual</strong></summary>


  Field | Support
  --- | ---
  `id` | <strong><span style="color:green">✓</span></strong>
  `first_name` | <strong><span style="color:green">✓</span></strong>
  `middle_name` | <strong><span style="color:green">✓</span></strong>
  `last_name` | <strong><span style="color:green">✓</span></strong>
  `preferred_name` | <strong><span style="color:green">✓</span></strong>
  `emails[].data` | <strong><span style="color:green">✓</span></strong>
  `emails[].type` | <strong><span style="color:green">✓</span></strong>
  `phone_numbers[].data` | <strong><span style="color:green">✓</span></strong>
  `phone_numbers[].type` | <strong><span style="color:green">✓</span></strong>
  `dob` | <strong><span style="color:green">✓</span></strong>
  `residence.line1` | <strong><span style="color:green">✓</span></strong>
  `residence.line2` | <strong><span style="color:green">✓</span></strong>
  `residence.city` | <strong><span style="color:green">✓</span></strong>
  `residence.state` | <strong><span style="color:green">✓</span></strong>
  `residence.postal_code` | <strong><span style="color:green">✓</span></strong>
  `residence.country` | <strong><span style="color:green">✓</span></strong>
  `gender` | <strong><span style="color:green">✓</span></strong>
  `ethnicity` | <strong><span style="color:green">✓</span></strong>
  `ssn` | <strong><span style="color:green">✓</span></strong>

</details>

<details>
<summary><strong style="display:inline">Employment</strong></summary>


  Field | Support
  --- | ---
  `id` | <strong><span style="color:green">✓</span></strong>
  `first_name` | <strong><span style="color:green">✓</span></strong>
  `middle_name` | <strong><span style="color:green">✓</span></strong>
  `last_name` | <strong><span style="color:green">✓</span></strong>
  `title` | <strong><span style="color:green">✓</span></strong>
  `manager.id` | <strong><span style="color:green">✓</span></strong>
  `department.name` | <strong><span style="color:green">✓</span></strong>
  `employment.type` | <strong><span style="color:green">✓</span></strong>
  `employment.subtype` | <strong><span style="color:green">✓</span></strong>
  `start_date` | <strong><span style="color:green">✓</span></strong>
  `end_date` | <strong><span style="color:green">✓</span></strong>
  `is_active` | <strong><span style="color:green">✓</span></strong>
  `location.line1` | <strong><span style="color:green">✓</span></strong>
  `location.line2` | <strong><span style="color:green">✓</span></strong>
  `location.city` | <strong><span style="color:green">✓</span></strong>
  `location.state` | <strong><span style="color:green">✓</span></strong>
  `location.postal_code` | <strong><span style="color:green">✓</span></strong>
  `location.country` | <strong><span style="color:green">✓</span></strong>
  `income.unit` | <strong><span style="color:green">✓</span></strong>
  `income.amount` | <strong><span style="color:green">✓</span></strong>
  `income.currency` | <strong><span style="color:green">✓</span></strong>
  `income.history` | <strong><span style="color:green">✓</span></strong>
  `class_code` | <strong><span style="color:green">✓</span></strong>
  `custom_fields` | <strong><span style="color:green">✓</span></strong>

</details>

<details>
<summary><strong style="display:inline">Payment</strong></summary>


  Field | Support
  --- | ---
  `id` | <strong><span style="color:green">✓</span></strong>
  `pay_period.start_date` | <strong><span style="color:green">✓</span></strong>
  `pay_period.end_date` | <strong><span style="color:green">✓</span></strong>
  `pay_date` | <strong><span style="color:green">✓</span></strong>
  `debit_date` | <strong><span style="color:green">✓</span></strong>
  `company_debit` | <strong><span style="color:green">✓</span></strong>
  `gross_pay` | <strong><span style="color:green">✓</span></strong>
  `net_pay` | <strong><span style="color:green">✓</span></strong>
  `employer_taxes` | <strong><span style="color:green">✓</span></strong>
  `employee_taxes` | <strong><span style="color:green">✓</span></strong>
  `individual_ids` | <strong><span style="color:green">✓</span></strong>


</details>

<details>
<summary><strong style="display:inline">Pay Statement</strong></summary>


  Field | Support
  --- | ---
  `individual_id` | <strong><span style="color:green">✓</span></strong>
  `type` | <strong><span style="color:green">✓</span></strong>
  `payment_method` | <strong><span style="color:green">✓</span></strong>
  `total_hours` | <strong><span style="color:green">✓</span></strong>
  `gross_pay` | <strong><span style="color:green">✓</span></strong>
  `net_pay` | <strong><span style="color:green">✓</span></strong>
  `earnings.type` | <strong><span style="color:green">✓</span></strong>
  `earnings.name` | <strong><span style="color:green">✓</span></strong>
  `earnings.amount` | <strong><span style="color:green">✓</span></strong>
  `earnings.currency` | <strong><span style="color:green">✓</span></strong>
  `earnings.hours` | <strong><span style="color:green">✓</span></strong>
  `taxes.type` | <strong><span style="color:green">✓</span></strong>
  `taxes.name` | <strong><span style="color:green">✓</span></strong>
  `taxes.amount` | <strong><span style="color:green">✓</span></strong>
  `taxes.currency` | <strong><span style="color:green">✓</span></strong>
  `taxes.hours` | <strong><span style="color:green">✓</span></strong>
  `employee_deductions.type` | <strong><span style="color:green">✓</span></strong>
  `employee_deductions.name` | <strong><span style="color:green">✓</span></strong>
  `employee_deductions.amount` | <strong><span style="color:green">✓</span></strong>
  `employee_deductions.currency` | <strong><span style="color:green">✓</span></strong>
  `employee_deductions.pre_tax` | <strong><span style="color:green">✓</span></strong>
  `employer_contributions.type` | <strong><span style="color:green">✓</span></strong>
  `employer_contributions.name` | <strong><span style="color:green">✓</span></strong>
  `employer_contributions.amount` | <strong><span style="color:green">✓</span></strong>
  `employer_contributions.currency` | <strong><span style="color:green">✓</span></strong>

</details>

<!-- type: tab-end -->

### BambooHR
<!--
type: tab
title: Credentials
-->
<details>
<summary><strong style="display:inline">Company</strong></summary>


  Field | Support
  ---- | -----
  `id` | <strong><span style="color:green">✓</span></strong>
  `legal_name` | <strong><span style="color:green">✓</span></strong>
  `entity.type` | <strong><span style="color:green">✓</span></strong>
  `entity.subtype` | <strong><span style="color:green">✓</span></strong>
  `primary_email` | <strong><span style="color:green">✓</span></strong>
  `primary_phone_number` | <strong><span style="color:green">✓</span></strong>
  `ein` | <strong><span style="color:green">✓</span></strong>
  `departments[]` | <strong><span style="color:green">✓</span></strong>
  `departments[].parent`| <strong><span style="color:green">✓</span></strong>
  `departments[].parent.name`| <strong><span style="color:green">✓</span></strong>
  `locations[].line1` | <strong><span style="color:red">x</span></strong>
  `locations[].line2` | <strong><span style="color:red">x</span></strong>
  `locations[].city` | <strong><span style="color:red">x</span></strong>
  `locations[].state` |<strong><span style="color:red">x</span></strong>
  `locations[].postal_code` | <strong><span style="color:red">x</span></strong>
  `locations[].country` | <strong><span style="color:red">x</span></strong>
  `accounts[].routing_number` | <strong><span style="color:red">x</span></strong>
  `accounts[].account_name` | <strong><span style="color:red">x</span></strong>
  `accounts[].institution_name` | <strong><span style="color:red">x</span></strong>
  `accounts[].account_type` | <strong><span style="color:red">x</span></strong>
  `accounts[].account_number` | <strong><span style="color:red">x</span></strong>

</details>

<details>
<summary><strong style="display:inline">Directory</strong></summary>

  Field | Support
  --- | ---
  `id` | <strong><span style="color:green">✓</span></strong>
  `first_name` | <strong><span style="color:green">✓</span></strong>
  `middle_name` | <strong><span style="color:green">✓</span></strong>
  `last_name` | <strong><span style="color:green">✓</span></strong>
  `manager.id` | <strong><span style="color:green">✓</span></strong>
  `department.name` | <strong><span style="color:green">✓</span></strong>
  `is_active` | <strong><span style="color:green">✓</span></strong>

</details>

<details>
<summary><strong style="display:inline">Individual</strong></summary>


  Field | Support
  --- | ---
  `id` | <strong><span style="color:green">✓</span></strong>
  `first_name` | <strong><span style="color:green">✓</span></strong>
  `middle_name` | <strong><span style="color:green">✓</span></strong>
  `last_name` | <strong><span style="color:green">✓</span></strong>
  `manager.id` | <strong><span style="color:green">✓</span></strong>
  `department.name` | <strong><span style="color:green">✓</span></strong>
  `is_active` | <strong><span style="color:green">✓</span></strong>

</details>

<details>
<summary><strong style="display:inline">Employment</strong></summary>


  Field | Support
  --- | ---
  `id` | <strong><span style="color:green">✓</span></strong>
  `first_name` | <strong><span style="color:green">✓</span></strong>
  `middle_name` | <strong><span style="color:green">✓</span></strong>
  `last_name` | <strong><span style="color:green">✓</span></strong>
  `manager.id` | <strong><span style="color:green">✓</span></strong>
  `department.name` | <strong><span style="color:green">✓</span></strong>
  `is_active` | <strong><span style="color:green">✓</span></strong>

</details>

<details>
<summary><strong style="display:inline">Payment</strong></summary>


  Field | Support
  --- | ---
  `id` | <strong><span style="color:green">✓</span></strong>
  `first_name` | <strong><span style="color:green">✓</span></strong>
  `middle_name` | <strong><span style="color:green">✓</span></strong>
  `last_name` | <strong><span style="color:green">✓</span></strong>
  `manager.id` | <strong><span style="color:green">✓</span></strong>
  `department.name` | <strong><span style="color:green">✓</span></strong>
  `is_active` | <strong><span style="color:green">✓</span></strong>

</details>

<details>
<summary><strong style="display:inline">Pay Statement</strong></summary>


  Field | Support
  --- | ---
  `id` | <strong><span style="color:green">✓</span></strong>
  `first_name` | <strong><span style="color:green">✓</span></strong>
  `middle_name` | <strong><span style="color:green">✓</span></strong>
  `last_name` | <strong><span style="color:green">✓</span></strong>
  `manager.id` | <strong><span style="color:green">✓</span></strong>
  `department.name` | <strong><span style="color:green">✓</span></strong>
  `is_active` | <strong><span style="color:green">✓</span></strong>

</details>


<!--
type: tab
title: API
-->
<details>
<summary><strong style="display:inline">Company</strong></summary>


  Field | Support
  ---- | -----
  `id` | <strong><span style="color:green">✓</span></strong>
  `legal_name` | <strong><span style="color:green">✓</span></strong>
  `entity.type` | <strong><span style="color:green">✓</span></strong>
  `entity.subtype` | <strong><span style="color:green">✓</span></strong>
  `primary_email` | <strong><span style="color:green">✓</span></strong>
  `primary_phone_number` | <strong><span style="color:green">✓</span></strong>
  `ein` | <strong><span style="color:green">✓</span></strong>
  `departments[]` | <strong><span style="color:green">✓</span></strong>
  `departments[].parent`| <strong><span style="color:green">✓</span></strong>
  `departments[].parent.name`| <strong><span style="color:green">✓</span></strong>
  `locations[].line1` | <strong><span style="color:red">x</span></strong>
  `locations[].line2` | <strong><span style="color:red">x</span></strong>
  `locations[].city` | <strong><span style="color:red">x</span></strong>
  `locations[].state` |<strong><span style="color:red">x</span></strong>
  `locations[].postal_code` | <strong><span style="color:red">x</span></strong>
  `locations[].country` | <strong><span style="color:red">x</span></strong>
  `accounts[].routing_number` | <strong><span style="color:red">x</span></strong>
  `accounts[].account_name` | <strong><span style="color:red">x</span></strong>
  `accounts[].institution_name` | <strong><span style="color:red">x</span></strong>
  `accounts[].account_type` | <strong><span style="color:red">x</span></strong>
  `accounts[].account_number` | <strong><span style="color:red">x</span></strong>

</details>

<details>
<summary><strong style="display:inline">Directory</strong></summary>

  Field | Support
  --- | ---
  `id` | <strong><span style="color:green">✓</span></strong>
  `first_name` | <strong><span style="color:green">✓</span></strong>
  `middle_name` | <strong><span style="color:green">✓</span></strong>
  `last_name` | <strong><span style="color:green">✓</span></strong>
  `manager.id` | <strong><span style="color:green">✓</span></strong>
  `department.name` | <strong><span style="color:green">✓</span></strong>
  `is_active` | <strong><span style="color:green">✓</span></strong>

</details>

<details>
<summary><strong style="display:inline">Individual</strong></summary>


  Field | Support
  --- | ---
  `id` | <strong><span style="color:green">✓</span></strong>
  `first_name` | <strong><span style="color:green">✓</span></strong>
  `middle_name` | <strong><span style="color:green">✓</span></strong>
  `last_name` | <strong><span style="color:green">✓</span></strong>
  `manager.id` | <strong><span style="color:green">✓</span></strong>
  `department.name` | <strong><span style="color:green">✓</span></strong>
  `is_active` | <strong><span style="color:green">✓</span></strong>

</details>

<details>
<summary><strong style="display:inline">Employment</strong></summary>


  Field | Support
  --- | ---
  `id` | <strong><span style="color:green">✓</span></strong>
  `first_name` | <strong><span style="color:green">✓</span></strong>
  `middle_name` | <strong><span style="color:green">✓</span></strong>
  `last_name` | <strong><span style="color:green">✓</span></strong>
  `manager.id` | <strong><span style="color:green">✓</span></strong>
  `department.name` | <strong><span style="color:green">✓</span></strong>
  `is_active` | <strong><span style="color:green">✓</span></strong>

</details>

<details>
<summary><strong style="display:inline">Payment</strong></summary>


  Field | Support
  --- | ---
  `id` | <strong><span style="color:green">✓</span></strong>
  `first_name` | <strong><span style="color:green">✓</span></strong>
  `middle_name` | <strong><span style="color:green">✓</span></strong>
  `last_name` | <strong><span style="color:green">✓</span></strong>
  `manager.id` | <strong><span style="color:green">✓</span></strong>
  `department.name` | <strong><span style="color:green">✓</span></strong>
  `is_active` | <strong><span style="color:green">✓</span></strong>

</details>

<details>
<summary><strong style="display:inline">Pay Statement</strong></summary>


  Field | Support
  --- | ---
  `id` | <strong><span style="color:green">✓</span></strong>
  `first_name` | <strong><span style="color:green">✓</span></strong>
  `middle_name` | <strong><span style="color:green">✓</span></strong>
  `last_name` | <strong><span style="color:green">✓</span></strong>
  `manager.id` | <strong><span style="color:green">✓</span></strong>
  `department.name` | <strong><span style="color:green">✓</span></strong>
  `is_active` | <strong><span style="color:green">✓</span></strong>

</details>

<!-- type: tab-end -->

### Bob
<!--
type: tab
title: Credentials
-->
<details>
<summary><strong style="display:inline">Company</strong></summary>


  Field | Support
  ---- | -----
  `id` | <strong><span style="color:green">✓</span></strong>
  `legal_name` | <strong><span style="color:green">✓</span></strong>
  `entity.type` | <strong><span style="color:green">✓</span></strong>
  `entity.subtype` | <strong><span style="color:green">✓</span></strong>
  `primary_email` | <strong><span style="color:green">✓</span></strong>
  `primary_phone_number` | <strong><span style="color:green">✓</span></strong>
  `ein` | <strong><span style="color:green">✓</span></strong>
  `departments[]` | <strong><span style="color:green">✓</span></strong>
  `departments[].parent`| <strong><span style="color:green">✓</span></strong>
  `departments[].parent.name`| <strong><span style="color:green">✓</span></strong>
  `locations[].line1` | <strong><span style="color:red">x</span></strong>
  `locations[].line2` | <strong><span style="color:red">x</span></strong>
  `locations[].city` | <strong><span style="color:red">x</span></strong>
  `locations[].state` |<strong><span style="color:red">x</span></strong>
  `locations[].postal_code` | <strong><span style="color:red">x</span></strong>
  `locations[].country` | <strong><span style="color:red">x</span></strong>
  `accounts[].routing_number` | <strong><span style="color:red">x</span></strong>
  `accounts[].account_name` | <strong><span style="color:red">x</span></strong>
  `accounts[].institution_name` | <strong><span style="color:red">x</span></strong>
  `accounts[].account_type` | <strong><span style="color:red">x</span></strong>
  `accounts[].account_number` | <strong><span style="color:red">x</span></strong>

</details>

<details>
<summary><strong style="display:inline">Directory</strong></summary>

  Field | Support
  --- | ---
  `id` | <strong><span style="color:green">✓</span></strong>
  `first_name` | <strong><span style="color:green">✓</span></strong>
  `middle_name` | <strong><span style="color:green">✓</span></strong>
  `last_name` | <strong><span style="color:green">✓</span></strong>
  `manager.id` | <strong><span style="color:green">✓</span></strong>
  `department.name` | <strong><span style="color:green">✓</span></strong>
  `is_active` | <strong><span style="color:green">✓</span></strong>

</details>

<details>
<summary><strong style="display:inline">Individual</strong></summary>


  Field | Support
  --- | ---
  `id` | <strong><span style="color:green">✓</span></strong>
  `first_name` | <strong><span style="color:green">✓</span></strong>
  `middle_name` | <strong><span style="color:green">✓</span></strong>
  `last_name` | <strong><span style="color:green">✓</span></strong>
  `manager.id` | <strong><span style="color:green">✓</span></strong>
  `department.name` | <strong><span style="color:green">✓</span></strong>
  `is_active` | <strong><span style="color:green">✓</span></strong>

</details>

<details>
<summary><strong style="display:inline">Employment</strong></summary>


  Field | Support
  --- | ---
  `id` | <strong><span style="color:green">✓</span></strong>
  `first_name` | <strong><span style="color:green">✓</span></strong>
  `middle_name` | <strong><span style="color:green">✓</span></strong>
  `last_name` | <strong><span style="color:green">✓</span></strong>
  `manager.id` | <strong><span style="color:green">✓</span></strong>
  `department.name` | <strong><span style="color:green">✓</span></strong>
  `is_active` | <strong><span style="color:green">✓</span></strong>

</details>

<details>
<summary><strong style="display:inline">Payment</strong></summary>


  Field | Support
  --- | ---
  `id` | <strong><span style="color:green">✓</span></strong>
  `first_name` | <strong><span style="color:green">✓</span></strong>
  `middle_name` | <strong><span style="color:green">✓</span></strong>
  `last_name` | <strong><span style="color:green">✓</span></strong>
  `manager.id` | <strong><span style="color:green">✓</span></strong>
  `department.name` | <strong><span style="color:green">✓</span></strong>
  `is_active` | <strong><span style="color:green">✓</span></strong>

</details>

<details>
<summary><strong style="display:inline">Pay Statement</strong></summary>


  Field | Support
  --- | ---
  `id` | <strong><span style="color:green">✓</span></strong>
  `first_name` | <strong><span style="color:green">✓</span></strong>
  `middle_name` | <strong><span style="color:green">✓</span></strong>
  `last_name` | <strong><span style="color:green">✓</span></strong>
  `manager.id` | <strong><span style="color:green">✓</span></strong>
  `department.name` | <strong><span style="color:green">✓</span></strong>
  `is_active` | <strong><span style="color:green">✓</span></strong>

</details>

<!--
type: tab
title: API
-->
<details>
<summary><strong style="display:inline">Company</strong></summary>


  Field | Support
  ---- | -----
  `id` | <strong><span style="color:green">✓</span></strong>
  `legal_name` | <strong><span style="color:green">✓</span></strong>
  `entity.type` | <strong><span style="color:green">✓</span></strong>
  `entity.subtype` | <strong><span style="color:green">✓</span></strong>
  `primary_email` | <strong><span style="color:green">✓</span></strong>
  `primary_phone_number` | <strong><span style="color:green">✓</span></strong>
  `ein` | <strong><span style="color:green">✓</span></strong>
  `departments[]` | <strong><span style="color:green">✓</span></strong>
  `departments[].parent`| <strong><span style="color:green">✓</span></strong>
  `departments[].parent.name`| <strong><span style="color:green">✓</span></strong>
  `locations[].line1` | <strong><span style="color:red">x</span></strong>
  `locations[].line2` | <strong><span style="color:red">x</span></strong>
  `locations[].city` | <strong><span style="color:red">x</span></strong>
  `locations[].state` |<strong><span style="color:red">x</span></strong>
  `locations[].postal_code` | <strong><span style="color:red">x</span></strong>
  `locations[].country` | <strong><span style="color:red">x</span></strong>
  `accounts[].routing_number` | <strong><span style="color:red">x</span></strong>
  `accounts[].account_name` | <strong><span style="color:red">x</span></strong>
  `accounts[].institution_name` | <strong><span style="color:red">x</span></strong>
  `accounts[].account_type` | <strong><span style="color:red">x</span></strong>
  `accounts[].account_number` | <strong><span style="color:red">x</span></strong>

</details>

<details>
<summary><strong style="display:inline">Directory</strong></summary>

  Field | Support
  --- | ---
  `id` | <strong><span style="color:green">✓</span></strong>
  `first_name` | <strong><span style="color:green">✓</span></strong>
  `middle_name` | <strong><span style="color:green">✓</span></strong>
  `last_name` | <strong><span style="color:green">✓</span></strong>
  `manager.id` | <strong><span style="color:green">✓</span></strong>
  `department.name` | <strong><span style="color:green">✓</span></strong>
  `is_active` | <strong><span style="color:green">✓</span></strong>

</details>

<details>
<summary><strong style="display:inline">Individual</strong></summary>


  Field | Support
  --- | ---
  `id` | <strong><span style="color:green">✓</span></strong>
  `first_name` | <strong><span style="color:green">✓</span></strong>
  `middle_name` | <strong><span style="color:green">✓</span></strong>
  `last_name` | <strong><span style="color:green">✓</span></strong>
  `manager.id` | <strong><span style="color:green">✓</span></strong>
  `department.name` | <strong><span style="color:green">✓</span></strong>
  `is_active` | <strong><span style="color:green">✓</span></strong>

</details>

<details>
<summary><strong style="display:inline">Employment</strong></summary>


  Field | Support
  --- | ---
  `id` | <strong><span style="color:green">✓</span></strong>
  `first_name` | <strong><span style="color:green">✓</span></strong>
  `middle_name` | <strong><span style="color:green">✓</span></strong>
  `last_name` | <strong><span style="color:green">✓</span></strong>
  `manager.id` | <strong><span style="color:green">✓</span></strong>
  `department.name` | <strong><span style="color:green">✓</span></strong>
  `is_active` | <strong><span style="color:green">✓</span></strong>

</details>

<details>
<summary><strong style="display:inline">Payment</strong></summary>


  Field | Support
  --- | ---
  `id` | <strong><span style="color:green">✓</span></strong>
  `first_name` | <strong><span style="color:green">✓</span></strong>
  `middle_name` | <strong><span style="color:green">✓</span></strong>
  `last_name` | <strong><span style="color:green">✓</span></strong>
  `manager.id` | <strong><span style="color:green">✓</span></strong>
  `department.name` | <strong><span style="color:green">✓</span></strong>
  `is_active` | <strong><span style="color:green">✓</span></strong>

</details>

<details>
<summary><strong style="display:inline">Pay Statement</strong></summary>


  Field | Support
  --- | ---
  `id` | <strong><span style="color:green">✓</span></strong>
  `first_name` | <strong><span style="color:green">✓</span></strong>
  `middle_name` | <strong><span style="color:green">✓</span></strong>
  `last_name` | <strong><span style="color:green">✓</span></strong>
  `manager.id` | <strong><span style="color:green">✓</span></strong>
  `department.name` | <strong><span style="color:green">✓</span></strong>
  `is_active` | <strong><span style="color:green">✓</span></strong>

</details>

<!-- type: tab-end -->

### Gusto
<!--
type: tab
title: Credentials
-->
<details>
<summary><strong style="display:inline">Company</strong></summary>


  Field | Support
  ---- | -----
  `id` | <strong><span style="color:green">✓</span></strong>
  `legal_name` | <strong><span style="color:green">✓</span></strong>
  `entity.type` | <strong><span style="color:green">✓</span></strong>
  `entity.subtype` | <strong><span style="color:green">✓</span></strong>
  `primary_email` | <strong><span style="color:green">✓</span></strong>
  `primary_phone_number` | <strong><span style="color:green">✓</span></strong>
  `ein` | <strong><span style="color:green">✓</span></strong>
  `departments[]` | <strong><span style="color:green">✓</span></strong>
  `departments[].parent`| <strong><span style="color:green">✓</span></strong>
  `departments[].parent.name`| <strong><span style="color:green">✓</span></strong>
  `locations[].line1` | <strong><span style="color:red">x</span></strong>
  `locations[].line2` | <strong><span style="color:red">x</span></strong>
  `locations[].city` | <strong><span style="color:red">x</span></strong>
  `locations[].state` |<strong><span style="color:red">x</span></strong>
  `locations[].postal_code` | <strong><span style="color:red">x</span></strong>
  `locations[].country` | <strong><span style="color:red">x</span></strong>
  `accounts[].routing_number` | <strong><span style="color:red">x</span></strong>
  `accounts[].account_name` | <strong><span style="color:red">x</span></strong>
  `accounts[].institution_name` | <strong><span style="color:red">x</span></strong>
  `accounts[].account_type` | <strong><span style="color:red">x</span></strong>
  `accounts[].account_number` | <strong><span style="color:red">x</span></strong>

</details>

<details>
<summary><strong style="display:inline">Directory</strong></summary>

  Field | Support
  --- | ---
  `id` | <strong><span style="color:green">✓</span></strong>
  `first_name` | <strong><span style="color:green">✓</span></strong>
  `middle_name` | <strong><span style="color:green">✓</span></strong>
  `last_name` | <strong><span style="color:green">✓</span></strong>
  `manager.id` | <strong><span style="color:green">✓</span></strong>
  `department.name` | <strong><span style="color:green">✓</span></strong>
  `is_active` | <strong><span style="color:green">✓</span></strong>

</details>

<details>
<summary><strong style="display:inline">Individual</strong></summary>


  Field | Support
  --- | ---
  `id` | <strong><span style="color:green">✓</span></strong>
  `first_name` | <strong><span style="color:green">✓</span></strong>
  `middle_name` | <strong><span style="color:green">✓</span></strong>
  `last_name` | <strong><span style="color:green">✓</span></strong>
  `manager.id` | <strong><span style="color:green">✓</span></strong>
  `department.name` | <strong><span style="color:green">✓</span></strong>
  `is_active` | <strong><span style="color:green">✓</span></strong>

</details>

<details>
<summary><strong style="display:inline">Employment</strong></summary>


  Field | Support
  --- | ---
  `id` | <strong><span style="color:green">✓</span></strong>
  `first_name` | <strong><span style="color:green">✓</span></strong>
  `middle_name` | <strong><span style="color:green">✓</span></strong>
  `last_name` | <strong><span style="color:green">✓</span></strong>
  `manager.id` | <strong><span style="color:green">✓</span></strong>
  `department.name` | <strong><span style="color:green">✓</span></strong>
  `is_active` | <strong><span style="color:green">✓</span></strong>

</details>

<details>
<summary><strong style="display:inline">Payment</strong></summary>


  Field | Support
  --- | ---
  `id` | <strong><span style="color:green">✓</span></strong>
  `first_name` | <strong><span style="color:green">✓</span></strong>
  `middle_name` | <strong><span style="color:green">✓</span></strong>
  `last_name` | <strong><span style="color:green">✓</span></strong>
  `manager.id` | <strong><span style="color:green">✓</span></strong>
  `department.name` | <strong><span style="color:green">✓</span></strong>
  `is_active` | <strong><span style="color:green">✓</span></strong>

</details>

<details>
<summary><strong style="display:inline">Pay Statement</strong></summary>


  Field | Support
  --- | ---
  `id` | <strong><span style="color:green">✓</span></strong>
  `first_name` | <strong><span style="color:green">✓</span></strong>
  `middle_name` | <strong><span style="color:green">✓</span></strong>
  `last_name` | <strong><span style="color:green">✓</span></strong>
  `manager.id` | <strong><span style="color:green">✓</span></strong>
  `department.name` | <strong><span style="color:green">✓</span></strong>
  `is_active` | <strong><span style="color:green">✓</span></strong>

</details>

<!-- type: tab-end -->

### Humaans
<!--
type: tab
title: API
-->
<details>
<summary><strong style="display:inline">Company</strong></summary>


  Field | Support
  ---- | -----
  `id` | <strong><span style="color:green">✓</span></strong>
  `legal_name` | <strong><span style="color:green">✓</span></strong>
  `entity.type` | <strong><span style="color:green">✓</span></strong>
  `entity.subtype` | <strong><span style="color:green">✓</span></strong>
  `primary_email` | <strong><span style="color:green">✓</span></strong>
  `primary_phone_number` | <strong><span style="color:green">✓</span></strong>
  `ein` | <strong><span style="color:green">✓</span></strong>
  `departments[]` | <strong><span style="color:green">✓</span></strong>
  `departments[].parent`| <strong><span style="color:green">✓</span></strong>
  `departments[].parent.name`| <strong><span style="color:green">✓</span></strong>
  `locations[].line1` | <strong><span style="color:red">x</span></strong>
  `locations[].line2` | <strong><span style="color:red">x</span></strong>
  `locations[].city` | <strong><span style="color:red">x</span></strong>
  `locations[].state` |<strong><span style="color:red">x</span></strong>
  `locations[].postal_code` | <strong><span style="color:red">x</span></strong>
  `locations[].country` | <strong><span style="color:red">x</span></strong>
  `accounts[].routing_number` | <strong><span style="color:red">x</span></strong>
  `accounts[].account_name` | <strong><span style="color:red">x</span></strong>
  `accounts[].institution_name` | <strong><span style="color:red">x</span></strong>
  `accounts[].account_type` | <strong><span style="color:red">x</span></strong>
  `accounts[].account_number` | <strong><span style="color:red">x</span></strong>

</details>

<details>
<summary><strong style="display:inline">Directory</strong></summary>

  Field | Support
  --- | ---
  `id` | <strong><span style="color:green">✓</span></strong>
  `first_name` | <strong><span style="color:green">✓</span></strong>
  `middle_name` | <strong><span style="color:green">✓</span></strong>
  `last_name` | <strong><span style="color:green">✓</span></strong>
  `manager.id` | <strong><span style="color:green">✓</span></strong>
  `department.name` | <strong><span style="color:green">✓</span></strong>
  `is_active` | <strong><span style="color:green">✓</span></strong>

</details>

<details>
<summary><strong style="display:inline">Individual</strong></summary>


  Field | Support
  --- | ---
  `id` | <strong><span style="color:green">✓</span></strong>
  `first_name` | <strong><span style="color:green">✓</span></strong>
  `middle_name` | <strong><span style="color:green">✓</span></strong>
  `last_name` | <strong><span style="color:green">✓</span></strong>
  `manager.id` | <strong><span style="color:green">✓</span></strong>
  `department.name` | <strong><span style="color:green">✓</span></strong>
  `is_active` | <strong><span style="color:green">✓</span></strong>

</details>

<details>
<summary><strong style="display:inline">Employment</strong></summary>


  Field | Support
  --- | ---
  `id` | <strong><span style="color:green">✓</span></strong>
  `first_name` | <strong><span style="color:green">✓</span></strong>
  `middle_name` | <strong><span style="color:green">✓</span></strong>
  `last_name` | <strong><span style="color:green">✓</span></strong>
  `manager.id` | <strong><span style="color:green">✓</span></strong>
  `department.name` | <strong><span style="color:green">✓</span></strong>
  `is_active` | <strong><span style="color:green">✓</span></strong>

</details>

<details>
<summary><strong style="display:inline">Payment</strong></summary>


  Field | Support
  --- | ---
  `id` | <strong><span style="color:green">✓</span></strong>
  `first_name` | <strong><span style="color:green">✓</span></strong>
  `middle_name` | <strong><span style="color:green">✓</span></strong>
  `last_name` | <strong><span style="color:green">✓</span></strong>
  `manager.id` | <strong><span style="color:green">✓</span></strong>
  `department.name` | <strong><span style="color:green">✓</span></strong>
  `is_active` | <strong><span style="color:green">✓</span></strong>

</details>

<details>
<summary><strong style="display:inline">Pay Statement</strong></summary>


  Field | Support
  --- | ---
  `id` | <strong><span style="color:green">✓</span></strong>
  `first_name` | <strong><span style="color:green">✓</span></strong>
  `middle_name` | <strong><span style="color:green">✓</span></strong>
  `last_name` | <strong><span style="color:green">✓</span></strong>
  `manager.id` | <strong><span style="color:green">✓</span></strong>
  `department.name` | <strong><span style="color:green">✓</span></strong>
  `is_active` | <strong><span style="color:green">✓</span></strong>

</details>

<!-- type: tab-end -->

### Insperity`
<!--
type: tab
title: Credentials
-->
<details>
<summary><strong style="display:inline">Company</strong></summary>


  Field | Support
  ---- | -----
  `id` | <strong><span style="color:green">✓</span></strong>
  `legal_name` | <strong><span style="color:green">✓</span></strong>
  `entity.type` | <strong><span style="color:green">✓</span></strong>
  `entity.subtype` | <strong><span style="color:green">✓</span></strong>
  `primary_email` | <strong><span style="color:green">✓</span></strong>
  `primary_phone_number` | <strong><span style="color:green">✓</span></strong>
  `ein` | <strong><span style="color:green">✓</span></strong>
  `departments[]` | <strong><span style="color:green">✓</span></strong>
  `departments[].parent`| <strong><span style="color:green">✓</span></strong>
  `departments[].parent.name`| <strong><span style="color:green">✓</span></strong>
  `locations[].line1` | <strong><span style="color:red">x</span></strong>
  `locations[].line2` | <strong><span style="color:red">x</span></strong>
  `locations[].city` | <strong><span style="color:red">x</span></strong>
  `locations[].state` |<strong><span style="color:red">x</span></strong>
  `locations[].postal_code` | <strong><span style="color:red">x</span></strong>
  `locations[].country` | <strong><span style="color:red">x</span></strong>
  `accounts[].routing_number` | <strong><span style="color:red">x</span></strong>
  `accounts[].account_name` | <strong><span style="color:red">x</span></strong>
  `accounts[].institution_name` | <strong><span style="color:red">x</span></strong>
  `accounts[].account_type` | <strong><span style="color:red">x</span></strong>
  `accounts[].account_number` | <strong><span style="color:red">x</span></strong>

</details>

<details>
<summary><strong style="display:inline">Directory</strong></summary>

  Field | Support
  --- | ---
  `id` | <strong><span style="color:green">✓</span></strong>
  `first_name` | <strong><span style="color:green">✓</span></strong>
  `middle_name` | <strong><span style="color:green">✓</span></strong>
  `last_name` | <strong><span style="color:green">✓</span></strong>
  `manager.id` | <strong><span style="color:green">✓</span></strong>
  `department.name` | <strong><span style="color:green">✓</span></strong>
  `is_active` | <strong><span style="color:green">✓</span></strong>

</details>

<details>
<summary><strong style="display:inline">Individual</strong></summary>


  Field | Support
  --- | ---
  `id` | <strong><span style="color:green">✓</span></strong>
  `first_name` | <strong><span style="color:green">✓</span></strong>
  `middle_name` | <strong><span style="color:green">✓</span></strong>
  `last_name` | <strong><span style="color:green">✓</span></strong>
  `manager.id` | <strong><span style="color:green">✓</span></strong>
  `department.name` | <strong><span style="color:green">✓</span></strong>
  `is_active` | <strong><span style="color:green">✓</span></strong>

</details>

<details>
<summary><strong style="display:inline">Employment</strong></summary>


  Field | Support
  --- | ---
  `id` | <strong><span style="color:green">✓</span></strong>
  `first_name` | <strong><span style="color:green">✓</span></strong>
  `middle_name` | <strong><span style="color:green">✓</span></strong>
  `last_name` | <strong><span style="color:green">✓</span></strong>
  `manager.id` | <strong><span style="color:green">✓</span></strong>
  `department.name` | <strong><span style="color:green">✓</span></strong>
  `is_active` | <strong><span style="color:green">✓</span></strong>

</details>

<details>
<summary><strong style="display:inline">Payment</strong></summary>


  Field | Support
  --- | ---
  `id` | <strong><span style="color:green">✓</span></strong>
  `first_name` | <strong><span style="color:green">✓</span></strong>
  `middle_name` | <strong><span style="color:green">✓</span></strong>
  `last_name` | <strong><span style="color:green">✓</span></strong>
  `manager.id` | <strong><span style="color:green">✓</span></strong>
  `department.name` | <strong><span style="color:green">✓</span></strong>
  `is_active` | <strong><span style="color:green">✓</span></strong>

</details>

<details>
<summary><strong style="display:inline">Pay Statement</strong></summary>


  Field | Support
  --- | ---
  `id` | <strong><span style="color:green">✓</span></strong>
  `first_name` | <strong><span style="color:green">✓</span></strong>
  `middle_name` | <strong><span style="color:green">✓</span></strong>
  `last_name` | <strong><span style="color:green">✓</span></strong>
  `manager.id` | <strong><span style="color:green">✓</span></strong>
  `department.name` | <strong><span style="color:green">✓</span></strong>
  `is_active` | <strong><span style="color:green">✓</span></strong>

</details>

<!--
type: tab
title: API
-->
<details>
<summary><strong style="display:inline">Company</strong></summary>


  Field | Support
  ---- | -----
  `id` | <strong><span style="color:green">✓</span></strong>
  `legal_name` | <strong><span style="color:green">✓</span></strong>
  `entity.type` | <strong><span style="color:green">✓</span></strong>
  `entity.subtype` | <strong><span style="color:green">✓</span></strong>
  `primary_email` | <strong><span style="color:green">✓</span></strong>
  `primary_phone_number` | <strong><span style="color:green">✓</span></strong>
  `ein` | <strong><span style="color:green">✓</span></strong>
  `departments[]` | <strong><span style="color:green">✓</span></strong>
  `departments[].parent`| <strong><span style="color:green">✓</span></strong>
  `departments[].parent.name`| <strong><span style="color:green">✓</span></strong>
  `locations[].line1` | <strong><span style="color:red">x</span></strong>
  `locations[].line2` | <strong><span style="color:red">x</span></strong>
  `locations[].city` | <strong><span style="color:red">x</span></strong>
  `locations[].state` |<strong><span style="color:red">x</span></strong>
  `locations[].postal_code` | <strong><span style="color:red">x</span></strong>
  `locations[].country` | <strong><span style="color:red">x</span></strong>
  `accounts[].routing_number` | <strong><span style="color:red">x</span></strong>
  `accounts[].account_name` | <strong><span style="color:red">x</span></strong>
  `accounts[].institution_name` | <strong><span style="color:red">x</span></strong>
  `accounts[].account_type` | <strong><span style="color:red">x</span></strong>
  `accounts[].account_number` | <strong><span style="color:red">x</span></strong>

</details>

<details>
<summary><strong style="display:inline">Directory</strong></summary>

  Field | Support
  --- | ---
  `id` | <strong><span style="color:green">✓</span></strong>
  `first_name` | <strong><span style="color:green">✓</span></strong>
  `middle_name` | <strong><span style="color:green">✓</span></strong>
  `last_name` | <strong><span style="color:green">✓</span></strong>
  `manager.id` | <strong><span style="color:green">✓</span></strong>
  `department.name` | <strong><span style="color:green">✓</span></strong>
  `is_active` | <strong><span style="color:green">✓</span></strong>

</details>

<details>
<summary><strong style="display:inline">Individual</strong></summary>


  Field | Support
  --- | ---
  `id` | <strong><span style="color:green">✓</span></strong>
  `first_name` | <strong><span style="color:green">✓</span></strong>
  `middle_name` | <strong><span style="color:green">✓</span></strong>
  `last_name` | <strong><span style="color:green">✓</span></strong>
  `manager.id` | <strong><span style="color:green">✓</span></strong>
  `department.name` | <strong><span style="color:green">✓</span></strong>
  `is_active` | <strong><span style="color:green">✓</span></strong>

</details>

<details>
<summary><strong style="display:inline">Employment</strong></summary>


  Field | Support
  --- | ---
  `id` | <strong><span style="color:green">✓</span></strong>
  `first_name` | <strong><span style="color:green">✓</span></strong>
  `middle_name` | <strong><span style="color:green">✓</span></strong>
  `last_name` | <strong><span style="color:green">✓</span></strong>
  `manager.id` | <strong><span style="color:green">✓</span></strong>
  `department.name` | <strong><span style="color:green">✓</span></strong>
  `is_active` | <strong><span style="color:green">✓</span></strong>

</details>

<details>
<summary><strong style="display:inline">Payment</strong></summary>


  Field | Support
  --- | ---
  `id` | <strong><span style="color:green">✓</span></strong>
  `first_name` | <strong><span style="color:green">✓</span></strong>
  `middle_name` | <strong><span style="color:green">✓</span></strong>
  `last_name` | <strong><span style="color:green">✓</span></strong>
  `manager.id` | <strong><span style="color:green">✓</span></strong>
  `department.name` | <strong><span style="color:green">✓</span></strong>
  `is_active` | <strong><span style="color:green">✓</span></strong>

</details>

<details>
<summary><strong style="display:inline">Pay Statement</strong></summary>


  Field | Support
  --- | ---
  `id` | <strong><span style="color:green">✓</span></strong>
  `first_name` | <strong><span style="color:green">✓</span></strong>
  `middle_name` | <strong><span style="color:green">✓</span></strong>
  `last_name` | <strong><span style="color:green">✓</span></strong>
  `manager.id` | <strong><span style="color:green">✓</span></strong>
  `department.name` | <strong><span style="color:green">✓</span></strong>
  `is_active` | <strong><span style="color:green">✓</span></strong>

</details>

<!-- type: tab-end -->

### Justworks
<!--
type: tab
title: Credentials
-->
<details>
<summary><strong style="display:inline">Company</strong></summary>


  Field | Support
  ---- | -----
  `id` | <strong><span style="color:green">✓</span></strong>
  `legal_name` | <strong><span style="color:green">✓</span></strong>
  `entity.type` | <strong><span style="color:green">✓</span></strong>
  `entity.subtype` | <strong><span style="color:green">✓</span></strong>
  `primary_email` | <strong><span style="color:green">✓</span></strong>
  `primary_phone_number` | <strong><span style="color:green">✓</span></strong>
  `ein` | <strong><span style="color:green">✓</span></strong>
  `departments[]` | <strong><span style="color:green">✓</span></strong>
  `departments[].parent`| <strong><span style="color:green">✓</span></strong>
  `departments[].parent.name`| <strong><span style="color:green">✓</span></strong>
  `locations[].line1` | <strong><span style="color:red">x</span></strong>
  `locations[].line2` | <strong><span style="color:red">x</span></strong>
  `locations[].city` | <strong><span style="color:red">x</span></strong>
  `locations[].state` |<strong><span style="color:red">x</span></strong>
  `locations[].postal_code` | <strong><span style="color:red">x</span></strong>
  `locations[].country` | <strong><span style="color:red">x</span></strong>
  `accounts[].routing_number` | <strong><span style="color:red">x</span></strong>
  `accounts[].account_name` | <strong><span style="color:red">x</span></strong>
  `accounts[].institution_name` | <strong><span style="color:red">x</span></strong>
  `accounts[].account_type` | <strong><span style="color:red">x</span></strong>
  `accounts[].account_number` | <strong><span style="color:red">x</span></strong>

</details>

<details>
<summary><strong style="display:inline">Directory</strong></summary>

  Field | Support
  --- | ---
  `id` | <strong><span style="color:green">✓</span></strong>
  `first_name` | <strong><span style="color:green">✓</span></strong>
  `middle_name` | <strong><span style="color:green">✓</span></strong>
  `last_name` | <strong><span style="color:green">✓</span></strong>
  `manager.id` | <strong><span style="color:green">✓</span></strong>
  `department.name` | <strong><span style="color:green">✓</span></strong>
  `is_active` | <strong><span style="color:green">✓</span></strong>

</details>

<details>
<summary><strong style="display:inline">Individual</strong></summary>


  Field | Support
  --- | ---
  `id` | <strong><span style="color:green">✓</span></strong>
  `first_name` | <strong><span style="color:green">✓</span></strong>
  `middle_name` | <strong><span style="color:green">✓</span></strong>
  `last_name` | <strong><span style="color:green">✓</span></strong>
  `manager.id` | <strong><span style="color:green">✓</span></strong>
  `department.name` | <strong><span style="color:green">✓</span></strong>
  `is_active` | <strong><span style="color:green">✓</span></strong>

</details>

<details>
<summary><strong style="display:inline">Employment</strong></summary>


  Field | Support
  --- | ---
  `id` | <strong><span style="color:green">✓</span></strong>
  `first_name` | <strong><span style="color:green">✓</span></strong>
  `middle_name` | <strong><span style="color:green">✓</span></strong>
  `last_name` | <strong><span style="color:green">✓</span></strong>
  `manager.id` | <strong><span style="color:green">✓</span></strong>
  `department.name` | <strong><span style="color:green">✓</span></strong>
  `is_active` | <strong><span style="color:green">✓</span></strong>

</details>

<details>
<summary><strong style="display:inline">Payment</strong></summary>


  Field | Support
  --- | ---
  `id` | <strong><span style="color:green">✓</span></strong>
  `first_name` | <strong><span style="color:green">✓</span></strong>
  `middle_name` | <strong><span style="color:green">✓</span></strong>
  `last_name` | <strong><span style="color:green">✓</span></strong>
  `manager.id` | <strong><span style="color:green">✓</span></strong>
  `department.name` | <strong><span style="color:green">✓</span></strong>
  `is_active` | <strong><span style="color:green">✓</span></strong>

</details>

<details>
<summary><strong style="display:inline">Pay Statement</strong></summary>


  Field | Support
  --- | ---
  `id` | <strong><span style="color:green">✓</span></strong>
  `first_name` | <strong><span style="color:green">✓</span></strong>
  `middle_name` | <strong><span style="color:green">✓</span></strong>
  `last_name` | <strong><span style="color:green">✓</span></strong>
  `manager.id` | <strong><span style="color:green">✓</span></strong>
  `department.name` | <strong><span style="color:green">✓</span></strong>
  `is_active` | <strong><span style="color:green">✓</span></strong>

</details>

<!-- type: tab-end -->

### Namely
<!--
type: tab
title: Credentials
-->
<details>
<summary><strong style="display:inline">Company</strong></summary>


  Field | Support
  ---- | -----
  `id` | <strong><span style="color:green">✓</span></strong>
  `legal_name` | <strong><span style="color:green">✓</span></strong>
  `entity.type` | <strong><span style="color:green">✓</span></strong>
  `entity.subtype` | <strong><span style="color:green">✓</span></strong>
  `primary_email` | <strong><span style="color:green">✓</span></strong>
  `primary_phone_number` | <strong><span style="color:green">✓</span></strong>
  `ein` | <strong><span style="color:green">✓</span></strong>
  `departments[]` | <strong><span style="color:green">✓</span></strong>
  `departments[].parent`| <strong><span style="color:green">✓</span></strong>
  `departments[].parent.name`| <strong><span style="color:green">✓</span></strong>
  `locations[].line1` | <strong><span style="color:red">x</span></strong>
  `locations[].line2` | <strong><span style="color:red">x</span></strong>
  `locations[].city` | <strong><span style="color:red">x</span></strong>
  `locations[].state` |<strong><span style="color:red">x</span></strong>
  `locations[].postal_code` | <strong><span style="color:red">x</span></strong>
  `locations[].country` | <strong><span style="color:red">x</span></strong>
  `accounts[].routing_number` | <strong><span style="color:red">x</span></strong>
  `accounts[].account_name` | <strong><span style="color:red">x</span></strong>
  `accounts[].institution_name` | <strong><span style="color:red">x</span></strong>
  `accounts[].account_type` | <strong><span style="color:red">x</span></strong>
  `accounts[].account_number` | <strong><span style="color:red">x</span></strong>

</details>

<details>
<summary><strong style="display:inline">Directory</strong></summary>

  Field | Support
  --- | ---
  `id` | <strong><span style="color:green">✓</span></strong>
  `first_name` | <strong><span style="color:green">✓</span></strong>
  `middle_name` | <strong><span style="color:green">✓</span></strong>
  `last_name` | <strong><span style="color:green">✓</span></strong>
  `manager.id` | <strong><span style="color:green">✓</span></strong>
  `department.name` | <strong><span style="color:green">✓</span></strong>
  `is_active` | <strong><span style="color:green">✓</span></strong>

</details>

<details>
<summary><strong style="display:inline">Individual</strong></summary>


  Field | Support
  --- | ---
  `id` | <strong><span style="color:green">✓</span></strong>
  `first_name` | <strong><span style="color:green">✓</span></strong>
  `middle_name` | <strong><span style="color:green">✓</span></strong>
  `last_name` | <strong><span style="color:green">✓</span></strong>
  `manager.id` | <strong><span style="color:green">✓</span></strong>
  `department.name` | <strong><span style="color:green">✓</span></strong>
  `is_active` | <strong><span style="color:green">✓</span></strong>

</details>

<details>
<summary><strong style="display:inline">Employment</strong></summary>


  Field | Support
  --- | ---
  `id` | <strong><span style="color:green">✓</span></strong>
  `first_name` | <strong><span style="color:green">✓</span></strong>
  `middle_name` | <strong><span style="color:green">✓</span></strong>
  `last_name` | <strong><span style="color:green">✓</span></strong>
  `manager.id` | <strong><span style="color:green">✓</span></strong>
  `department.name` | <strong><span style="color:green">✓</span></strong>
  `is_active` | <strong><span style="color:green">✓</span></strong>

</details>

<details>
<summary><strong style="display:inline">Payment</strong></summary>


  Field | Support
  --- | ---
  `id` | <strong><span style="color:green">✓</span></strong>
  `first_name` | <strong><span style="color:green">✓</span></strong>
  `middle_name` | <strong><span style="color:green">✓</span></strong>
  `last_name` | <strong><span style="color:green">✓</span></strong>
  `manager.id` | <strong><span style="color:green">✓</span></strong>
  `department.name` | <strong><span style="color:green">✓</span></strong>
  `is_active` | <strong><span style="color:green">✓</span></strong>

</details>

<details>
<summary><strong style="display:inline">Pay Statement</strong></summary>


  Field | Support
  --- | ---
  `id` | <strong><span style="color:green">✓</span></strong>
  `first_name` | <strong><span style="color:green">✓</span></strong>
  `middle_name` | <strong><span style="color:green">✓</span></strong>
  `last_name` | <strong><span style="color:green">✓</span></strong>
  `manager.id` | <strong><span style="color:green">✓</span></strong>
  `department.name` | <strong><span style="color:green">✓</span></strong>
  `is_active` | <strong><span style="color:green">✓</span></strong>

</details>

<!--
type: tab
title: API
-->
<details>
<summary><strong style="display:inline">Company</strong></summary>


  Field | Support
  ---- | -----
  `id` | <strong><span style="color:green">✓</span></strong>
  `legal_name` | <strong><span style="color:green">✓</span></strong>
  `entity.type` | <strong><span style="color:green">✓</span></strong>
  `entity.subtype` | <strong><span style="color:green">✓</span></strong>
  `primary_email` | <strong><span style="color:green">✓</span></strong>
  `primary_phone_number` | <strong><span style="color:green">✓</span></strong>
  `ein` | <strong><span style="color:green">✓</span></strong>
  `departments[]` | <strong><span style="color:green">✓</span></strong>
  `departments[].parent`| <strong><span style="color:green">✓</span></strong>
  `departments[].parent.name`| <strong><span style="color:green">✓</span></strong>
  `locations[].line1` | <strong><span style="color:red">x</span></strong>
  `locations[].line2` | <strong><span style="color:red">x</span></strong>
  `locations[].city` | <strong><span style="color:red">x</span></strong>
  `locations[].state` |<strong><span style="color:red">x</span></strong>
  `locations[].postal_code` | <strong><span style="color:red">x</span></strong>
  `locations[].country` | <strong><span style="color:red">x</span></strong>
  `accounts[].routing_number` | <strong><span style="color:red">x</span></strong>
  `accounts[].account_name` | <strong><span style="color:red">x</span></strong>
  `accounts[].institution_name` | <strong><span style="color:red">x</span></strong>
  `accounts[].account_type` | <strong><span style="color:red">x</span></strong>
  `accounts[].account_number` | <strong><span style="color:red">x</span></strong>

</details>

<details>
<summary><strong style="display:inline">Directory</strong></summary>

  Field | Support
  --- | ---
  `id` | <strong><span style="color:green">✓</span></strong>
  `first_name` | <strong><span style="color:green">✓</span></strong>
  `middle_name` | <strong><span style="color:green">✓</span></strong>
  `last_name` | <strong><span style="color:green">✓</span></strong>
  `manager.id` | <strong><span style="color:green">✓</span></strong>
  `department.name` | <strong><span style="color:green">✓</span></strong>
  `is_active` | <strong><span style="color:green">✓</span></strong>

</details>

<details>
<summary><strong style="display:inline">Individual</strong></summary>


  Field | Support
  --- | ---
  `id` | <strong><span style="color:green">✓</span></strong>
  `first_name` | <strong><span style="color:green">✓</span></strong>
  `middle_name` | <strong><span style="color:green">✓</span></strong>
  `last_name` | <strong><span style="color:green">✓</span></strong>
  `manager.id` | <strong><span style="color:green">✓</span></strong>
  `department.name` | <strong><span style="color:green">✓</span></strong>
  `is_active` | <strong><span style="color:green">✓</span></strong>

</details>

<details>
<summary><strong style="display:inline">Employment</strong></summary>


  Field | Support
  --- | ---
  `id` | <strong><span style="color:green">✓</span></strong>
  `first_name` | <strong><span style="color:green">✓</span></strong>
  `middle_name` | <strong><span style="color:green">✓</span></strong>
  `last_name` | <strong><span style="color:green">✓</span></strong>
  `manager.id` | <strong><span style="color:green">✓</span></strong>
  `department.name` | <strong><span style="color:green">✓</span></strong>
  `is_active` | <strong><span style="color:green">✓</span></strong>

</details>

<details>
<summary><strong style="display:inline">Payment</strong></summary>


  Field | Support
  --- | ---
  `id` | <strong><span style="color:green">✓</span></strong>
  `first_name` | <strong><span style="color:green">✓</span></strong>
  `middle_name` | <strong><span style="color:green">✓</span></strong>
  `last_name` | <strong><span style="color:green">✓</span></strong>
  `manager.id` | <strong><span style="color:green">✓</span></strong>
  `department.name` | <strong><span style="color:green">✓</span></strong>
  `is_active` | <strong><span style="color:green">✓</span></strong>

</details>

<details>
<summary><strong style="display:inline">Pay Statement</strong></summary>


  Field | Support
  --- | ---
  `id` | <strong><span style="color:green">✓</span></strong>
  `first_name` | <strong><span style="color:green">✓</span></strong>
  `middle_name` | <strong><span style="color:green">✓</span></strong>
  `last_name` | <strong><span style="color:green">✓</span></strong>
  `manager.id` | <strong><span style="color:green">✓</span></strong>
  `department.name` | <strong><span style="color:green">✓</span></strong>
  `is_active` | <strong><span style="color:green">✓</span></strong>

</details>

<!-- type: tab-end -->

### Paycom
<!--
type: tab
title: Credentials
-->
<details>
<summary><strong style="display:inline">Company</strong></summary>


  Field | Support
  ---- | -----
  `id` | <strong><span style="color:green">✓</span></strong>
  `legal_name` | <strong><span style="color:green">✓</span></strong>
  `entity.type` | <strong><span style="color:green">✓</span></strong>
  `entity.subtype` | <strong><span style="color:green">✓</span></strong>
  `primary_email` | <strong><span style="color:green">✓</span></strong>
  `primary_phone_number` | <strong><span style="color:green">✓</span></strong>
  `ein` | <strong><span style="color:green">✓</span></strong>
  `departments[]` | <strong><span style="color:green">✓</span></strong>
  `departments[].parent`| <strong><span style="color:green">✓</span></strong>
  `departments[].parent.name`| <strong><span style="color:green">✓</span></strong>
  `locations[].line1` | <strong><span style="color:red">x</span></strong>
  `locations[].line2` | <strong><span style="color:red">x</span></strong>
  `locations[].city` | <strong><span style="color:red">x</span></strong>
  `locations[].state` |<strong><span style="color:red">x</span></strong>
  `locations[].postal_code` | <strong><span style="color:red">x</span></strong>
  `locations[].country` | <strong><span style="color:red">x</span></strong>
  `accounts[].routing_number` | <strong><span style="color:red">x</span></strong>
  `accounts[].account_name` | <strong><span style="color:red">x</span></strong>
  `accounts[].institution_name` | <strong><span style="color:red">x</span></strong>
  `accounts[].account_type` | <strong><span style="color:red">x</span></strong>
  `accounts[].account_number` | <strong><span style="color:red">x</span></strong>

</details>

<details>
<summary><strong style="display:inline">Directory</strong></summary>

  Field | Support
  --- | ---
  `id` | <strong><span style="color:green">✓</span></strong>
  `first_name` | <strong><span style="color:green">✓</span></strong>
  `middle_name` | <strong><span style="color:green">✓</span></strong>
  `last_name` | <strong><span style="color:green">✓</span></strong>
  `manager.id` | <strong><span style="color:green">✓</span></strong>
  `department.name` | <strong><span style="color:green">✓</span></strong>
  `is_active` | <strong><span style="color:green">✓</span></strong>

</details>

<details>
<summary><strong style="display:inline">Individual</strong></summary>


  Field | Support
  --- | ---
  `id` | <strong><span style="color:green">✓</span></strong>
  `first_name` | <strong><span style="color:green">✓</span></strong>
  `middle_name` | <strong><span style="color:green">✓</span></strong>
  `last_name` | <strong><span style="color:green">✓</span></strong>
  `manager.id` | <strong><span style="color:green">✓</span></strong>
  `department.name` | <strong><span style="color:green">✓</span></strong>
  `is_active` | <strong><span style="color:green">✓</span></strong>

</details>

<details>
<summary><strong style="display:inline">Employment</strong></summary>


  Field | Support
  --- | ---
  `id` | <strong><span style="color:green">✓</span></strong>
  `first_name` | <strong><span style="color:green">✓</span></strong>
  `middle_name` | <strong><span style="color:green">✓</span></strong>
  `last_name` | <strong><span style="color:green">✓</span></strong>
  `manager.id` | <strong><span style="color:green">✓</span></strong>
  `department.name` | <strong><span style="color:green">✓</span></strong>
  `is_active` | <strong><span style="color:green">✓</span></strong>

</details>

<details>
<summary><strong style="display:inline">Payment</strong></summary>


  Field | Support
  --- | ---
  `id` | <strong><span style="color:green">✓</span></strong>
  `first_name` | <strong><span style="color:green">✓</span></strong>
  `middle_name` | <strong><span style="color:green">✓</span></strong>
  `last_name` | <strong><span style="color:green">✓</span></strong>
  `manager.id` | <strong><span style="color:green">✓</span></strong>
  `department.name` | <strong><span style="color:green">✓</span></strong>
  `is_active` | <strong><span style="color:green">✓</span></strong>

</details>

<details>
<summary><strong style="display:inline">Pay Statement</strong></summary>


  Field | Support
  --- | ---
  `id` | <strong><span style="color:green">✓</span></strong>
  `first_name` | <strong><span style="color:green">✓</span></strong>
  `middle_name` | <strong><span style="color:green">✓</span></strong>
  `last_name` | <strong><span style="color:green">✓</span></strong>
  `manager.id` | <strong><span style="color:green">✓</span></strong>
  `department.name` | <strong><span style="color:green">✓</span></strong>
  `is_active` | <strong><span style="color:green">✓</span></strong>

</details>

<!--
type: tab
title: API
-->
<details>
<summary><strong style="display:inline">Company</strong></summary>


  Field | Support
  ---- | -----
  `id` | <strong><span style="color:green">✓</span></strong>
  `legal_name` | <strong><span style="color:green">✓</span></strong>
  `entity.type` | <strong><span style="color:green">✓</span></strong>
  `entity.subtype` | <strong><span style="color:green">✓</span></strong>
  `primary_email` | <strong><span style="color:green">✓</span></strong>
  `primary_phone_number` | <strong><span style="color:green">✓</span></strong>
  `ein` | <strong><span style="color:green">✓</span></strong>
  `departments[]` | <strong><span style="color:green">✓</span></strong>
  `departments[].parent`| <strong><span style="color:green">✓</span></strong>
  `departments[].parent.name`| <strong><span style="color:green">✓</span></strong>
  `locations[].line1` | <strong><span style="color:red">x</span></strong>
  `locations[].line2` | <strong><span style="color:red">x</span></strong>
  `locations[].city` | <strong><span style="color:red">x</span></strong>
  `locations[].state` |<strong><span style="color:red">x</span></strong>
  `locations[].postal_code` | <strong><span style="color:red">x</span></strong>
  `locations[].country` | <strong><span style="color:red">x</span></strong>
  `accounts[].routing_number` | <strong><span style="color:red">x</span></strong>
  `accounts[].account_name` | <strong><span style="color:red">x</span></strong>
  `accounts[].institution_name` | <strong><span style="color:red">x</span></strong>
  `accounts[].account_type` | <strong><span style="color:red">x</span></strong>
  `accounts[].account_number` | <strong><span style="color:red">x</span></strong>

</details>

<details>
<summary><strong style="display:inline">Directory</strong></summary>

  Field | Support
  --- | ---
  `id` | <strong><span style="color:green">✓</span></strong>
  `first_name` | <strong><span style="color:green">✓</span></strong>
  `middle_name` | <strong><span style="color:green">✓</span></strong>
  `last_name` | <strong><span style="color:green">✓</span></strong>
  `manager.id` | <strong><span style="color:green">✓</span></strong>
  `department.name` | <strong><span style="color:green">✓</span></strong>
  `is_active` | <strong><span style="color:green">✓</span></strong>

</details>

<details>
<summary><strong style="display:inline">Individual</strong></summary>


  Field | Support
  --- | ---
  `id` | <strong><span style="color:green">✓</span></strong>
  `first_name` | <strong><span style="color:green">✓</span></strong>
  `middle_name` | <strong><span style="color:green">✓</span></strong>
  `last_name` | <strong><span style="color:green">✓</span></strong>
  `manager.id` | <strong><span style="color:green">✓</span></strong>
  `department.name` | <strong><span style="color:green">✓</span></strong>
  `is_active` | <strong><span style="color:green">✓</span></strong>

</details>

<details>
<summary><strong style="display:inline">Employment</strong></summary>


  Field | Support
  --- | ---
  `id` | <strong><span style="color:green">✓</span></strong>
  `first_name` | <strong><span style="color:green">✓</span></strong>
  `middle_name` | <strong><span style="color:green">✓</span></strong>
  `last_name` | <strong><span style="color:green">✓</span></strong>
  `manager.id` | <strong><span style="color:green">✓</span></strong>
  `department.name` | <strong><span style="color:green">✓</span></strong>
  `is_active` | <strong><span style="color:green">✓</span></strong>

</details>

<details>
<summary><strong style="display:inline">Payment</strong></summary>


  Field | Support
  --- | ---
  `id` | <strong><span style="color:green">✓</span></strong>
  `first_name` | <strong><span style="color:green">✓</span></strong>
  `middle_name` | <strong><span style="color:green">✓</span></strong>
  `last_name` | <strong><span style="color:green">✓</span></strong>
  `manager.id` | <strong><span style="color:green">✓</span></strong>
  `department.name` | <strong><span style="color:green">✓</span></strong>
  `is_active` | <strong><span style="color:green">✓</span></strong>

</details>

<details>
<summary><strong style="display:inline">Pay Statement</strong></summary>


  Field | Support
  --- | ---
  `id` | <strong><span style="color:green">✓</span></strong>
  `first_name` | <strong><span style="color:green">✓</span></strong>
  `middle_name` | <strong><span style="color:green">✓</span></strong>
  `last_name` | <strong><span style="color:green">✓</span></strong>
  `manager.id` | <strong><span style="color:green">✓</span></strong>
  `department.name` | <strong><span style="color:green">✓</span></strong>
  `is_active` | <strong><span style="color:green">✓</span></strong>

</details>

<!-- type: tab-end -->

### Paychex Flex
<!--
type: tab
title: Credentials
-->
<details>
<summary><strong style="display:inline">Company</strong></summary>


  Field | Support
  ---- | -----
  `id` | <strong><span style="color:green">✓</span></strong>
  `legal_name` | <strong><span style="color:green">✓</span></strong>
  `entity.type` | <strong><span style="color:green">✓</span></strong>
  `entity.subtype` | <strong><span style="color:green">✓</span></strong>
  `primary_email` | <strong><span style="color:green">✓</span></strong>
  `primary_phone_number` | <strong><span style="color:green">✓</span></strong>
  `ein` | <strong><span style="color:green">✓</span></strong>
  `departments[]` | <strong><span style="color:green">✓</span></strong>
  `departments[].parent`| <strong><span style="color:green">✓</span></strong>
  `departments[].parent.name`| <strong><span style="color:green">✓</span></strong>
  `locations[].line1` | <strong><span style="color:red">x</span></strong>
  `locations[].line2` | <strong><span style="color:red">x</span></strong>
  `locations[].city` | <strong><span style="color:red">x</span></strong>
  `locations[].state` |<strong><span style="color:red">x</span></strong>
  `locations[].postal_code` | <strong><span style="color:red">x</span></strong>
  `locations[].country` | <strong><span style="color:red">x</span></strong>
  `accounts[].routing_number` | <strong><span style="color:red">x</span></strong>
  `accounts[].account_name` | <strong><span style="color:red">x</span></strong>
  `accounts[].institution_name` | <strong><span style="color:red">x</span></strong>
  `accounts[].account_type` | <strong><span style="color:red">x</span></strong>
  `accounts[].account_number` | <strong><span style="color:red">x</span></strong>

</details>

<details>
<summary><strong style="display:inline">Directory</strong></summary>

  Field | Support
  --- | ---
  `id` | <strong><span style="color:green">✓</span></strong>
  `first_name` | <strong><span style="color:green">✓</span></strong>
  `middle_name` | <strong><span style="color:green">✓</span></strong>
  `last_name` | <strong><span style="color:green">✓</span></strong>
  `manager.id` | <strong><span style="color:green">✓</span></strong>
  `department.name` | <strong><span style="color:green">✓</span></strong>
  `is_active` | <strong><span style="color:green">✓</span></strong>

</details>

<details>
<summary><strong style="display:inline">Individual</strong></summary>


  Field | Support
  --- | ---
  `id` | <strong><span style="color:green">✓</span></strong>
  `first_name` | <strong><span style="color:green">✓</span></strong>
  `middle_name` | <strong><span style="color:green">✓</span></strong>
  `last_name` | <strong><span style="color:green">✓</span></strong>
  `manager.id` | <strong><span style="color:green">✓</span></strong>
  `department.name` | <strong><span style="color:green">✓</span></strong>
  `is_active` | <strong><span style="color:green">✓</span></strong>

</details>

<details>
<summary><strong style="display:inline">Employment</strong></summary>


  Field | Support
  --- | ---
  `id` | <strong><span style="color:green">✓</span></strong>
  `first_name` | <strong><span style="color:green">✓</span></strong>
  `middle_name` | <strong><span style="color:green">✓</span></strong>
  `last_name` | <strong><span style="color:green">✓</span></strong>
  `manager.id` | <strong><span style="color:green">✓</span></strong>
  `department.name` | <strong><span style="color:green">✓</span></strong>
  `is_active` | <strong><span style="color:green">✓</span></strong>

</details>

<details>
<summary><strong style="display:inline">Payment</strong></summary>


  Field | Support
  --- | ---
  `id` | <strong><span style="color:green">✓</span></strong>
  `first_name` | <strong><span style="color:green">✓</span></strong>
  `middle_name` | <strong><span style="color:green">✓</span></strong>
  `last_name` | <strong><span style="color:green">✓</span></strong>
  `manager.id` | <strong><span style="color:green">✓</span></strong>
  `department.name` | <strong><span style="color:green">✓</span></strong>
  `is_active` | <strong><span style="color:green">✓</span></strong>

</details>

<details>
<summary><strong style="display:inline">Pay Statement</strong></summary>


  Field | Support
  --- | ---
  `id` | <strong><span style="color:green">✓</span></strong>
  `first_name` | <strong><span style="color:green">✓</span></strong>
  `middle_name` | <strong><span style="color:green">✓</span></strong>
  `last_name` | <strong><span style="color:green">✓</span></strong>
  `manager.id` | <strong><span style="color:green">✓</span></strong>
  `department.name` | <strong><span style="color:green">✓</span></strong>
  `is_active` | <strong><span style="color:green">✓</span></strong>

</details>

<!--
type: tab
title: API
-->
<details>
<summary><strong style="display:inline">Company</strong></summary>


  Field | Support
  ---- | -----
  `id` | <strong><span style="color:green">✓</span></strong>
  `legal_name` | <strong><span style="color:green">✓</span></strong>
  `entity.type` | <strong><span style="color:green">✓</span></strong>
  `entity.subtype` | <strong><span style="color:green">✓</span></strong>
  `primary_email` | <strong><span style="color:green">✓</span></strong>
  `primary_phone_number` | <strong><span style="color:green">✓</span></strong>
  `ein` | <strong><span style="color:green">✓</span></strong>
  `departments[]` | <strong><span style="color:green">✓</span></strong>
  `departments[].parent`| <strong><span style="color:green">✓</span></strong>
  `departments[].parent.name`| <strong><span style="color:green">✓</span></strong>
  `locations[].line1` | <strong><span style="color:red">x</span></strong>
  `locations[].line2` | <strong><span style="color:red">x</span></strong>
  `locations[].city` | <strong><span style="color:red">x</span></strong>
  `locations[].state` |<strong><span style="color:red">x</span></strong>
  `locations[].postal_code` | <strong><span style="color:red">x</span></strong>
  `locations[].country` | <strong><span style="color:red">x</span></strong>
  `accounts[].routing_number` | <strong><span style="color:red">x</span></strong>
  `accounts[].account_name` | <strong><span style="color:red">x</span></strong>
  `accounts[].institution_name` | <strong><span style="color:red">x</span></strong>
  `accounts[].account_type` | <strong><span style="color:red">x</span></strong>
  `accounts[].account_number` | <strong><span style="color:red">x</span></strong>

</details>

<details>
<summary><strong style="display:inline">Directory</strong></summary>

  Field | Support
  --- | ---
  `id` | <strong><span style="color:green">✓</span></strong>
  `first_name` | <strong><span style="color:green">✓</span></strong>
  `middle_name` | <strong><span style="color:green">✓</span></strong>
  `last_name` | <strong><span style="color:green">✓</span></strong>
  `manager.id` | <strong><span style="color:green">✓</span></strong>
  `department.name` | <strong><span style="color:green">✓</span></strong>
  `is_active` | <strong><span style="color:green">✓</span></strong>

</details>

<details>
<summary><strong style="display:inline">Individual</strong></summary>


  Field | Support
  --- | ---
  `id` | <strong><span style="color:green">✓</span></strong>
  `first_name` | <strong><span style="color:green">✓</span></strong>
  `middle_name` | <strong><span style="color:green">✓</span></strong>
  `last_name` | <strong><span style="color:green">✓</span></strong>
  `manager.id` | <strong><span style="color:green">✓</span></strong>
  `department.name` | <strong><span style="color:green">✓</span></strong>
  `is_active` | <strong><span style="color:green">✓</span></strong>

</details>

<details>
<summary><strong style="display:inline">Employment</strong></summary>


  Field | Support
  --- | ---
  `id` | <strong><span style="color:green">✓</span></strong>
  `first_name` | <strong><span style="color:green">✓</span></strong>
  `middle_name` | <strong><span style="color:green">✓</span></strong>
  `last_name` | <strong><span style="color:green">✓</span></strong>
  `manager.id` | <strong><span style="color:green">✓</span></strong>
  `department.name` | <strong><span style="color:green">✓</span></strong>
  `is_active` | <strong><span style="color:green">✓</span></strong>

</details>

<details>
<summary><strong style="display:inline">Payment</strong></summary>


  Field | Support
  --- | ---
  `id` | <strong><span style="color:green">✓</span></strong>
  `first_name` | <strong><span style="color:green">✓</span></strong>
  `middle_name` | <strong><span style="color:green">✓</span></strong>
  `last_name` | <strong><span style="color:green">✓</span></strong>
  `manager.id` | <strong><span style="color:green">✓</span></strong>
  `department.name` | <strong><span style="color:green">✓</span></strong>
  `is_active` | <strong><span style="color:green">✓</span></strong>

</details>

<details>
<summary><strong style="display:inline">Pay Statement</strong></summary>


  Field | Support
  --- | ---
  `id` | <strong><span style="color:green">✓</span></strong>
  `first_name` | <strong><span style="color:green">✓</span></strong>
  `middle_name` | <strong><span style="color:green">✓</span></strong>
  `last_name` | <strong><span style="color:green">✓</span></strong>
  `manager.id` | <strong><span style="color:green">✓</span></strong>
  `department.name` | <strong><span style="color:green">✓</span></strong>
  `is_active` | <strong><span style="color:green">✓</span></strong>

</details>

<!-- type: tab-end -->

### Paycor
<!--
type: tab
title: Credentials
-->
<details>
<summary><strong style="display:inline">Company</strong></summary>


  Field | Support
  ---- | -----
  `id` | <strong><span style="color:green">✓</span></strong>
  `legal_name` | <strong><span style="color:green">✓</span></strong>
  `entity.type` | <strong><span style="color:green">✓</span></strong>
  `entity.subtype` | <strong><span style="color:green">✓</span></strong>
  `primary_email` | <strong><span style="color:green">✓</span></strong>
  `primary_phone_number` | <strong><span style="color:green">✓</span></strong>
  `ein` | <strong><span style="color:green">✓</span></strong>
  `departments[]` | <strong><span style="color:green">✓</span></strong>
  `departments[].parent`| <strong><span style="color:green">✓</span></strong>
  `departments[].parent.name`| <strong><span style="color:green">✓</span></strong>
  `locations[].line1` | <strong><span style="color:red">x</span></strong>
  `locations[].line2` | <strong><span style="color:red">x</span></strong>
  `locations[].city` | <strong><span style="color:red">x</span></strong>
  `locations[].state` |<strong><span style="color:red">x</span></strong>
  `locations[].postal_code` | <strong><span style="color:red">x</span></strong>
  `locations[].country` | <strong><span style="color:red">x</span></strong>
  `accounts[].routing_number` | <strong><span style="color:red">x</span></strong>
  `accounts[].account_name` | <strong><span style="color:red">x</span></strong>
  `accounts[].institution_name` | <strong><span style="color:red">x</span></strong>
  `accounts[].account_type` | <strong><span style="color:red">x</span></strong>
  `accounts[].account_number` | <strong><span style="color:red">x</span></strong>

</details>

<details>
<summary><strong style="display:inline">Directory</strong></summary>

  Field | Support
  --- | ---
  `id` | <strong><span style="color:green">✓</span></strong>
  `first_name` | <strong><span style="color:green">✓</span></strong>
  `middle_name` | <strong><span style="color:green">✓</span></strong>
  `last_name` | <strong><span style="color:green">✓</span></strong>
  `manager.id` | <strong><span style="color:green">✓</span></strong>
  `department.name` | <strong><span style="color:green">✓</span></strong>
  `is_active` | <strong><span style="color:green">✓</span></strong>

</details>

<details>
<summary><strong style="display:inline">Individual</strong></summary>


  Field | Support
  --- | ---
  `id` | <strong><span style="color:green">✓</span></strong>
  `first_name` | <strong><span style="color:green">✓</span></strong>
  `middle_name` | <strong><span style="color:green">✓</span></strong>
  `last_name` | <strong><span style="color:green">✓</span></strong>
  `manager.id` | <strong><span style="color:green">✓</span></strong>
  `department.name` | <strong><span style="color:green">✓</span></strong>
  `is_active` | <strong><span style="color:green">✓</span></strong>

</details>

<details>
<summary><strong style="display:inline">Employment</strong></summary>


  Field | Support
  --- | ---
  `id` | <strong><span style="color:green">✓</span></strong>
  `first_name` | <strong><span style="color:green">✓</span></strong>
  `middle_name` | <strong><span style="color:green">✓</span></strong>
  `last_name` | <strong><span style="color:green">✓</span></strong>
  `manager.id` | <strong><span style="color:green">✓</span></strong>
  `department.name` | <strong><span style="color:green">✓</span></strong>
  `is_active` | <strong><span style="color:green">✓</span></strong>

</details>

<details>
<summary><strong style="display:inline">Payment</strong></summary>


  Field | Support
  --- | ---
  `id` | <strong><span style="color:green">✓</span></strong>
  `first_name` | <strong><span style="color:green">✓</span></strong>
  `middle_name` | <strong><span style="color:green">✓</span></strong>
  `last_name` | <strong><span style="color:green">✓</span></strong>
  `manager.id` | <strong><span style="color:green">✓</span></strong>
  `department.name` | <strong><span style="color:green">✓</span></strong>
  `is_active` | <strong><span style="color:green">✓</span></strong>

</details>

<details>
<summary><strong style="display:inline">Pay Statement</strong></summary>


  Field | Support
  --- | ---
  `id` | <strong><span style="color:green">✓</span></strong>
  `first_name` | <strong><span style="color:green">✓</span></strong>
  `middle_name` | <strong><span style="color:green">✓</span></strong>
  `last_name` | <strong><span style="color:green">✓</span></strong>
  `manager.id` | <strong><span style="color:green">✓</span></strong>
  `department.name` | <strong><span style="color:green">✓</span></strong>
  `is_active` | <strong><span style="color:green">✓</span></strong>

</details>

<!-- type: tab-end -->

### Paylocity

<!--
type: tab
title: Credentials
-->

<details>
<summary><strong style="display:inline">Company</strong></summary>


  Field | Support
  ---- | -----
  `id` | <strong><span style="color:green">✓</span></strong>
  `legal_name` | <strong><span style="color:green">✓</span></strong>
  `entity.type` | <strong><span style="color:green">✓</span></strong>
  `entity.subtype` | <strong><span style="color:green">✓</span></strong>
  `primary_email` | <strong><span style="color:green">✓</span></strong>
  `primary_phone_number` | <strong><span style="color:green">✓</span></strong>
  `ein` | <strong><span style="color:green">✓</span></strong>
  `departments[]` | <strong><span style="color:green">✓</span></strong>
  `departments[].parent`| <strong><span style="color:green">✓</span></strong>
  `departments[].parent.name`| <strong><span style="color:green">✓</span></strong>
  `locations[].line1` | <strong><span style="color:red">x</span></strong>
  `locations[].line2` | <strong><span style="color:red">x</span></strong>
  `locations[].city` | <strong><span style="color:red">x</span></strong>
  `locations[].state` |<strong><span style="color:red">x</span></strong>
  `locations[].postal_code` | <strong><span style="color:red">x</span></strong>
  `locations[].country` | <strong><span style="color:red">x</span></strong>
  `accounts[].routing_number` | <strong><span style="color:red">x</span></strong>
  `accounts[].account_name` | <strong><span style="color:red">x</span></strong>
  `accounts[].institution_name` | <strong><span style="color:red">x</span></strong>
  `accounts[].account_type` | <strong><span style="color:red">x</span></strong>
  `accounts[].account_number` | <strong><span style="color:red">x</span></strong>

</details>

<details>
<summary><strong style="display:inline">Directory</strong></summary>

  Field | Support
  --- | ---
  `id` | <strong><span style="color:green">✓</span></strong>
  `first_name` | <strong><span style="color:green">✓</span></strong>
  `middle_name` | <strong><span style="color:green">✓</span></strong>
  `last_name` | <strong><span style="color:green">✓</span></strong>
  `manager.id` | <strong><span style="color:green">✓</span></strong>
  `department.name` | <strong><span style="color:green">✓</span></strong>
  `is_active` | <strong><span style="color:green">✓</span></strong>

</details>

<details>
<summary><strong style="display:inline">Individual</strong></summary>


  Field | Support
  --- | ---
  `id` | <strong><span style="color:green">✓</span></strong>
  `first_name` | <strong><span style="color:green">✓</span></strong>
  `middle_name` | <strong><span style="color:green">✓</span></strong>
  `last_name` | <strong><span style="color:green">✓</span></strong>
  `manager.id` | <strong><span style="color:green">✓</span></strong>
  `department.name` | <strong><span style="color:green">✓</span></strong>
  `is_active` | <strong><span style="color:green">✓</span></strong>

</details>

<details>
<summary><strong style="display:inline">Employment</strong></summary>


  Field | Support
  --- | ---
  `id` | <strong><span style="color:green">✓</span></strong>
  `first_name` | <strong><span style="color:green">✓</span></strong>
  `middle_name` | <strong><span style="color:green">✓</span></strong>
  `last_name` | <strong><span style="color:green">✓</span></strong>
  `manager.id` | <strong><span style="color:green">✓</span></strong>
  `department.name` | <strong><span style="color:green">✓</span></strong>
  `is_active` | <strong><span style="color:green">✓</span></strong>

</details>

<details>
<summary><strong style="display:inline">Payment</strong></summary>


  Field | Support
  --- | ---
  `id` | <strong><span style="color:green">✓</span></strong>
  `first_name` | <strong><span style="color:green">✓</span></strong>
  `middle_name` | <strong><span style="color:green">✓</span></strong>
  `last_name` | <strong><span style="color:green">✓</span></strong>
  `manager.id` | <strong><span style="color:green">✓</span></strong>
  `department.name` | <strong><span style="color:green">✓</span></strong>
  `is_active` | <strong><span style="color:green">✓</span></strong>

</details>

<details>
<summary><strong style="display:inline">Pay Statement</strong></summary>


  Field | Support
  --- | ---
  `id` | <strong><span style="color:green">✓</span></strong>
  `first_name` | <strong><span style="color:green">✓</span></strong>
  `middle_name` | <strong><span style="color:green">✓</span></strong>
  `last_name` | <strong><span style="color:green">✓</span></strong>
  `manager.id` | <strong><span style="color:green">✓</span></strong>
  `department.name` | <strong><span style="color:green">✓</span></strong>
  `is_active` | <strong><span style="color:green">✓</span></strong>

</details>

<!--
type: tab
title: API
-->
<details>
<summary><strong style="display:inline">Company</strong></summary>


  Field | Support
  ---- | -----
  `id` | <strong><span style="color:green">✓</span></strong>
  `legal_name` | <strong><span style="color:green">✓</span></strong>
  `entity.type` | <strong><span style="color:green">✓</span></strong>
  `entity.subtype` | <strong><span style="color:green">✓</span></strong>
  `primary_email` | <strong><span style="color:green">✓</span></strong>
  `primary_phone_number` | <strong><span style="color:green">✓</span></strong>
  `ein` | <strong><span style="color:green">✓</span></strong>
  `departments[]` | <strong><span style="color:green">✓</span></strong>
  `departments[].parent`| <strong><span style="color:green">✓</span></strong>
  `departments[].parent.name`| <strong><span style="color:green">✓</span></strong>
  `locations[].line1` | <strong><span style="color:red">x</span></strong>
  `locations[].line2` | <strong><span style="color:red">x</span></strong>
  `locations[].city` | <strong><span style="color:red">x</span></strong>
  `locations[].state` |<strong><span style="color:red">x</span></strong>
  `locations[].postal_code` | <strong><span style="color:red">x</span></strong>
  `locations[].country` | <strong><span style="color:red">x</span></strong>
  `accounts[].routing_number` | <strong><span style="color:red">x</span></strong>
  `accounts[].account_name` | <strong><span style="color:red">x</span></strong>
  `accounts[].institution_name` | <strong><span style="color:red">x</span></strong>
  `accounts[].account_type` | <strong><span style="color:red">x</span></strong>
  `accounts[].account_number` | <strong><span style="color:red">x</span></strong>

</details>

<details>
<summary><strong style="display:inline">Directory</strong></summary>

  Field | Support
  --- | ---
  `id` | <strong><span style="color:green">✓</span></strong>
  `first_name` | <strong><span style="color:green">✓</span></strong>
  `middle_name` | <strong><span style="color:green">✓</span></strong>
  `last_name` | <strong><span style="color:green">✓</span></strong>
  `manager.id` | <strong><span style="color:green">✓</span></strong>
  `department.name` | <strong><span style="color:green">✓</span></strong>
  `is_active` | <strong><span style="color:green">✓</span></strong>

</details>

<details>
<summary><strong style="display:inline">Individual</strong></summary>


  Field | Support
  --- | ---
  `id` | <strong><span style="color:green">✓</span></strong>
  `first_name` | <strong><span style="color:green">✓</span></strong>
  `middle_name` | <strong><span style="color:green">✓</span></strong>
  `last_name` | <strong><span style="color:green">✓</span></strong>
  `manager.id` | <strong><span style="color:green">✓</span></strong>
  `department.name` | <strong><span style="color:green">✓</span></strong>
  `is_active` | <strong><span style="color:green">✓</span></strong>

</details>

<details>
<summary><strong style="display:inline">Employment</strong></summary>


  Field | Support
  --- | ---
  `id` | <strong><span style="color:green">✓</span></strong>
  `first_name` | <strong><span style="color:green">✓</span></strong>
  `middle_name` | <strong><span style="color:green">✓</span></strong>
  `last_name` | <strong><span style="color:green">✓</span></strong>
  `manager.id` | <strong><span style="color:green">✓</span></strong>
  `department.name` | <strong><span style="color:green">✓</span></strong>
  `is_active` | <strong><span style="color:green">✓</span></strong>

</details>

<details>
<summary><strong style="display:inline">Payment</strong></summary>


  Field | Support
  --- | ---
  `id` | <strong><span style="color:green">✓</span></strong>
  `first_name` | <strong><span style="color:green">✓</span></strong>
  `middle_name` | <strong><span style="color:green">✓</span></strong>
  `last_name` | <strong><span style="color:green">✓</span></strong>
  `manager.id` | <strong><span style="color:green">✓</span></strong>
  `department.name` | <strong><span style="color:green">✓</span></strong>
  `is_active` | <strong><span style="color:green">✓</span></strong>

</details>

<details>
<summary><strong style="display:inline">Pay Statement</strong></summary>


  Field | Support
  --- | ---
  `id` | <strong><span style="color:green">✓</span></strong>
  `first_name` | <strong><span style="color:green">✓</span></strong>
  `middle_name` | <strong><span style="color:green">✓</span></strong>
  `last_name` | <strong><span style="color:green">✓</span></strong>
  `manager.id` | <strong><span style="color:green">✓</span></strong>
  `department.name` | <strong><span style="color:green">✓</span></strong>
  `is_active` | <strong><span style="color:green">✓</span></strong>

</details>

<!-- type: tab-end -->

### Personio
<!--
type: tab
title: API
-->
<details>
<summary><strong style="display:inline">Company</strong></summary>


  Field | Support
  ---- | -----
  `id` | <strong><span style="color:green">✓</span></strong>
  `legal_name` | <strong><span style="color:green">✓</span></strong>
  `entity.type` | <strong><span style="color:green">✓</span></strong>
  `entity.subtype` | <strong><span style="color:green">✓</span></strong>
  `primary_email` | <strong><span style="color:green">✓</span></strong>
  `primary_phone_number` | <strong><span style="color:green">✓</span></strong>
  `ein` | <strong><span style="color:green">✓</span></strong>
  `departments[]` | <strong><span style="color:green">✓</span></strong>
  `departments[].parent`| <strong><span style="color:green">✓</span></strong>
  `departments[].parent.name`| <strong><span style="color:green">✓</span></strong>
  `locations[].line1` | <strong><span style="color:red">x</span></strong>
  `locations[].line2` | <strong><span style="color:red">x</span></strong>
  `locations[].city` | <strong><span style="color:red">x</span></strong>
  `locations[].state` |<strong><span style="color:red">x</span></strong>
  `locations[].postal_code` | <strong><span style="color:red">x</span></strong>
  `locations[].country` | <strong><span style="color:red">x</span></strong>
  `accounts[].routing_number` | <strong><span style="color:red">x</span></strong>
  `accounts[].account_name` | <strong><span style="color:red">x</span></strong>
  `accounts[].institution_name` | <strong><span style="color:red">x</span></strong>
  `accounts[].account_type` | <strong><span style="color:red">x</span></strong>
  `accounts[].account_number` | <strong><span style="color:red">x</span></strong>

</details>

<details>
<summary><strong style="display:inline">Directory</strong></summary>

  Field | Support
  --- | ---
  `id` | <strong><span style="color:green">✓</span></strong>
  `first_name` | <strong><span style="color:green">✓</span></strong>
  `middle_name` | <strong><span style="color:green">✓</span></strong>
  `last_name` | <strong><span style="color:green">✓</span></strong>
  `manager.id` | <strong><span style="color:green">✓</span></strong>
  `department.name` | <strong><span style="color:green">✓</span></strong>
  `is_active` | <strong><span style="color:green">✓</span></strong>

</details>

<details>
<summary><strong style="display:inline">Individual</strong></summary>


  Field | Support
  --- | ---
  `id` | <strong><span style="color:green">✓</span></strong>
  `first_name` | <strong><span style="color:green">✓</span></strong>
  `middle_name` | <strong><span style="color:green">✓</span></strong>
  `last_name` | <strong><span style="color:green">✓</span></strong>
  `manager.id` | <strong><span style="color:green">✓</span></strong>
  `department.name` | <strong><span style="color:green">✓</span></strong>
  `is_active` | <strong><span style="color:green">✓</span></strong>

</details>

<details>
<summary><strong style="display:inline">Employment</strong></summary>


  Field | Support
  --- | ---
  `id` | <strong><span style="color:green">✓</span></strong>
  `first_name` | <strong><span style="color:green">✓</span></strong>
  `middle_name` | <strong><span style="color:green">✓</span></strong>
  `last_name` | <strong><span style="color:green">✓</span></strong>
  `manager.id` | <strong><span style="color:green">✓</span></strong>
  `department.name` | <strong><span style="color:green">✓</span></strong>
  `is_active` | <strong><span style="color:green">✓</span></strong>

</details>

<details>
<summary><strong style="display:inline">Payment</strong></summary>


  Field | Support
  --- | ---
  `id` | <strong><span style="color:green">✓</span></strong>
  `first_name` | <strong><span style="color:green">✓</span></strong>
  `middle_name` | <strong><span style="color:green">✓</span></strong>
  `last_name` | <strong><span style="color:green">✓</span></strong>
  `manager.id` | <strong><span style="color:green">✓</span></strong>
  `department.name` | <strong><span style="color:green">✓</span></strong>
  `is_active` | <strong><span style="color:green">✓</span></strong>

</details>

<details>
<summary><strong style="display:inline">Pay Statement</strong></summary>


  Field | Support
  --- | ---
  `id` | <strong><span style="color:green">✓</span></strong>
  `first_name` | <strong><span style="color:green">✓</span></strong>
  `middle_name` | <strong><span style="color:green">✓</span></strong>
  `last_name` | <strong><span style="color:green">✓</span></strong>
  `manager.id` | <strong><span style="color:green">✓</span></strong>
  `department.name` | <strong><span style="color:green">✓</span></strong>
  `is_active` | <strong><span style="color:green">✓</span></strong>

</details>

<!-- type: tab-end -->

### Quickbooks
<!--
type: tab
title: Credentials
-->
<details>
<summary><strong style="display:inline">Company</strong></summary>


  Field | Support
  ---- | -----
  `id` | <strong><span style="color:green">✓</span></strong>
  `legal_name` | <strong><span style="color:green">✓</span></strong>
  `entity.type` | <strong><span style="color:green">✓</span></strong>
  `entity.subtype` | <strong><span style="color:green">✓</span></strong>
  `primary_email` | <strong><span style="color:green">✓</span></strong>
  `primary_phone_number` | <strong><span style="color:green">✓</span></strong>
  `ein` | <strong><span style="color:green">✓</span></strong>
  `departments[]` | <strong><span style="color:green">✓</span></strong>
  `departments[].parent`| <strong><span style="color:green">✓</span></strong>
  `departments[].parent.name`| <strong><span style="color:green">✓</span></strong>
  `locations[].line1` | <strong><span style="color:red">x</span></strong>
  `locations[].line2` | <strong><span style="color:red">x</span></strong>
  `locations[].city` | <strong><span style="color:red">x</span></strong>
  `locations[].state` |<strong><span style="color:red">x</span></strong>
  `locations[].postal_code` | <strong><span style="color:red">x</span></strong>
  `locations[].country` | <strong><span style="color:red">x</span></strong>
  `accounts[].routing_number` | <strong><span style="color:red">x</span></strong>
  `accounts[].account_name` | <strong><span style="color:red">x</span></strong>
  `accounts[].institution_name` | <strong><span style="color:red">x</span></strong>
  `accounts[].account_type` | <strong><span style="color:red">x</span></strong>
  `accounts[].account_number` | <strong><span style="color:red">x</span></strong>

</details>

<details>
<summary><strong style="display:inline">Directory</strong></summary>

  Field | Support
  --- | ---
  `id` | <strong><span style="color:green">✓</span></strong>
  `first_name` | <strong><span style="color:green">✓</span></strong>
  `middle_name` | <strong><span style="color:green">✓</span></strong>
  `last_name` | <strong><span style="color:green">✓</span></strong>
  `manager.id` | <strong><span style="color:green">✓</span></strong>
  `department.name` | <strong><span style="color:green">✓</span></strong>
  `is_active` | <strong><span style="color:green">✓</span></strong>

</details>

<details>
<summary><strong style="display:inline">Individual</strong></summary>


  Field | Support
  --- | ---
  `id` | <strong><span style="color:green">✓</span></strong>
  `first_name` | <strong><span style="color:green">✓</span></strong>
  `middle_name` | <strong><span style="color:green">✓</span></strong>
  `last_name` | <strong><span style="color:green">✓</span></strong>
  `manager.id` | <strong><span style="color:green">✓</span></strong>
  `department.name` | <strong><span style="color:green">✓</span></strong>
  `is_active` | <strong><span style="color:green">✓</span></strong>

</details>

<details>
<summary><strong style="display:inline">Employment</strong></summary>


  Field | Support
  --- | ---
  `id` | <strong><span style="color:green">✓</span></strong>
  `first_name` | <strong><span style="color:green">✓</span></strong>
  `middle_name` | <strong><span style="color:green">✓</span></strong>
  `last_name` | <strong><span style="color:green">✓</span></strong>
  `manager.id` | <strong><span style="color:green">✓</span></strong>
  `department.name` | <strong><span style="color:green">✓</span></strong>
  `is_active` | <strong><span style="color:green">✓</span></strong>

</details>

<details>
<summary><strong style="display:inline">Payment</strong></summary>


  Field | Support
  --- | ---
  `id` | <strong><span style="color:green">✓</span></strong>
  `first_name` | <strong><span style="color:green">✓</span></strong>
  `middle_name` | <strong><span style="color:green">✓</span></strong>
  `last_name` | <strong><span style="color:green">✓</span></strong>
  `manager.id` | <strong><span style="color:green">✓</span></strong>
  `department.name` | <strong><span style="color:green">✓</span></strong>
  `is_active` | <strong><span style="color:green">✓</span></strong>

</details>

<details>
<summary><strong style="display:inline">Pay Statement</strong></summary>


  Field | Support
  --- | ---
  `id` | <strong><span style="color:green">✓</span></strong>
  `first_name` | <strong><span style="color:green">✓</span></strong>
  `middle_name` | <strong><span style="color:green">✓</span></strong>
  `last_name` | <strong><span style="color:green">✓</span></strong>
  `manager.id` | <strong><span style="color:green">✓</span></strong>
  `department.name` | <strong><span style="color:green">✓</span></strong>
  `is_active` | <strong><span style="color:green">✓</span></strong>

</details>

<!-- type: tab-end -->


### Rippling
<!--
type: tab
title: API
-->
<details>
<summary><strong style="display:inline">Company</strong></summary>


  Field | Support
  ---- | -----
  `id` | <strong><span style="color:green">✓</span></strong>
  `legal_name` | <strong><span style="color:green">✓</span></strong>
  `entity.type` | <strong><span style="color:green">✓</span></strong>
  `entity.subtype` | <strong><span style="color:green">✓</span></strong>
  `primary_email` | <strong><span style="color:green">✓</span></strong>
  `primary_phone_number` | <strong><span style="color:green">✓</span></strong>
  `ein` | <strong><span style="color:green">✓</span></strong>
  `departments[]` | <strong><span style="color:green">✓</span></strong>
  `departments[].parent`| <strong><span style="color:green">✓</span></strong>
  `departments[].parent.name`| <strong><span style="color:green">✓</span></strong>
  `locations[].line1` | <strong><span style="color:red">x</span></strong>
  `locations[].line2` | <strong><span style="color:red">x</span></strong>
  `locations[].city` | <strong><span style="color:red">x</span></strong>
  `locations[].state` |<strong><span style="color:red">x</span></strong>
  `locations[].postal_code` | <strong><span style="color:red">x</span></strong>
  `locations[].country` | <strong><span style="color:red">x</span></strong>
  `accounts[].routing_number` | <strong><span style="color:red">x</span></strong>
  `accounts[].account_name` | <strong><span style="color:red">x</span></strong>
  `accounts[].institution_name` | <strong><span style="color:red">x</span></strong>
  `accounts[].account_type` | <strong><span style="color:red">x</span></strong>
  `accounts[].account_number` | <strong><span style="color:red">x</span></strong>

</details>

<details>
<summary><strong style="display:inline">Directory</strong></summary>

  Field | Support
  --- | ---
  `id` | <strong><span style="color:green">✓</span></strong>
  `first_name` | <strong><span style="color:green">✓</span></strong>
  `middle_name` | <strong><span style="color:green">✓</span></strong>
  `last_name` | <strong><span style="color:green">✓</span></strong>
  `manager.id` | <strong><span style="color:green">✓</span></strong>
  `department.name` | <strong><span style="color:green">✓</span></strong>
  `is_active` | <strong><span style="color:green">✓</span></strong>

</details>

<details>
<summary><strong style="display:inline">Individual</strong></summary>


  Field | Support
  --- | ---
  `id` | <strong><span style="color:green">✓</span></strong>
  `first_name` | <strong><span style="color:green">✓</span></strong>
  `middle_name` | <strong><span style="color:green">✓</span></strong>
  `last_name` | <strong><span style="color:green">✓</span></strong>
  `manager.id` | <strong><span style="color:green">✓</span></strong>
  `department.name` | <strong><span style="color:green">✓</span></strong>
  `is_active` | <strong><span style="color:green">✓</span></strong>

</details>

<details>
<summary><strong style="display:inline">Employment</strong></summary>


  Field | Support
  --- | ---
  `id` | <strong><span style="color:green">✓</span></strong>
  `first_name` | <strong><span style="color:green">✓</span></strong>
  `middle_name` | <strong><span style="color:green">✓</span></strong>
  `last_name` | <strong><span style="color:green">✓</span></strong>
  `manager.id` | <strong><span style="color:green">✓</span></strong>
  `department.name` | <strong><span style="color:green">✓</span></strong>
  `is_active` | <strong><span style="color:green">✓</span></strong>

</details>

<details>
<summary><strong style="display:inline">Payment</strong></summary>


  Field | Support
  --- | ---
  `id` | <strong><span style="color:green">✓</span></strong>
  `first_name` | <strong><span style="color:green">✓</span></strong>
  `middle_name` | <strong><span style="color:green">✓</span></strong>
  `last_name` | <strong><span style="color:green">✓</span></strong>
  `manager.id` | <strong><span style="color:green">✓</span></strong>
  `department.name` | <strong><span style="color:green">✓</span></strong>
  `is_active` | <strong><span style="color:green">✓</span></strong>

</details>

<details>
<summary><strong style="display:inline">Pay Statement</strong></summary>


  Field | Support
  --- | ---
  `id` | <strong><span style="color:green">✓</span></strong>
  `first_name` | <strong><span style="color:green">✓</span></strong>
  `middle_name` | <strong><span style="color:green">✓</span></strong>
  `last_name` | <strong><span style="color:green">✓</span></strong>
  `manager.id` | <strong><span style="color:green">✓</span></strong>
  `department.name` | <strong><span style="color:green">✓</span></strong>
  `is_active` | <strong><span style="color:green">✓</span></strong>

</details>

<!-- type: tab-end -->

### Run Powered by ADP
<!--
type: tab
title: Credentials
-->
<details>
<summary><strong style="display:inline">Company</strong></summary>


  Field | Support
  ---- | -----
  `id` | <strong><span style="color:green">✓</span></strong>
  `legal_name` | <strong><span style="color:green">✓</span></strong>
  `entity.type` | <strong><span style="color:green">✓</span></strong>
  `entity.subtype` | <strong><span style="color:green">✓</span></strong>
  `primary_email` | <strong><span style="color:green">✓</span></strong>
  `primary_phone_number` | <strong><span style="color:green">✓</span></strong>
  `ein` | <strong><span style="color:green">✓</span></strong>
  `departments[]` | <strong><span style="color:green">✓</span></strong>
  `departments[].parent`| <strong><span style="color:green">✓</span></strong>
  `departments[].parent.name`| <strong><span style="color:green">✓</span></strong>
  `locations[].line1` | <strong><span style="color:red">x</span></strong>
  `locations[].line2` | <strong><span style="color:red">x</span></strong>
  `locations[].city` | <strong><span style="color:red">x</span></strong>
  `locations[].state` |<strong><span style="color:red">x</span></strong>
  `locations[].postal_code` | <strong><span style="color:red">x</span></strong>
  `locations[].country` | <strong><span style="color:red">x</span></strong>
  `accounts[].routing_number` | <strong><span style="color:red">x</span></strong>
  `accounts[].account_name` | <strong><span style="color:red">x</span></strong>
  `accounts[].institution_name` | <strong><span style="color:red">x</span></strong>
  `accounts[].account_type` | <strong><span style="color:red">x</span></strong>
  `accounts[].account_number` | <strong><span style="color:red">x</span></strong>

</details>

<details>
<summary><strong style="display:inline">Directory</strong></summary>

  Field | Support
  --- | ---
  `id` | <strong><span style="color:green">✓</span></strong>
  `first_name` | <strong><span style="color:green">✓</span></strong>
  `middle_name` | <strong><span style="color:green">✓</span></strong>
  `last_name` | <strong><span style="color:green">✓</span></strong>
  `manager.id` | <strong><span style="color:green">✓</span></strong>
  `department.name` | <strong><span style="color:green">✓</span></strong>
  `is_active` | <strong><span style="color:green">✓</span></strong>

</details>

<details>
<summary><strong style="display:inline">Individual</strong></summary>


  Field | Support
  --- | ---
  `id` | <strong><span style="color:green">✓</span></strong>
  `first_name` | <strong><span style="color:green">✓</span></strong>
  `middle_name` | <strong><span style="color:green">✓</span></strong>
  `last_name` | <strong><span style="color:green">✓</span></strong>
  `manager.id` | <strong><span style="color:green">✓</span></strong>
  `department.name` | <strong><span style="color:green">✓</span></strong>
  `is_active` | <strong><span style="color:green">✓</span></strong>

</details>

<details>
<summary><strong style="display:inline">Employment</strong></summary>


  Field | Support
  --- | ---
  `id` | <strong><span style="color:green">✓</span></strong>
  `first_name` | <strong><span style="color:green">✓</span></strong>
  `middle_name` | <strong><span style="color:green">✓</span></strong>
  `last_name` | <strong><span style="color:green">✓</span></strong>
  `manager.id` | <strong><span style="color:green">✓</span></strong>
  `department.name` | <strong><span style="color:green">✓</span></strong>
  `is_active` | <strong><span style="color:green">✓</span></strong>

</details>

<details>
<summary><strong style="display:inline">Payment</strong></summary>


  Field | Support
  --- | ---
  `id` | <strong><span style="color:green">✓</span></strong>
  `first_name` | <strong><span style="color:green">✓</span></strong>
  `middle_name` | <strong><span style="color:green">✓</span></strong>
  `last_name` | <strong><span style="color:green">✓</span></strong>
  `manager.id` | <strong><span style="color:green">✓</span></strong>
  `department.name` | <strong><span style="color:green">✓</span></strong>
  `is_active` | <strong><span style="color:green">✓</span></strong>

</details>

<details>
<summary><strong style="display:inline">Pay Statement</strong></summary>


  Field | Support
  --- | ---
  `id` | <strong><span style="color:green">✓</span></strong>
  `first_name` | <strong><span style="color:green">✓</span></strong>
  `middle_name` | <strong><span style="color:green">✓</span></strong>
  `last_name` | <strong><span style="color:green">✓</span></strong>
  `manager.id` | <strong><span style="color:green">✓</span></strong>
  `department.name` | <strong><span style="color:green">✓</span></strong>
  `is_active` | <strong><span style="color:green">✓</span></strong>

</details>

<!-- type: tab-end -->

### SageHR
<!--
type: tab
title: API
-->
<details>
<summary><strong style="display:inline">Company</strong></summary>


  Field | Support
  ---- | -----
  `id` | <strong><span style="color:green">✓</span></strong>
  `legal_name` | <strong><span style="color:green">✓</span></strong>
  `entity.type` | <strong><span style="color:green">✓</span></strong>
  `entity.subtype` | <strong><span style="color:green">✓</span></strong>
  `primary_email` | <strong><span style="color:green">✓</span></strong>
  `primary_phone_number` | <strong><span style="color:green">✓</span></strong>
  `ein` | <strong><span style="color:green">✓</span></strong>
  `departments[]` | <strong><span style="color:green">✓</span></strong>
  `departments[].parent`| <strong><span style="color:green">✓</span></strong>
  `departments[].parent.name`| <strong><span style="color:green">✓</span></strong>
  `locations[].line1` | <strong><span style="color:red">x</span></strong>
  `locations[].line2` | <strong><span style="color:red">x</span></strong>
  `locations[].city` | <strong><span style="color:red">x</span></strong>
  `locations[].state` |<strong><span style="color:red">x</span></strong>
  `locations[].postal_code` | <strong><span style="color:red">x</span></strong>
  `locations[].country` | <strong><span style="color:red">x</span></strong>
  `accounts[].routing_number` | <strong><span style="color:red">x</span></strong>
  `accounts[].account_name` | <strong><span style="color:red">x</span></strong>
  `accounts[].institution_name` | <strong><span style="color:red">x</span></strong>
  `accounts[].account_type` | <strong><span style="color:red">x</span></strong>
  `accounts[].account_number` | <strong><span style="color:red">x</span></strong>

</details>

<details>
<summary><strong style="display:inline">Directory</strong></summary>

  Field | Support
  --- | ---
  `id` | <strong><span style="color:green">✓</span></strong>
  `first_name` | <strong><span style="color:green">✓</span></strong>
  `middle_name` | <strong><span style="color:green">✓</span></strong>
  `last_name` | <strong><span style="color:green">✓</span></strong>
  `manager.id` | <strong><span style="color:green">✓</span></strong>
  `department.name` | <strong><span style="color:green">✓</span></strong>
  `is_active` | <strong><span style="color:green">✓</span></strong>

</details>

<details>
<summary><strong style="display:inline">Individual</strong></summary>


  Field | Support
  --- | ---
  `id` | <strong><span style="color:green">✓</span></strong>
  `first_name` | <strong><span style="color:green">✓</span></strong>
  `middle_name` | <strong><span style="color:green">✓</span></strong>
  `last_name` | <strong><span style="color:green">✓</span></strong>
  `manager.id` | <strong><span style="color:green">✓</span></strong>
  `department.name` | <strong><span style="color:green">✓</span></strong>
  `is_active` | <strong><span style="color:green">✓</span></strong>

</details>

<details>
<summary><strong style="display:inline">Employment</strong></summary>


  Field | Support
  --- | ---
  `id` | <strong><span style="color:green">✓</span></strong>
  `first_name` | <strong><span style="color:green">✓</span></strong>
  `middle_name` | <strong><span style="color:green">✓</span></strong>
  `last_name` | <strong><span style="color:green">✓</span></strong>
  `manager.id` | <strong><span style="color:green">✓</span></strong>
  `department.name` | <strong><span style="color:green">✓</span></strong>
  `is_active` | <strong><span style="color:green">✓</span></strong>

</details>

<details>
<summary><strong style="display:inline">Payment</strong></summary>


  Field | Support
  --- | ---
  `id` | <strong><span style="color:green">✓</span></strong>
  `first_name` | <strong><span style="color:green">✓</span></strong>
  `middle_name` | <strong><span style="color:green">✓</span></strong>
  `last_name` | <strong><span style="color:green">✓</span></strong>
  `manager.id` | <strong><span style="color:green">✓</span></strong>
  `department.name` | <strong><span style="color:green">✓</span></strong>
  `is_active` | <strong><span style="color:green">✓</span></strong>

</details>

<details>
<summary><strong style="display:inline">Pay Statement</strong></summary>


  Field | Support
  --- | ---
  `id` | <strong><span style="color:green">✓</span></strong>
  `first_name` | <strong><span style="color:green">✓</span></strong>
  `middle_name` | <strong><span style="color:green">✓</span></strong>
  `last_name` | <strong><span style="color:green">✓</span></strong>
  `manager.id` | <strong><span style="color:green">✓</span></strong>
  `department.name` | <strong><span style="color:green">✓</span></strong>
  `is_active` | <strong><span style="color:green">✓</span></strong>

</details>

<!-- type: tab-end -->

### Sapling
<!--
type: tab
title: API
-->
<details>
<summary><strong style="display:inline">Company</strong></summary>


  Field | Support
  ---- | -----
  `id` | <strong><span style="color:green">✓</span></strong>
  `legal_name` | <strong><span style="color:green">✓</span></strong>
  `entity.type` | <strong><span style="color:green">✓</span></strong>
  `entity.subtype` | <strong><span style="color:green">✓</span></strong>
  `primary_email` | <strong><span style="color:green">✓</span></strong>
  `primary_phone_number` | <strong><span style="color:green">✓</span></strong>
  `ein` | <strong><span style="color:green">✓</span></strong>
  `departments[]` | <strong><span style="color:green">✓</span></strong>
  `departments[].parent`| <strong><span style="color:green">✓</span></strong>
  `departments[].parent.name`| <strong><span style="color:green">✓</span></strong>
  `locations[].line1` | <strong><span style="color:red">x</span></strong>
  `locations[].line2` | <strong><span style="color:red">x</span></strong>
  `locations[].city` | <strong><span style="color:red">x</span></strong>
  `locations[].state` |<strong><span style="color:red">x</span></strong>
  `locations[].postal_code` | <strong><span style="color:red">x</span></strong>
  `locations[].country` | <strong><span style="color:red">x</span></strong>
  `accounts[].routing_number` | <strong><span style="color:red">x</span></strong>
  `accounts[].account_name` | <strong><span style="color:red">x</span></strong>
  `accounts[].institution_name` | <strong><span style="color:red">x</span></strong>
  `accounts[].account_type` | <strong><span style="color:red">x</span></strong>
  `accounts[].account_number` | <strong><span style="color:red">x</span></strong>

</details>

<details>
<summary><strong style="display:inline">Directory</strong></summary>

  Field | Support
  --- | ---
  `id` | <strong><span style="color:green">✓</span></strong>
  `first_name` | <strong><span style="color:green">✓</span></strong>
  `middle_name` | <strong><span style="color:green">✓</span></strong>
  `last_name` | <strong><span style="color:green">✓</span></strong>
  `manager.id` | <strong><span style="color:green">✓</span></strong>
  `department.name` | <strong><span style="color:green">✓</span></strong>
  `is_active` | <strong><span style="color:green">✓</span></strong>

</details>

<details>
<summary><strong style="display:inline">Individual</strong></summary>


  Field | Support
  --- | ---
  `id` | <strong><span style="color:green">✓</span></strong>
  `first_name` | <strong><span style="color:green">✓</span></strong>
  `middle_name` | <strong><span style="color:green">✓</span></strong>
  `last_name` | <strong><span style="color:green">✓</span></strong>
  `manager.id` | <strong><span style="color:green">✓</span></strong>
  `department.name` | <strong><span style="color:green">✓</span></strong>
  `is_active` | <strong><span style="color:green">✓</span></strong>

</details>

<details>
<summary><strong style="display:inline">Employment</strong></summary>


  Field | Support
  --- | ---
  `id` | <strong><span style="color:green">✓</span></strong>
  `first_name` | <strong><span style="color:green">✓</span></strong>
  `middle_name` | <strong><span style="color:green">✓</span></strong>
  `last_name` | <strong><span style="color:green">✓</span></strong>
  `manager.id` | <strong><span style="color:green">✓</span></strong>
  `department.name` | <strong><span style="color:green">✓</span></strong>
  `is_active` | <strong><span style="color:green">✓</span></strong>

</details>

<details>
<summary><strong style="display:inline">Payment</strong></summary>


  Field | Support
  --- | ---
  `id` | <strong><span style="color:green">✓</span></strong>
  `first_name` | <strong><span style="color:green">✓</span></strong>
  `middle_name` | <strong><span style="color:green">✓</span></strong>
  `last_name` | <strong><span style="color:green">✓</span></strong>
  `manager.id` | <strong><span style="color:green">✓</span></strong>
  `department.name` | <strong><span style="color:green">✓</span></strong>
  `is_active` | <strong><span style="color:green">✓</span></strong>

</details>

<details>
<summary><strong style="display:inline">Pay Statement</strong></summary>


  Field | Support
  --- | ---
  `id` | <strong><span style="color:green">✓</span></strong>
  `first_name` | <strong><span style="color:green">✓</span></strong>
  `middle_name` | <strong><span style="color:green">✓</span></strong>
  `last_name` | <strong><span style="color:green">✓</span></strong>
  `manager.id` | <strong><span style="color:green">✓</span></strong>
  `department.name` | <strong><span style="color:green">✓</span></strong>
  `is_active` | <strong><span style="color:green">✓</span></strong>

</details>

<!-- type: tab-end -->

### Sequioa One
<!--
type: tab
title: Credentials
-->
<details>
<summary><strong style="display:inline">Company</strong></summary>


  Field | Support
  ---- | -----
  `id` | <strong><span style="color:green">✓</span></strong>
  `legal_name` | <strong><span style="color:green">✓</span></strong>
  `entity.type` | <strong><span style="color:green">✓</span></strong>
  `entity.subtype` | <strong><span style="color:green">✓</span></strong>
  `primary_email` | <strong><span style="color:green">✓</span></strong>
  `primary_phone_number` | <strong><span style="color:green">✓</span></strong>
  `ein` | <strong><span style="color:green">✓</span></strong>
  `departments[]` | <strong><span style="color:green">✓</span></strong>
  `departments[].parent`| <strong><span style="color:green">✓</span></strong>
  `departments[].parent.name`| <strong><span style="color:green">✓</span></strong>
  `locations[].line1` | <strong><span style="color:red">x</span></strong>
  `locations[].line2` | <strong><span style="color:red">x</span></strong>
  `locations[].city` | <strong><span style="color:red">x</span></strong>
  `locations[].state` |<strong><span style="color:red">x</span></strong>
  `locations[].postal_code` | <strong><span style="color:red">x</span></strong>
  `locations[].country` | <strong><span style="color:red">x</span></strong>
  `accounts[].routing_number` | <strong><span style="color:red">x</span></strong>
  `accounts[].account_name` | <strong><span style="color:red">x</span></strong>
  `accounts[].institution_name` | <strong><span style="color:red">x</span></strong>
  `accounts[].account_type` | <strong><span style="color:red">x</span></strong>
  `accounts[].account_number` | <strong><span style="color:red">x</span></strong>

</details>

<details>
<summary><strong style="display:inline">Directory</strong></summary>

  Field | Support
  --- | ---
  `id` | <strong><span style="color:green">✓</span></strong>
  `first_name` | <strong><span style="color:green">✓</span></strong>
  `middle_name` | <strong><span style="color:green">✓</span></strong>
  `last_name` | <strong><span style="color:green">✓</span></strong>
  `manager.id` | <strong><span style="color:green">✓</span></strong>
  `department.name` | <strong><span style="color:green">✓</span></strong>
  `is_active` | <strong><span style="color:green">✓</span></strong>

</details>

<details>
<summary><strong style="display:inline">Individual</strong></summary>


  Field | Support
  --- | ---
  `id` | <strong><span style="color:green">✓</span></strong>
  `first_name` | <strong><span style="color:green">✓</span></strong>
  `middle_name` | <strong><span style="color:green">✓</span></strong>
  `last_name` | <strong><span style="color:green">✓</span></strong>
  `manager.id` | <strong><span style="color:green">✓</span></strong>
  `department.name` | <strong><span style="color:green">✓</span></strong>
  `is_active` | <strong><span style="color:green">✓</span></strong>

</details>

<details>
<summary><strong style="display:inline">Employment</strong></summary>


  Field | Support
  --- | ---
  `id` | <strong><span style="color:green">✓</span></strong>
  `first_name` | <strong><span style="color:green">✓</span></strong>
  `middle_name` | <strong><span style="color:green">✓</span></strong>
  `last_name` | <strong><span style="color:green">✓</span></strong>
  `manager.id` | <strong><span style="color:green">✓</span></strong>
  `department.name` | <strong><span style="color:green">✓</span></strong>
  `is_active` | <strong><span style="color:green">✓</span></strong>

</details>

<details>
<summary><strong style="display:inline">Payment</strong></summary>


  Field | Support
  --- | ---
  `id` | <strong><span style="color:green">✓</span></strong>
  `first_name` | <strong><span style="color:green">✓</span></strong>
  `middle_name` | <strong><span style="color:green">✓</span></strong>
  `last_name` | <strong><span style="color:green">✓</span></strong>
  `manager.id` | <strong><span style="color:green">✓</span></strong>
  `department.name` | <strong><span style="color:green">✓</span></strong>
  `is_active` | <strong><span style="color:green">✓</span></strong>

</details>

<details>
<summary><strong style="display:inline">Pay Statement</strong></summary>


  Field | Support
  --- | ---
  `id` | <strong><span style="color:green">✓</span></strong>
  `first_name` | <strong><span style="color:green">✓</span></strong>
  `middle_name` | <strong><span style="color:green">✓</span></strong>
  `last_name` | <strong><span style="color:green">✓</span></strong>
  `manager.id` | <strong><span style="color:green">✓</span></strong>
  `department.name` | <strong><span style="color:green">✓</span></strong>
  `is_active` | <strong><span style="color:green">✓</span></strong>

</details>

<!-- type: tab-end -->

### Square Payroll
<!--
type: tab
title: Credentials
-->
<details>
<summary><strong style="display:inline">Company</strong></summary>


  Field | Support
  ---- | -----
  `id` | <strong><span style="color:green">✓</span></strong>
  `legal_name` | <strong><span style="color:green">✓</span></strong>
  `entity.type` | <strong><span style="color:green">✓</span></strong>
  `entity.subtype` | <strong><span style="color:green">✓</span></strong>
  `primary_email` | <strong><span style="color:green">✓</span></strong>
  `primary_phone_number` | <strong><span style="color:green">✓</span></strong>
  `ein` | <strong><span style="color:green">✓</span></strong>
  `departments[]` | <strong><span style="color:green">✓</span></strong>
  `departments[].parent`| <strong><span style="color:green">✓</span></strong>
  `departments[].parent.name`| <strong><span style="color:green">✓</span></strong>
  `locations[].line1` | <strong><span style="color:red">x</span></strong>
  `locations[].line2` | <strong><span style="color:red">x</span></strong>
  `locations[].city` | <strong><span style="color:red">x</span></strong>
  `locations[].state` |<strong><span style="color:red">x</span></strong>
  `locations[].postal_code` | <strong><span style="color:red">x</span></strong>
  `locations[].country` | <strong><span style="color:red">x</span></strong>
  `accounts[].routing_number` | <strong><span style="color:red">x</span></strong>
  `accounts[].account_name` | <strong><span style="color:red">x</span></strong>
  `accounts[].institution_name` | <strong><span style="color:red">x</span></strong>
  `accounts[].account_type` | <strong><span style="color:red">x</span></strong>
  `accounts[].account_number` | <strong><span style="color:red">x</span></strong>

</details>

<details>
<summary><strong style="display:inline">Directory</strong></summary>

  Field | Support
  --- | ---
  `id` | <strong><span style="color:green">✓</span></strong>
  `first_name` | <strong><span style="color:green">✓</span></strong>
  `middle_name` | <strong><span style="color:green">✓</span></strong>
  `last_name` | <strong><span style="color:green">✓</span></strong>
  `manager.id` | <strong><span style="color:green">✓</span></strong>
  `department.name` | <strong><span style="color:green">✓</span></strong>
  `is_active` | <strong><span style="color:green">✓</span></strong>

</details>

<details>
<summary><strong style="display:inline">Individual</strong></summary>


  Field | Support
  --- | ---
  `id` | <strong><span style="color:green">✓</span></strong>
  `first_name` | <strong><span style="color:green">✓</span></strong>
  `middle_name` | <strong><span style="color:green">✓</span></strong>
  `last_name` | <strong><span style="color:green">✓</span></strong>
  `manager.id` | <strong><span style="color:green">✓</span></strong>
  `department.name` | <strong><span style="color:green">✓</span></strong>
  `is_active` | <strong><span style="color:green">✓</span></strong>

</details>

<details>
<summary><strong style="display:inline">Employment</strong></summary>


  Field | Support
  --- | ---
  `id` | <strong><span style="color:green">✓</span></strong>
  `first_name` | <strong><span style="color:green">✓</span></strong>
  `middle_name` | <strong><span style="color:green">✓</span></strong>
  `last_name` | <strong><span style="color:green">✓</span></strong>
  `manager.id` | <strong><span style="color:green">✓</span></strong>
  `department.name` | <strong><span style="color:green">✓</span></strong>
  `is_active` | <strong><span style="color:green">✓</span></strong>

</details>

<details>
<summary><strong style="display:inline">Payment</strong></summary>


  Field | Support
  --- | ---
  `id` | <strong><span style="color:green">✓</span></strong>
  `first_name` | <strong><span style="color:green">✓</span></strong>
  `middle_name` | <strong><span style="color:green">✓</span></strong>
  `last_name` | <strong><span style="color:green">✓</span></strong>
  `manager.id` | <strong><span style="color:green">✓</span></strong>
  `department.name` | <strong><span style="color:green">✓</span></strong>
  `is_active` | <strong><span style="color:green">✓</span></strong>

</details>

<details>
<summary><strong style="display:inline">Pay Statement</strong></summary>


  Field | Support
  --- | ---
  `id` | <strong><span style="color:green">✓</span></strong>
  `first_name` | <strong><span style="color:green">✓</span></strong>
  `middle_name` | <strong><span style="color:green">✓</span></strong>
  `last_name` | <strong><span style="color:green">✓</span></strong>
  `manager.id` | <strong><span style="color:green">✓</span></strong>
  `department.name` | <strong><span style="color:green">✓</span></strong>
  `is_active` | <strong><span style="color:green">✓</span></strong>

</details>

<!--
type: tab
title: API
-->
<details>
<summary><strong style="display:inline">Company</strong></summary>


  Field | Support
  ---- | -----
  `id` | <strong><span style="color:green">✓</span></strong>
  `legal_name` | <strong><span style="color:green">✓</span></strong>
  `entity.type` | <strong><span style="color:green">✓</span></strong>
  `entity.subtype` | <strong><span style="color:green">✓</span></strong>
  `primary_email` | <strong><span style="color:green">✓</span></strong>
  `primary_phone_number` | <strong><span style="color:green">✓</span></strong>
  `ein` | <strong><span style="color:green">✓</span></strong>
  `departments[]` | <strong><span style="color:green">✓</span></strong>
  `departments[].parent`| <strong><span style="color:green">✓</span></strong>
  `departments[].parent.name`| <strong><span style="color:green">✓</span></strong>
  `locations[].line1` | <strong><span style="color:red">x</span></strong>
  `locations[].line2` | <strong><span style="color:red">x</span></strong>
  `locations[].city` | <strong><span style="color:red">x</span></strong>
  `locations[].state` |<strong><span style="color:red">x</span></strong>
  `locations[].postal_code` | <strong><span style="color:red">x</span></strong>
  `locations[].country` | <strong><span style="color:red">x</span></strong>
  `accounts[].routing_number` | <strong><span style="color:red">x</span></strong>
  `accounts[].account_name` | <strong><span style="color:red">x</span></strong>
  `accounts[].institution_name` | <strong><span style="color:red">x</span></strong>
  `accounts[].account_type` | <strong><span style="color:red">x</span></strong>
  `accounts[].account_number` | <strong><span style="color:red">x</span></strong>

</details>

<details>
<summary><strong style="display:inline">Directory</strong></summary>

  Field | Support
  --- | ---
  `id` | <strong><span style="color:green">✓</span></strong>
  `first_name` | <strong><span style="color:green">✓</span></strong>
  `middle_name` | <strong><span style="color:green">✓</span></strong>
  `last_name` | <strong><span style="color:green">✓</span></strong>
  `manager.id` | <strong><span style="color:green">✓</span></strong>
  `department.name` | <strong><span style="color:green">✓</span></strong>
  `is_active` | <strong><span style="color:green">✓</span></strong>

</details>

<details>
<summary><strong style="display:inline">Individual</strong></summary>


  Field | Support
  --- | ---
  `id` | <strong><span style="color:green">✓</span></strong>
  `first_name` | <strong><span style="color:green">✓</span></strong>
  `middle_name` | <strong><span style="color:green">✓</span></strong>
  `last_name` | <strong><span style="color:green">✓</span></strong>
  `manager.id` | <strong><span style="color:green">✓</span></strong>
  `department.name` | <strong><span style="color:green">✓</span></strong>
  `is_active` | <strong><span style="color:green">✓</span></strong>

</details>

<details>
<summary><strong style="display:inline">Employment</strong></summary>


  Field | Support
  --- | ---
  `id` | <strong><span style="color:green">✓</span></strong>
  `first_name` | <strong><span style="color:green">✓</span></strong>
  `middle_name` | <strong><span style="color:green">✓</span></strong>
  `last_name` | <strong><span style="color:green">✓</span></strong>
  `manager.id` | <strong><span style="color:green">✓</span></strong>
  `department.name` | <strong><span style="color:green">✓</span></strong>
  `is_active` | <strong><span style="color:green">✓</span></strong>

</details>

<details>
<summary><strong style="display:inline">Payment</strong></summary>


  Field | Support
  --- | ---
  `id` | <strong><span style="color:green">✓</span></strong>
  `first_name` | <strong><span style="color:green">✓</span></strong>
  `middle_name` | <strong><span style="color:green">✓</span></strong>
  `last_name` | <strong><span style="color:green">✓</span></strong>
  `manager.id` | <strong><span style="color:green">✓</span></strong>
  `department.name` | <strong><span style="color:green">✓</span></strong>
  `is_active` | <strong><span style="color:green">✓</span></strong>

</details>

<details>
<summary><strong style="display:inline">Pay Statement</strong></summary>


  Field | Support
  --- | ---
  `id` | <strong><span style="color:green">✓</span></strong>
  `first_name` | <strong><span style="color:green">✓</span></strong>
  `middle_name` | <strong><span style="color:green">✓</span></strong>
  `last_name` | <strong><span style="color:green">✓</span></strong>
  `manager.id` | <strong><span style="color:green">✓</span></strong>
  `department.name` | <strong><span style="color:green">✓</span></strong>
  `is_active` | <strong><span style="color:green">✓</span></strong>

</details>

<!-- type: tab-end -->

### TriNet
<!--
type: tab
title: Credentials
-->
<details>
<summary><strong style="display:inline">Company</strong></summary>


  Field | Support
  ---- | -----
  `id` | <strong><span style="color:green">✓</span></strong>
  `legal_name` | <strong><span style="color:green">✓</span></strong>
  `entity.type` | <strong><span style="color:green">✓</span></strong>
  `entity.subtype` | <strong><span style="color:green">✓</span></strong>
  `primary_email` | <strong><span style="color:green">✓</span></strong>
  `primary_phone_number` | <strong><span style="color:green">✓</span></strong>
  `ein` | <strong><span style="color:green">✓</span></strong>
  `departments[]` | <strong><span style="color:green">✓</span></strong>
  `departments[].parent`| <strong><span style="color:green">✓</span></strong>
  `departments[].parent.name`| <strong><span style="color:green">✓</span></strong>
  `locations[].line1` | <strong><span style="color:red">x</span></strong>
  `locations[].line2` | <strong><span style="color:red">x</span></strong>
  `locations[].city` | <strong><span style="color:red">x</span></strong>
  `locations[].state` |<strong><span style="color:red">x</span></strong>
  `locations[].postal_code` | <strong><span style="color:red">x</span></strong>
  `locations[].country` | <strong><span style="color:red">x</span></strong>
  `accounts[].routing_number` | <strong><span style="color:red">x</span></strong>
  `accounts[].account_name` | <strong><span style="color:red">x</span></strong>
  `accounts[].institution_name` | <strong><span style="color:red">x</span></strong>
  `accounts[].account_type` | <strong><span style="color:red">x</span></strong>
  `accounts[].account_number` | <strong><span style="color:red">x</span></strong>

</details>

<details>
<summary><strong style="display:inline">Directory</strong></summary>

  Field | Support
  --- | ---
  `id` | <strong><span style="color:green">✓</span></strong>
  `first_name` | <strong><span style="color:green">✓</span></strong>
  `middle_name` | <strong><span style="color:green">✓</span></strong>
  `last_name` | <strong><span style="color:green">✓</span></strong>
  `manager.id` | <strong><span style="color:green">✓</span></strong>
  `department.name` | <strong><span style="color:green">✓</span></strong>
  `is_active` | <strong><span style="color:green">✓</span></strong>

</details>

<details>
<summary><strong style="display:inline">Individual</strong></summary>


  Field | Support
  --- | ---
  `id` | <strong><span style="color:green">✓</span></strong>
  `first_name` | <strong><span style="color:green">✓</span></strong>
  `middle_name` | <strong><span style="color:green">✓</span></strong>
  `last_name` | <strong><span style="color:green">✓</span></strong>
  `manager.id` | <strong><span style="color:green">✓</span></strong>
  `department.name` | <strong><span style="color:green">✓</span></strong>
  `is_active` | <strong><span style="color:green">✓</span></strong>

</details>

<details>
<summary><strong style="display:inline">Employment</strong></summary>


  Field | Support
  --- | ---
  `id` | <strong><span style="color:green">✓</span></strong>
  `first_name` | <strong><span style="color:green">✓</span></strong>
  `middle_name` | <strong><span style="color:green">✓</span></strong>
  `last_name` | <strong><span style="color:green">✓</span></strong>
  `manager.id` | <strong><span style="color:green">✓</span></strong>
  `department.name` | <strong><span style="color:green">✓</span></strong>
  `is_active` | <strong><span style="color:green">✓</span></strong>

</details>

<details>
<summary><strong style="display:inline">Payment</strong></summary>


  Field | Support
  --- | ---
  `id` | <strong><span style="color:green">✓</span></strong>
  `first_name` | <strong><span style="color:green">✓</span></strong>
  `middle_name` | <strong><span style="color:green">✓</span></strong>
  `last_name` | <strong><span style="color:green">✓</span></strong>
  `manager.id` | <strong><span style="color:green">✓</span></strong>
  `department.name` | <strong><span style="color:green">✓</span></strong>
  `is_active` | <strong><span style="color:green">✓</span></strong>

</details>

<details>
<summary><strong style="display:inline">Pay Statement</strong></summary>


  Field | Support
  --- | ---
  `id` | <strong><span style="color:green">✓</span></strong>
  `first_name` | <strong><span style="color:green">✓</span></strong>
  `middle_name` | <strong><span style="color:green">✓</span></strong>
  `last_name` | <strong><span style="color:green">✓</span></strong>
  `manager.id` | <strong><span style="color:green">✓</span></strong>
  `department.name` | <strong><span style="color:green">✓</span></strong>
  `is_active` | <strong><span style="color:green">✓</span></strong>

</details>

<!--
type: tab
title: API
-->
<details>
<summary><strong style="display:inline">Company</strong></summary>


  Field | Support
  ---- | -----
  `id` | <strong><span style="color:green">✓</span></strong>
  `legal_name` | <strong><span style="color:green">✓</span></strong>
  `entity.type` | <strong><span style="color:green">✓</span></strong>
  `entity.subtype` | <strong><span style="color:green">✓</span></strong>
  `primary_email` | <strong><span style="color:green">✓</span></strong>
  `primary_phone_number` | <strong><span style="color:green">✓</span></strong>
  `ein` | <strong><span style="color:green">✓</span></strong>
  `departments[]` | <strong><span style="color:green">✓</span></strong>
  `departments[].parent`| <strong><span style="color:green">✓</span></strong>
  `departments[].parent.name`| <strong><span style="color:green">✓</span></strong>
  `locations[].line1` | <strong><span style="color:red">x</span></strong>
  `locations[].line2` | <strong><span style="color:red">x</span></strong>
  `locations[].city` | <strong><span style="color:red">x</span></strong>
  `locations[].state` |<strong><span style="color:red">x</span></strong>
  `locations[].postal_code` | <strong><span style="color:red">x</span></strong>
  `locations[].country` | <strong><span style="color:red">x</span></strong>
  `accounts[].routing_number` | <strong><span style="color:red">x</span></strong>
  `accounts[].account_name` | <strong><span style="color:red">x</span></strong>
  `accounts[].institution_name` | <strong><span style="color:red">x</span></strong>
  `accounts[].account_type` | <strong><span style="color:red">x</span></strong>
  `accounts[].account_number` | <strong><span style="color:red">x</span></strong>

</details>

<details>
<summary><strong style="display:inline">Directory</strong></summary>

  Field | Support
  --- | ---
  `id` | <strong><span style="color:green">✓</span></strong>
  `first_name` | <strong><span style="color:green">✓</span></strong>
  `middle_name` | <strong><span style="color:green">✓</span></strong>
  `last_name` | <strong><span style="color:green">✓</span></strong>
  `manager.id` | <strong><span style="color:green">✓</span></strong>
  `department.name` | <strong><span style="color:green">✓</span></strong>
  `is_active` | <strong><span style="color:green">✓</span></strong>

</details>

<details>
<summary><strong style="display:inline">Individual</strong></summary>


  Field | Support
  --- | ---
  `id` | <strong><span style="color:green">✓</span></strong>
  `first_name` | <strong><span style="color:green">✓</span></strong>
  `middle_name` | <strong><span style="color:green">✓</span></strong>
  `last_name` | <strong><span style="color:green">✓</span></strong>
  `manager.id` | <strong><span style="color:green">✓</span></strong>
  `department.name` | <strong><span style="color:green">✓</span></strong>
  `is_active` | <strong><span style="color:green">✓</span></strong>

</details>

<details>
<summary><strong style="display:inline">Employment</strong></summary>


  Field | Support
  --- | ---
  `id` | <strong><span style="color:green">✓</span></strong>
  `first_name` | <strong><span style="color:green">✓</span></strong>
  `middle_name` | <strong><span style="color:green">✓</span></strong>
  `last_name` | <strong><span style="color:green">✓</span></strong>
  `manager.id` | <strong><span style="color:green">✓</span></strong>
  `department.name` | <strong><span style="color:green">✓</span></strong>
  `is_active` | <strong><span style="color:green">✓</span></strong>

</details>

<details>
<summary><strong style="display:inline">Payment</strong></summary>


  Field | Support
  --- | ---
  `id` | <strong><span style="color:green">✓</span></strong>
  `first_name` | <strong><span style="color:green">✓</span></strong>
  `middle_name` | <strong><span style="color:green">✓</span></strong>
  `last_name` | <strong><span style="color:green">✓</span></strong>
  `manager.id` | <strong><span style="color:green">✓</span></strong>
  `department.name` | <strong><span style="color:green">✓</span></strong>
  `is_active` | <strong><span style="color:green">✓</span></strong>

</details>

<details>
<summary><strong style="display:inline">Pay Statement</strong></summary>


  Field | Support
  --- | ---
  `id` | <strong><span style="color:green">✓</span></strong>
  `first_name` | <strong><span style="color:green">✓</span></strong>
  `middle_name` | <strong><span style="color:green">✓</span></strong>
  `last_name` | <strong><span style="color:green">✓</span></strong>
  `manager.id` | <strong><span style="color:green">✓</span></strong>
  `department.name` | <strong><span style="color:green">✓</span></strong>
  `is_active` | <strong><span style="color:green">✓</span></strong>

</details>

<!-- type: tab-end -->


### UKG Pro
<!--
type: tab
title: API
-->
<details>
<summary><strong style="display:inline">Company</strong></summary>


  Field | Support
  ---- | -----
  `id` | <strong><span style="color:green">✓</span></strong>
  `legal_name` | <strong><span style="color:green">✓</span></strong>
  `entity.type` | <strong><span style="color:green">✓</span></strong>
  `entity.subtype` | <strong><span style="color:green">✓</span></strong>
  `primary_email` | <strong><span style="color:green">✓</span></strong>
  `primary_phone_number` | <strong><span style="color:green">✓</span></strong>
  `ein` | <strong><span style="color:green">✓</span></strong>
  `departments[]` | <strong><span style="color:green">✓</span></strong>
  `departments[].parent`| <strong><span style="color:green">✓</span></strong>
  `departments[].parent.name`| <strong><span style="color:green">✓</span></strong>
  `locations[].line1` | <strong><span style="color:red">x</span></strong>
  `locations[].line2` | <strong><span style="color:red">x</span></strong>
  `locations[].city` | <strong><span style="color:red">x</span></strong>
  `locations[].state` |<strong><span style="color:red">x</span></strong>
  `locations[].postal_code` | <strong><span style="color:red">x</span></strong>
  `locations[].country` | <strong><span style="color:red">x</span></strong>
  `accounts[].routing_number` | <strong><span style="color:red">x</span></strong>
  `accounts[].account_name` | <strong><span style="color:red">x</span></strong>
  `accounts[].institution_name` | <strong><span style="color:red">x</span></strong>
  `accounts[].account_type` | <strong><span style="color:red">x</span></strong>
  `accounts[].account_number` | <strong><span style="color:red">x</span></strong>

</details>

<details>
<summary><strong style="display:inline">Directory</strong></summary>

  Field | Support
  --- | ---
  `id` | <strong><span style="color:green">✓</span></strong>
  `first_name` | <strong><span style="color:green">✓</span></strong>
  `middle_name` | <strong><span style="color:green">✓</span></strong>
  `last_name` | <strong><span style="color:green">✓</span></strong>
  `manager.id` | <strong><span style="color:green">✓</span></strong>
  `department.name` | <strong><span style="color:green">✓</span></strong>
  `is_active` | <strong><span style="color:green">✓</span></strong>

</details>

<details>
<summary><strong style="display:inline">Individual</strong></summary>


  Field | Support
  --- | ---
  `id` | <strong><span style="color:green">✓</span></strong>
  `first_name` | <strong><span style="color:green">✓</span></strong>
  `middle_name` | <strong><span style="color:green">✓</span></strong>
  `last_name` | <strong><span style="color:green">✓</span></strong>
  `manager.id` | <strong><span style="color:green">✓</span></strong>
  `department.name` | <strong><span style="color:green">✓</span></strong>
  `is_active` | <strong><span style="color:green">✓</span></strong>

</details>

<details>
<summary><strong style="display:inline">Employment</strong></summary>


  Field | Support
  --- | ---
  `id` | <strong><span style="color:green">✓</span></strong>
  `first_name` | <strong><span style="color:green">✓</span></strong>
  `middle_name` | <strong><span style="color:green">✓</span></strong>
  `last_name` | <strong><span style="color:green">✓</span></strong>
  `manager.id` | <strong><span style="color:green">✓</span></strong>
  `department.name` | <strong><span style="color:green">✓</span></strong>
  `is_active` | <strong><span style="color:green">✓</span></strong>

</details>

<details>
<summary><strong style="display:inline">Payment</strong></summary>


  Field | Support
  --- | ---
  `id` | <strong><span style="color:green">✓</span></strong>
  `first_name` | <strong><span style="color:green">✓</span></strong>
  `middle_name` | <strong><span style="color:green">✓</span></strong>
  `last_name` | <strong><span style="color:green">✓</span></strong>
  `manager.id` | <strong><span style="color:green">✓</span></strong>
  `department.name` | <strong><span style="color:green">✓</span></strong>
  `is_active` | <strong><span style="color:green">✓</span></strong>

</details>

<details>
<summary><strong style="display:inline">Pay Statement</strong></summary>


  Field | Support
  --- | ---
  `id` | <strong><span style="color:green">✓</span></strong>
  `first_name` | <strong><span style="color:green">✓</span></strong>
  `middle_name` | <strong><span style="color:green">✓</span></strong>
  `last_name` | <strong><span style="color:green">✓</span></strong>
  `manager.id` | <strong><span style="color:green">✓</span></strong>
  `department.name` | <strong><span style="color:green">✓</span></strong>
  `is_active` | <strong><span style="color:green">✓</span></strong>

</details>

<!-- type: tab-end -->

### Wave
<!--
type: tab
title: Credentials
-->
<details>
<summary><strong style="display:inline">Company</strong></summary>


  Field | Support
  ---- | -----
  `id` | <strong><span style="color:green">✓</span></strong>
  `legal_name` | <strong><span style="color:green">✓</span></strong>
  `entity.type` | <strong><span style="color:green">✓</span></strong>
  `entity.subtype` | <strong><span style="color:green">✓</span></strong>
  `primary_email` | <strong><span style="color:green">✓</span></strong>
  `primary_phone_number` | <strong><span style="color:green">✓</span></strong>
  `ein` | <strong><span style="color:green">✓</span></strong>
  `departments[]` | <strong><span style="color:green">✓</span></strong>
  `departments[].parent`| <strong><span style="color:green">✓</span></strong>
  `departments[].parent.name`| <strong><span style="color:green">✓</span></strong>
  `locations[].line1` | <strong><span style="color:red">x</span></strong>
  `locations[].line2` | <strong><span style="color:red">x</span></strong>
  `locations[].city` | <strong><span style="color:red">x</span></strong>
  `locations[].state` |<strong><span style="color:red">x</span></strong>
  `locations[].postal_code` | <strong><span style="color:red">x</span></strong>
  `locations[].country` | <strong><span style="color:red">x</span></strong>
  `accounts[].routing_number` | <strong><span style="color:red">x</span></strong>
  `accounts[].account_name` | <strong><span style="color:red">x</span></strong>
  `accounts[].institution_name` | <strong><span style="color:red">x</span></strong>
  `accounts[].account_type` | <strong><span style="color:red">x</span></strong>
  `accounts[].account_number` | <strong><span style="color:red">x</span></strong>

</details>

<details>
<summary><strong style="display:inline">Directory</strong></summary>

  Field | Support
  --- | ---
  `id` | <strong><span style="color:green">✓</span></strong>
  `first_name` | <strong><span style="color:green">✓</span></strong>
  `middle_name` | <strong><span style="color:green">✓</span></strong>
  `last_name` | <strong><span style="color:green">✓</span></strong>
  `manager.id` | <strong><span style="color:green">✓</span></strong>
  `department.name` | <strong><span style="color:green">✓</span></strong>
  `is_active` | <strong><span style="color:green">✓</span></strong>

</details>

<details>
<summary><strong style="display:inline">Individual</strong></summary>


  Field | Support
  --- | ---
  `id` | <strong><span style="color:green">✓</span></strong>
  `first_name` | <strong><span style="color:green">✓</span></strong>
  `middle_name` | <strong><span style="color:green">✓</span></strong>
  `last_name` | <strong><span style="color:green">✓</span></strong>
  `manager.id` | <strong><span style="color:green">✓</span></strong>
  `department.name` | <strong><span style="color:green">✓</span></strong>
  `is_active` | <strong><span style="color:green">✓</span></strong>

</details>

<details>
<summary><strong style="display:inline">Employment</strong></summary>


  Field | Support
  --- | ---
  `id` | <strong><span style="color:green">✓</span></strong>
  `first_name` | <strong><span style="color:green">✓</span></strong>
  `middle_name` | <strong><span style="color:green">✓</span></strong>
  `last_name` | <strong><span style="color:green">✓</span></strong>
  `manager.id` | <strong><span style="color:green">✓</span></strong>
  `department.name` | <strong><span style="color:green">✓</span></strong>
  `is_active` | <strong><span style="color:green">✓</span></strong>

</details>

<details>
<summary><strong style="display:inline">Payment</strong></summary>


  Field | Support
  --- | ---
  `id` | <strong><span style="color:green">✓</span></strong>
  `first_name` | <strong><span style="color:green">✓</span></strong>
  `middle_name` | <strong><span style="color:green">✓</span></strong>
  `last_name` | <strong><span style="color:green">✓</span></strong>
  `manager.id` | <strong><span style="color:green">✓</span></strong>
  `department.name` | <strong><span style="color:green">✓</span></strong>
  `is_active` | <strong><span style="color:green">✓</span></strong>

</details>

<details>
<summary><strong style="display:inline">Pay Statement</strong></summary>


  Field | Support
  --- | ---
  `id` | <strong><span style="color:green">✓</span></strong>
  `first_name` | <strong><span style="color:green">✓</span></strong>
  `middle_name` | <strong><span style="color:green">✓</span></strong>
  `last_name` | <strong><span style="color:green">✓</span></strong>
  `manager.id` | <strong><span style="color:green">✓</span></strong>
  `department.name` | <strong><span style="color:green">✓</span></strong>
  `is_active` | <strong><span style="color:green">✓</span></strong>

</details>

<!-- type: tab-end -->

### Workday
<!--
type: tab
title: Credentials
-->
<details>
<summary><strong style="display:inline">Company</strong></summary>


  Field | Support
  ---- | -----
  `id` | <strong><span style="color:green">✓</span></strong>
  `legal_name` | <strong><span style="color:green">✓</span></strong>
  `entity.type` | <strong><span style="color:green">✓</span></strong>
  `entity.subtype` | <strong><span style="color:green">✓</span></strong>
  `primary_email` | <strong><span style="color:green">✓</span></strong>
  `primary_phone_number` | <strong><span style="color:green">✓</span></strong>
  `ein` | <strong><span style="color:green">✓</span></strong>
  `departments[]` | <strong><span style="color:green">✓</span></strong>
  `departments[].parent`| <strong><span style="color:green">✓</span></strong>
  `departments[].parent.name`| <strong><span style="color:green">✓</span></strong>
  `locations[].line1` | <strong><span style="color:red">x</span></strong>
  `locations[].line2` | <strong><span style="color:red">x</span></strong>
  `locations[].city` | <strong><span style="color:red">x</span></strong>
  `locations[].state` |<strong><span style="color:red">x</span></strong>
  `locations[].postal_code` | <strong><span style="color:red">x</span></strong>
  `locations[].country` | <strong><span style="color:red">x</span></strong>
  `accounts[].routing_number` | <strong><span style="color:red">x</span></strong>
  `accounts[].account_name` | <strong><span style="color:red">x</span></strong>
  `accounts[].institution_name` | <strong><span style="color:red">x</span></strong>
  `accounts[].account_type` | <strong><span style="color:red">x</span></strong>
  `accounts[].account_number` | <strong><span style="color:red">x</span></strong>

</details>

<details>
<summary><strong style="display:inline">Directory</strong></summary>

  Field | Support
  --- | ---
  `id` | <strong><span style="color:green">✓</span></strong>
  `first_name` | <strong><span style="color:green">✓</span></strong>
  `middle_name` | <strong><span style="color:green">✓</span></strong>
  `last_name` | <strong><span style="color:green">✓</span></strong>
  `manager.id` | <strong><span style="color:green">✓</span></strong>
  `department.name` | <strong><span style="color:green">✓</span></strong>
  `is_active` | <strong><span style="color:green">✓</span></strong>

</details>

<details>
<summary><strong style="display:inline">Individual</strong></summary>


  Field | Support
  --- | ---
  `id` | <strong><span style="color:green">✓</span></strong>
  `first_name` | <strong><span style="color:green">✓</span></strong>
  `middle_name` | <strong><span style="color:green">✓</span></strong>
  `last_name` | <strong><span style="color:green">✓</span></strong>
  `manager.id` | <strong><span style="color:green">✓</span></strong>
  `department.name` | <strong><span style="color:green">✓</span></strong>
  `is_active` | <strong><span style="color:green">✓</span></strong>

</details>

<details>
<summary><strong style="display:inline">Employment</strong></summary>


  Field | Support
  --- | ---
  `id` | <strong><span style="color:green">✓</span></strong>
  `first_name` | <strong><span style="color:green">✓</span></strong>
  `middle_name` | <strong><span style="color:green">✓</span></strong>
  `last_name` | <strong><span style="color:green">✓</span></strong>
  `manager.id` | <strong><span style="color:green">✓</span></strong>
  `department.name` | <strong><span style="color:green">✓</span></strong>
  `is_active` | <strong><span style="color:green">✓</span></strong>

</details>

<details>
<summary><strong style="display:inline">Payment</strong></summary>


  Field | Support
  --- | ---
  `id` | <strong><span style="color:green">✓</span></strong>
  `first_name` | <strong><span style="color:green">✓</span></strong>
  `middle_name` | <strong><span style="color:green">✓</span></strong>
  `last_name` | <strong><span style="color:green">✓</span></strong>
  `manager.id` | <strong><span style="color:green">✓</span></strong>
  `department.name` | <strong><span style="color:green">✓</span></strong>
  `is_active` | <strong><span style="color:green">✓</span></strong>

</details>

<details>
<summary><strong style="display:inline">Pay Statement</strong></summary>


  Field | Support
  --- | ---
  `id` | <strong><span style="color:green">✓</span></strong>
  `first_name` | <strong><span style="color:green">✓</span></strong>
  `middle_name` | <strong><span style="color:green">✓</span></strong>
  `last_name` | <strong><span style="color:green">✓</span></strong>
  `manager.id` | <strong><span style="color:green">✓</span></strong>
  `department.name` | <strong><span style="color:green">✓</span></strong>
  `is_active` | <strong><span style="color:green">✓</span></strong>

</details>

<!-- type: tab-end -->

### Zenefits
<!--
type: tab
title: Credentials
-->
<details>
<summary><strong style="display:inline">Company</strong></summary>


  Field | Support
  ---- | -----
  `id` | <strong><span style="color:green">✓</span></strong>
  `legal_name` | <strong><span style="color:green">✓</span></strong>
  `entity.type` | <strong><span style="color:green">✓</span></strong>
  `entity.subtype` | <strong><span style="color:green">✓</span></strong>
  `primary_email` | <strong><span style="color:green">✓</span></strong>
  `primary_phone_number` | <strong><span style="color:green">✓</span></strong>
  `ein` | <strong><span style="color:green">✓</span></strong>
  `departments[]` | <strong><span style="color:green">✓</span></strong>
  `departments[].parent`| <strong><span style="color:green">✓</span></strong>
  `departments[].parent.name`| <strong><span style="color:green">✓</span></strong>
  `locations[].line1` | <strong><span style="color:red">x</span></strong>
  `locations[].line2` | <strong><span style="color:red">x</span></strong>
  `locations[].city` | <strong><span style="color:red">x</span></strong>
  `locations[].state` |<strong><span style="color:red">x</span></strong>
  `locations[].postal_code` | <strong><span style="color:red">x</span></strong>
  `locations[].country` | <strong><span style="color:red">x</span></strong>
  `accounts[].routing_number` | <strong><span style="color:red">x</span></strong>
  `accounts[].account_name` | <strong><span style="color:red">x</span></strong>
  `accounts[].institution_name` | <strong><span style="color:red">x</span></strong>
  `accounts[].account_type` | <strong><span style="color:red">x</span></strong>
  `accounts[].account_number` | <strong><span style="color:red">x</span></strong>

</details>

<details>
<summary><strong style="display:inline">Directory</strong></summary>

  Field | Support
  --- | ---
  `id` | <strong><span style="color:green">✓</span></strong>
  `first_name` | <strong><span style="color:green">✓</span></strong>
  `middle_name` | <strong><span style="color:green">✓</span></strong>
  `last_name` | <strong><span style="color:green">✓</span></strong>
  `manager.id` | <strong><span style="color:green">✓</span></strong>
  `department.name` | <strong><span style="color:green">✓</span></strong>
  `is_active` | <strong><span style="color:green">✓</span></strong>

</details>

<details>
<summary><strong style="display:inline">Individual</strong></summary>


  Field | Support
  --- | ---
  `id` | <strong><span style="color:green">✓</span></strong>
  `first_name` | <strong><span style="color:green">✓</span></strong>
  `middle_name` | <strong><span style="color:green">✓</span></strong>
  `last_name` | <strong><span style="color:green">✓</span></strong>
  `manager.id` | <strong><span style="color:green">✓</span></strong>
  `department.name` | <strong><span style="color:green">✓</span></strong>
  `is_active` | <strong><span style="color:green">✓</span></strong>

</details>

<details>
<summary><strong style="display:inline">Employment</strong></summary>


  Field | Support
  --- | ---
  `id` | <strong><span style="color:green">✓</span></strong>
  `first_name` | <strong><span style="color:green">✓</span></strong>
  `middle_name` | <strong><span style="color:green">✓</span></strong>
  `last_name` | <strong><span style="color:green">✓</span></strong>
  `manager.id` | <strong><span style="color:green">✓</span></strong>
  `department.name` | <strong><span style="color:green">✓</span></strong>
  `is_active` | <strong><span style="color:green">✓</span></strong>

</details>

<details>
<summary><strong style="display:inline">Payment</strong></summary>


  Field | Support
  --- | ---
  `id` | <strong><span style="color:green">✓</span></strong>
  `first_name` | <strong><span style="color:green">✓</span></strong>
  `middle_name` | <strong><span style="color:green">✓</span></strong>
  `last_name` | <strong><span style="color:green">✓</span></strong>
  `manager.id` | <strong><span style="color:green">✓</span></strong>
  `department.name` | <strong><span style="color:green">✓</span></strong>
  `is_active` | <strong><span style="color:green">✓</span></strong>

</details>

<details>
<summary><strong style="display:inline">Pay Statement</strong></summary>


  Field | Support
  --- | ---
  `id` | <strong><span style="color:green">✓</span></strong>
  `first_name` | <strong><span style="color:green">✓</span></strong>
  `middle_name` | <strong><span style="color:green">✓</span></strong>
  `last_name` | <strong><span style="color:green">✓</span></strong>
  `manager.id` | <strong><span style="color:green">✓</span></strong>
  `department.name` | <strong><span style="color:green">✓</span></strong>
  `is_active` | <strong><span style="color:green">✓</span></strong>

</details>

<!--
type: tab
title: API
-->
<details>
<summary><strong style="display:inline">Company</strong></summary>


  Field | Support
  ---- | -----
  `id` | <strong><span style="color:green">✓</span></strong>
  `legal_name` | <strong><span style="color:green">✓</span></strong>
  `entity.type` | <strong><span style="color:green">✓</span></strong>
  `entity.subtype` | <strong><span style="color:green">✓</span></strong>
  `primary_email` | <strong><span style="color:green">✓</span></strong>
  `primary_phone_number` | <strong><span style="color:green">✓</span></strong>
  `ein` | <strong><span style="color:green">✓</span></strong>
  `departments[]` | <strong><span style="color:green">✓</span></strong>
  `departments[].parent`| <strong><span style="color:green">✓</span></strong>
  `departments[].parent.name`| <strong><span style="color:green">✓</span></strong>
  `locations[].line1` | <strong><span style="color:red">x</span></strong>
  `locations[].line2` | <strong><span style="color:red">x</span></strong>
  `locations[].city` | <strong><span style="color:red">x</span></strong>
  `locations[].state` |<strong><span style="color:red">x</span></strong>
  `locations[].postal_code` | <strong><span style="color:red">x</span></strong>
  `locations[].country` | <strong><span style="color:red">x</span></strong>
  `accounts[].routing_number` | <strong><span style="color:red">x</span></strong>
  `accounts[].account_name` | <strong><span style="color:red">x</span></strong>
  `accounts[].institution_name` | <strong><span style="color:red">x</span></strong>
  `accounts[].account_type` | <strong><span style="color:red">x</span></strong>
  `accounts[].account_number` | <strong><span style="color:red">x</span></strong>

</details>

<details>
<summary><strong style="display:inline">Directory</strong></summary>

  Field | Support
  --- | ---
  `id` | <strong><span style="color:green">✓</span></strong>
  `first_name` | <strong><span style="color:green">✓</span></strong>
  `middle_name` | <strong><span style="color:green">✓</span></strong>
  `last_name` | <strong><span style="color:green">✓</span></strong>
  `manager.id` | <strong><span style="color:green">✓</span></strong>
  `department.name` | <strong><span style="color:green">✓</span></strong>
  `is_active` | <strong><span style="color:green">✓</span></strong>

</details>

<details>
<summary><strong style="display:inline">Individual</strong></summary>


  Field | Support
  --- | ---
  `id` | <strong><span style="color:green">✓</span></strong>
  `first_name` | <strong><span style="color:green">✓</span></strong>
  `middle_name` | <strong><span style="color:green">✓</span></strong>
  `last_name` | <strong><span style="color:green">✓</span></strong>
  `manager.id` | <strong><span style="color:green">✓</span></strong>
  `department.name` | <strong><span style="color:green">✓</span></strong>
  `is_active` | <strong><span style="color:green">✓</span></strong>

</details>

<details>
<summary><strong style="display:inline">Employment</strong></summary>


  Field | Support
  --- | ---
  `id` | <strong><span style="color:green">✓</span></strong>
  `first_name` | <strong><span style="color:green">✓</span></strong>
  `middle_name` | <strong><span style="color:green">✓</span></strong>
  `last_name` | <strong><span style="color:green">✓</span></strong>
  `manager.id` | <strong><span style="color:green">✓</span></strong>
  `department.name` | <strong><span style="color:green">✓</span></strong>
  `is_active` | <strong><span style="color:green">✓</span></strong>

</details>

<details>
<summary><strong style="display:inline">Payment</strong></summary>


  Field | Support
  --- | ---
  `id` | <strong><span style="color:green">✓</span></strong>
  `first_name` | <strong><span style="color:green">✓</span></strong>
  `middle_name` | <strong><span style="color:green">✓</span></strong>
  `last_name` | <strong><span style="color:green">✓</span></strong>
  `manager.id` | <strong><span style="color:green">✓</span></strong>
  `department.name` | <strong><span style="color:green">✓</span></strong>
  `is_active` | <strong><span style="color:green">✓</span></strong>

</details>

<details>
<summary><strong style="display:inline">Pay Statement</strong></summary>


  Field | Support
  --- | ---
  `id` | <strong><span style="color:green">✓</span></strong>
  `first_name` | <strong><span style="color:green">✓</span></strong>
  `middle_name` | <strong><span style="color:green">✓</span></strong>
  `last_name` | <strong><span style="color:green">✓</span></strong>
  `manager.id` | <strong><span style="color:green">✓</span></strong>
  `department.name` | <strong><span style="color:green">✓</span></strong>
  `is_active` | <strong><span style="color:green">✓</span></strong>

</details>

<!-- type: tab-end -->

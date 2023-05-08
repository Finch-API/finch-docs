---
stoplight-id: 0517ab806dda4
---

# Census & Pay Support

Finch's API tries to maintain parity between all [providers](./Providers.md). However, every now and then, a provider may not support a specific data field (for example: job titles). This section outlines the compatibility of each data field per Automated API Integration and any other miscellaneous information that's important to know.

<!-- theme: info -->

> <strong><span style="color:green">✓</span></strong> — supported
>
> <strong><span style="color:red">x</span></strong> — not supported by Finch

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

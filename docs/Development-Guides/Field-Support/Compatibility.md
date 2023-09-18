---
stoplight-id: 0517ab806dda4
---

# Organization & Pay Support

Finch's API tries to maintain parity between all [providers](./Providers.md). However, every now and then, a provider may not support a specific data field (for example: job titles). This section outlines the compatibility of each data field per Automated API Integration and any other miscellaneous information that's important to know.

## Supported Data Fields

---

<!-- theme: info -->

> <strong><span style="color:green">✓</span></strong> — supported
>
> <strong><span style="color:red">x</span></strong> — not supported by Finch


### Company
![company.png](../../../assets/images/company.png)

<p><i>¹ Only available by inferring from entity.type</i><br>
<i>² account_number is mask and only shows the last 4 digits</i></p>

### Directory
![directory.png](../../../assets/images/directory.png)

<p><i>¹ Initial only</i></p>

### Individual
![individual.png](../../../assets/images/individual.png)

<p><i>¹ Initial only</i><br>
<i>² No work email available</i><br>
<i>³ Contractors don't have these fields in the QBO system</i></p>
<i>⁴ This field is deprecated and may be inaccurate</i></p>

### Employment
![employment.png](../../../assets/images/employment.png)

<p><i>¹ Initial only</i><br>
<i>² Requires customer to be at highest package tier, ADP Run Pro</i></br>
<i>³ These fields are not provided for contractors</i></p>

### Payment
![payment.png](../../../assets/images/payment.png)

### Pay Statement
![pay-statement.png](../../../assets/images/pay-statement.png)

<p><i>¹ 401k Match cannot be set on Justworks</i><br>
<i>² Paychex Flex only exposes the previous 24 months of pay data</i></br>
<i>³Attribute not always available via Paylocity's API</i></p>


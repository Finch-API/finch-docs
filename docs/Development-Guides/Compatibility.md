# Compatibility

Finch's API tries to maintain parity between all [providers](./Providers.md). However, every now and then, a provider may not support a specific data field (for example, job titles). This section outlines the compatibility of each data field per automated API integration and any other miscellaneous information that's important to know.

## Supported Data Fields

---

<!-- theme: info -->

> `✓` — supported
>
> `x` — not supported by Finch

### Company
![company.png](https://stoplight.io/api/v1/projects/cHJqOjEzNjY0/images/RjDtFReJyT8)

<p><i>* Only available by inferring from entity.type</i></p>

### Directory
![directory.png](https://stoplight.io/api/v1/projects/cHJqOjEzNjY0/images/YjdADwFRuq4)

<p><i>* Initial only</i></p>

### Individual
![individual.png](https://stoplight.io/api/v1/projects/cHJqOjEzNjY0/images/BXNIpVrHn94)

<p><i>* Initial only</i><br>
<i>** No work email available</i></p>

### Employment
![employment.png](https://stoplight.io/api/v1/projects/cHJqOjEzNjY0/images/GZNFvPjlWaQ)

<p><i>* Initial only</i><br>
<i>** Requires customer to be at highest package tier, ADP Run Pro</i></p>

### Payment
![payment.png](https://stoplight.io/api/v1/projects/cHJqOjEzNjY0/images/wFQ1bMyYjXo)


### Pay Statement
![pay_statement.png](https://stoplight.io/api/v1/projects/cHJqOjEzNjY0/images/iPpR2Txxizk)

<p><i>* 401k Match cannot be set on Justworks</i></p>

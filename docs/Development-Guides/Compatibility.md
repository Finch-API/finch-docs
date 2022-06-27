# Compatibility

Finch's API tries to maintain parity between all [providers](./Providers.md). However, every now and then, a provider may not support a specific data field (for example: job titles). This section outlines the compatibility of each data field per Automated API Integration and any other miscellaneous information that's important to know.

## Supported Data Fields

---

<!-- theme: info -->

> `✓` — supported
>
> `x` — not supported by Finch

### Company
![company.png](https://stoplight.io/api/v1/projects/cHJqOjEzNjY0/images/gIigZuAm88Q)

<p><i>* Only available by inferring from entity.type</i><br>
<i>** account_number is mask and only shows the last 4 digits</i></p>

### Directory
![directory.png](https://stoplight.io/api/v1/projects/cHJqOjEzNjY0/images/8UmwmvLO39M)

<p><i>* Initial only</i></p>

### Individual
![individual.png](https://stoplight.io/api/v1/projects/cHJqOjEzNjY0/images/gCkS7hisB7I)

<p><i>* Initial only</i><br>
<i>** No work email available</i></p>

### Employment
![employment.png](https://stoplight.io/api/v1/projects/cHJqOjEzNjY0/images/eOqHa68QWqA)

<p><i>* Initial only</i><br>
<i>** Requires customer to be at highest package tier, ADP Run Pro</i></p>

### Payment
![payment.png](https://stoplight.io/api/v1/projects/cHJqOjEzNjY0/images/wFQ1bMyYjXo)


### Pay Statement
![pay_statement.png](https://stoplight.io/api/v1/projects/cHJqOjEzNjY0/images/iPpR2Txxizk)

<p><i>* 401k Match cannot be set on Justworks</i></p>

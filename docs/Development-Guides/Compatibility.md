# Compatibility

Finch's API tries to maintain parity between all [providers](https://developer.tryfinch.com/docs/reference/ZG9jOjMyMDI2ODc0-providers). However, every now and then, a provider may not support a specific data field (for example, job titles). This section outlines the compatibility of each data field per automated API integration and any other miscellaneous information that's important to know.

## Supported Data Fields

---

<!-- theme: info -->

> `✓` — supported
>
> `x` — not supported by Finch

### Company
![company.png](https://stoplight.io/api/v1/projects/cHJqOjEzNjY0/images/LqDftcBnyrQ)

<p><i>* Only available by inferring from entity.type</i></p>

### Directory
![directory (1).png](https://stoplight.io/api/v1/projects/cHJqOjEzNjY0/images/iTCT034lpJU)

<p><i>* Initial only</i></p>

### Individual
![individual.png](https://stoplight.io/api/v1/projects/cHJqOjEzNjY0/images/IoaQOFoI6ik)

<p><i>* Initial only</i><br>
<i>** No work email available</i></p>

### Employment
![employment (1).png](https://stoplight.io/api/v1/projects/cHJqOjEzNjY0/images/CrW9OB4J65w)

<p><i>* Initial only</i><br>
<i>** Requires customer to be at highest package tier, ADP Run Pro</i></p>

### Payment

![payment.png](https://stoplight.io/api/v1/projects/cHJqOjEzNjY0/images/3S2mtrjLWdk)


### Pay Statement
![pay_statement.png](https://stoplight.io/api/v1/projects/cHJqOjEzNjY0/images/x7IYWYp8dQQ)

<p><i>* 401k Match cannot be set on Justworks</i></p>

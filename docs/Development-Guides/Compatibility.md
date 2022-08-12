# Compatibility

Finch's API tries to maintain parity between all [providers](./Providers.md). However, every now and then, a provider may not support a specific data field (for example: job titles). This section outlines the compatibility of each data field per Automated API Integration and any other miscellaneous information that's important to know.

## Supported Data Fields

---

<!-- theme: info -->

> `✓` — supported
>
> `x` — not supported by Finch

### Company
![Finch Compatibility - Company.png](https://stoplight.io/api/v1/projects/cHJqOjEzNjY0/images/AEtHZ61QXIA)


<p><i>* Only available by inferring from entity.type</i><br>
<i>** account_number is mask and only shows the last 4 digits</i></p>

### Directory
![Finch Compatibility - Directory.png](https://stoplight.io/api/v1/projects/cHJqOjEzNjY0/images/0hkrtIgzNJI)


<p><i>* Initial only</i></p>

### Individual
![Finch Compatibility - Individual.png](https://stoplight.io/api/v1/projects/cHJqOjEzNjY0/images/ONSlzNA7C9g)


<p><i>* Initial only</i><br>
<i>** No work email available</i></p>

### Employment
![Finch Compatibility - Employment.png](https://stoplight.io/api/v1/projects/cHJqOjEzNjY0/images/aGyLfMrl7SY)


<p><i>* Initial only</i><br>
<i>** Requires customer to be at highest package tier, ADP Run Pro</i></p>

### Payment
![Finch Compatibility - Payment.png](https://stoplight.io/api/v1/projects/cHJqOjEzNjY0/images/KeoczDkPZ2A)


### Pay Statement
![Finch Compatibility - Pay Statement.png](https://stoplight.io/api/v1/projects/cHJqOjEzNjY0/images/uvYJWn0hoZM)


<p><i>* 401k Match cannot be set on Justworks</i></p>
<p><i>** Paychex Flex only exposes the previous 24 months of pay data</i></p>

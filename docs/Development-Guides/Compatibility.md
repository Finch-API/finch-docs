# Compatibility

Finch's API tries to maintain parity between all [providers](./Providers.md). However, every now and then, a provider may not support a specific data field (for example: job titles). This section outlines the compatibility of each data field per Automated API Integration and any other miscellaneous information that's important to know.

## Supported Data Fields

---

<!-- theme: info -->

> `✓` — supported
>
> `x` — not supported by Finch

### Company
![Finch Compatibility - Company.jpg](https://stoplight.io/api/v1/projects/cHJqOjEzNjY0/images/rGKp0LCE23w)


<p><i>* Only available by inferring from entity.type</i><br>
<i>** account_number is mask and only shows the last 4 digits</i></p>

### Directory
![Finch Compatibility - Directory.jpg](https://stoplight.io/api/v1/projects/cHJqOjEzNjY0/images/I2Dc4OA111I)


<p><i>* Initial only</i></p>

### Individual
![Finch Compatibility - Individual.jpg](https://stoplight.io/api/v1/projects/cHJqOjEzNjY0/images/qRUMf3tA2SU)


<p><i>* Initial only</i><br>
<i>** No work email available</i></p>

### Employment

![Finch Compatibility - Employment.png](https://stoplight.io/api/v1/projects/cHJqOjEzNjY0/images/RFMk7Z9saHc)



<p><i>* Initial only</i><br>
<i>** Requires customer to be at highest package tier, ADP Run Pro</i></br>
<i>*** These fields are not provided for contractors</i></p>

### Payment
![Finch Compatibility - Payment.jpg](https://stoplight.io/api/v1/projects/cHJqOjEzNjY0/images/eUIR1IR9U5k)


### Pay Statement
![Finch Compatibility - Pay Statement.jpg](https://stoplight.io/api/v1/projects/cHJqOjEzNjY0/images/jSQ6no1e22M)


<p><i>* 401k Match cannot be set on Justworks</i>
<p><i>** Paychex Flex only exposes the previous 24 months of pay data</i></p>

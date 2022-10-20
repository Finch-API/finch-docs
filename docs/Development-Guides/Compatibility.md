# Compatibility

Finch's API tries to maintain parity between all [providers](./Providers.md). However, every now and then, a provider may not support a specific data field (for example: job titles). This section outlines the compatibility of each data field per Automated API Integration and any other miscellaneous information that's important to know.

## Supported Data Fields

---

<!-- theme: info -->

> `✓` — supported
>
> `x` — not supported by Finch

<!--
type: tab
title: HRIS
-->


### Company
![company.png](https://stoplight.io/api/v1/projects/cHJqOjEzNjY0/images/KJn3cQAW5mw)


<p><i>* Only available by inferring from entity.type</i><br>
<i>** account_number is mask and only shows the last 4 digits</i></p>

### Directory
![directory.png](https://stoplight.io/api/v1/projects/cHJqOjEzNjY0/images/Nfdo8FPyDCE)


<p><i>* Initial only</i></p>

### Individual
![individual.png](https://stoplight.io/api/v1/projects/cHJqOjEzNjY0/images/y2Sg2796qJE)


<p><i>* Initial only</i><br>
<i>** No work email available</i></p>

### Employment
![employment.png](https://stoplight.io/api/v1/projects/cHJqOjEzNjY0/images/eF5QpbJau34)


<p><i>* Initial only</i><br>
<i>** Requires customer to be at highest package tier, ADP Run Pro</i></br>
<i>*** These fields are not provided for contractors</i></p>

### Payment
![payment.png](https://stoplight.io/api/v1/projects/cHJqOjEzNjY0/images/aIOil0UBh3A)


### Pay Statement
![pay-statement.png](https://stoplight.io/api/v1/projects/cHJqOjEzNjY0/images/cPQrrgoojtc)


<p><i>* 401k Match cannot be set on Justworks</i>
<p><i>** Paychex Flex only exposes the previous 24 months of pay data</i></p>

<!--
type: tab
title: ATS
-->

### Candidates
![candidate.png](https://stoplight.io/api/v1/projects/cHJqOjEzNjY0/images/xHpEvqi6KAQ)
*opportunity leads are excluded from Candidates for Lever

### Applications
![application.png](https://stoplight.io/api/v1/projects/cHJqOjEzNjY0/images/B2kFm0MqXtQ)

### Jobs
![job.png](https://stoplight.io/api/v1/projects/cHJqOjEzNjY0/images/lqrWiljFmOc)

### Stages
![stage.png](https://stoplight.io/api/v1/projects/cHJqOjEzNjY0/images/fcqmlGCgTcQ)


### Offers
![offers.png](https://stoplight.io/api/v1/projects/cHJqOjEzNjY0/images/h1l2OxWUQPg)



<!-- type: tab-end -->

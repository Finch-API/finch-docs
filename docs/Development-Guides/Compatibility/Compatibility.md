---
stoplight-id: 0517ab806dda4
---

# Field Support Overview

Finch's API attempts to maintain field support parity between all [providers](./Providers.md). However, at times a provider may not support a specific data field (for example: job titles) or Finch may not yet have built support for a particular field. The pages in this section outline the compatibility of each data field for each automated API integration and any other miscellaneous information that's important to know.

### Gusto

---

<!-- theme: info -->

> <strong><span style="color:green">✓</span></strong> — supported
>
> <strong><span style="color:red">x</span></strong> — not supported by Finch

<!--
type: tab
title: HRIS
-->

### Company
![company.jpg](../../../assets/images/company.jpg)

<p><i>* Only available by inferring from entity.type</i><br>
<i>** account_number is mask and only shows the last 4 digits</i></p>

### Directory
![directory.png](../../../assets/images/directory.png)

<p><i>* Initial only</i></p>

### Individual
![individual.png](../../../assets/images/individual.png)

<p><i>* Initial only</i><br>
<i>** No work email available</i></p>

### Employment
![employment.png](../../../assets/images/employment-2.png)


<p><i>* Initial only</i><br>
<i>** Requires customer to be at highest package tier, ADP Run Pro</i></br>
<i>*** These fields are not provided for contractors</i></p>

### Payment
![payment.jpg](../../../assets/images/payment.jpg)

### Pay Statement
![pay-statement.jpg](../../../assets/images/pay-statement.jpg)

<p><i>* 401k Match cannot be set on Justworks</i><br>
<i>** Paychex Flex only exposes the previous 24 months of pay data</i></br>
<i>***Attribute not always available via Paylocity's API</i></p>

<!--
type: tab
title: ATS
-->



<!-- type: tab-end -->

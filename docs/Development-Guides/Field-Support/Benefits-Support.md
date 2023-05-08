# Benefits Field Support

Finch's Benefits endpoints provide a unified API that enables users to both read and write benefits information. The tables below outline the features of the Benefits API that are supported for providers, along with any notable information. 

**Note: One-time post-tax deductions are not currently supported for benefits.**

><strong><span style="color:green">✓</span></strong> - supported
>
><strong><span style="color:red">x</span></strong> - not supported by Finch
>
>`n/a` - not supported by provider
>
>`*` - the client must create the benefit


### ADP Run

<!--
type: tab
title: Supported Operations
-->

Benefit | Read Company Benefits | Create Company Benefits | Read Individual Benefits | Enroll/Unenroll Individual Benefits
--------|----------|---------|------------|------------
**401(k)** | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |
**Roth 401(k)** | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |
**401(k) Loan** | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |
**403(b)** | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |
**Roth 403(b)** | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |
**457** | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |
**Roth 457**  | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |
**Simple IRA** | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |
**HSA (post-tax)** | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |
**HSA (pre-tax)** | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |
**FSA Dependent** | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |
**FSA Medical** | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |
**Section 125 Dental** | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |
**Section 125 Medical** | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |
**Section 125 Vision** | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |
**Commuter (pre-tax)** | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |
**Custom pre-tax** | n/a | n/a | n/a | n/a |
**Custom post-tax** | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |

<!--
type: tab
title: Supported Features
-->

Benefit | Features
--------|----------
**401(k)** | `company_contribution`: `percent`<br>`employee_deduction`: `fixed`, `percent`<br>`catch_up`
**Roth 401(k)** | `company_contribution`: `percent`<br>`employee_deduction`: `fixed`, `percent`<br>`catch_up`
**401(k) Loan** | `employee_deduction`: `fixed`
**403(b)** | `company_contribution`: `percent`<br>`employee_deduction`: `fixed`, `percent`
**Roth 403(b)**| `company_contribution`: `percent`<br>`employee_deduction`: `fixed`, `percent`
**457**| `employee_deduction`: `fixed`, `percent`<br>`catch_up`
**Roth 457** | `employee_deduction`: `fixed`, `percent`<br>`catch_up`
**Simple IRA**| `company_contribution`: `fixed`, `percent`<br>`employee_deduction`: `fixed`, `percent`<br>`catch_up`
**HSA (pre-tax)**| `employee_deduction`: `fixed`, `percent`<br>`hsa_contribution_limit`: `individual`, `family`
**HSA (post-tax)**| `company_contribution`: `fixed`, `percent`<br>`employee_deduction`: `fixed`, `percent`<br>`hsa_contribution_limit`: `individual`, `family`
**FSA Dependent** | `employee_deduction`: `fixed`
**FSA Medical** | `employee_deduction`: `fixed`
**Section 125 Dental** | `employee_deduction`: `fixed`
**Section 125 Medical**| `employee_deduction`: `fixed`
**Section 125 Vision** | `employee_deduction`: `fixed`
**Commuter (pre-tax)** | `employee_deduction`: `fixed`
**Custom post-tax** | `employee_deduction`: `fixed`, `percent`

<!-- type: tab-end -->

### ADP Workforce Now

<!--
type: tab
title: Supported Operations
-->

Benefit | Read Company Benefits | Create Company Benefits | Read Individual Benefits | Enroll/Unenroll Individual Benefits
--------|----------|---------|------------|------------
**401(k)** | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |
**Roth 401(k)** | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |
**401(k) Loan** | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |
**403(b)** | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |
**Roth 403(b)** | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |
**457** | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |
**Roth 457**  | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |
**Simple IRA** | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |
**HSA (post-tax)** | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |
**HSA (pre-tax)** | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |
**FSA Dependent** | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |
**FSA Medical** | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |
**Section 125 Dental** | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |
**Section 125 Medical** | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |
**Section 125 Vision** | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |
**Commuter (pre-tax)** | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |
**Custom pre-tax** | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |
**Custom post-tax** | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |

<!--
type: tab
title: Supported Features
-->

Benefit | Features
--------|----------
**401(k)** | `employee_deduction`: `fixed`, `percent`<br>`catch_up`<br>`annual_max`
**Roth 401(k)** | `employee_deduction`: `fixed`, `percent`<br>`catch_up`<br>`annual_max`
**401(k) Loan** | `employee_deduction`: `fixed`, `percent`<br>
**403(b)** | `employee_deduction`: `fixed`, `percent`<br>`catch_up`<br>`annual_max`
**Roth 403(b)**| `employee_deduction`: `fixed`, `percent`
**457**| `employee_deduction`: `fixed`, `percent`<br>`catch_up`<br>`annual_max`
**Roth 457** | `employee_deduction`: `fixed`, `percent`<br>`catch_up`<br>`annual_max`
**Simple IRA**| `employee_deduction`: `fixed`, `percent`<br>`catch_up`<br>`annual_max`
**HSA (pre-tax)**| `employee_deduction`: `fixed`, `percent`<br>`hsa_contribution_limit`: `individual`, `family`
**HSA (post-tax)**| `employee_deduction`: `fixed`, `percent`<br>`hsa_contribution_limit`: `individual`, `family`
**FSA Dependent** | `employee_deduction`: `fixed`, `percent`
**FSA Medical** | `employee_deduction`: `fixed`, `percent`
**Section 125 Dental** | `employee_deduction`: `fixed`, `percent`
**Section 125 Medical**| `employee_deduction`: `fixed`, `percent`
**Section 125 Vision** | `employee_deduction`: `fixed`, `percent`
**Commuter (pre-tax)** | `employee_deduction`: `fixed`, `percent`
**Custom pre-tax** | `employee_deduction`: `fixed`, `percent`
**Custom post-tax** | `employee_deduction`: `fixed`, `percent`

<!-- type: tab-end -->

### BambooHR

<!--
type: tab
title: Supported Operations
-->

Benefit | Read Company Benefits | Create Company Benefits | Read Individual Benefits | Enroll/Unenroll Individual Benefits
--------|----------|---------|------------|------------
**401(k)** | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |
**Roth 401(k)** | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |
**401(k) Loan** | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |
**403(b)** | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |
**Roth 403(b)** | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |
**457** | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |
**Roth 457**  | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |
**Simple IRA** | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |
**HSA (post-tax)** | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |
**HSA (pre-tax)** | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |
**FSA Dependent** | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |
**FSA Medical** | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |
**Section 125 Dental** | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |
**Section 125 Medical** | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |
**Section 125 Vision** | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |
**Commuter (pre-tax)** | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |
**Custom pre-tax** | n/a | n/a | n/a | n/a |
**Custom post-tax** | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |

<!--
type: tab
title: Supported Features
-->

Benefit | Features
--------|----------
**401(k)** | `company_contribution`: `fixed`, `percent`<br>`employee_deduction`: `fixed`, `percent`
**Roth 401(k)** | `company_contribution`: `fixed`, `percent`<br>`employee_deduction`: `fixed`, `percent`
**401(k) Loan** | `company_contribution`: `fixed`, `percent`<br>`employee_deduction`: `fixed`, `percent`
**403(b)** | `company_contribution`: `fixed`, `percent`<br>`employee_deduction`: `fixed`, `percent`
**Roth 403(b)**| `company_contribution`: `fixed`, `percent`<br>`employee_deduction`: `fixed`, `percent`
**457**| `company_contribution`: `fixed`, `percent`<br>`employee_deduction`: `fixed`, `percent`
**Roth 457** | `company_contribution`: `fixed`, `percent`<br>`employee_deduction`: `fixed`, `percent`
**Simple IRA**| `company_contribution`: `fixed`, `percent`<br>`employee_deduction`: `fixed`, `percent`
**HSA (pre-tax)**| `employee_deduction`: `fixed`, `percent`<br>`hsa_contribution_limit`: `individual`, `family`
**HSA (post-tax)**| `company_contribution`: `fixed`, `percent`<br>`employee_deduction`: `fixed`, `percent`
**FSA Dependent** | `employee_deduction`: `fixed`
**FSA Medical** | `company_contribution`: `fixed`, `percent`<br>`employee_deduction`: `fixed`, `percent`
**Section 125 Dental** | `company_contribution`: `fixed`, `percent`<br>`employee_deduction`: `fixed`, `percent`
**Section 125 Medical**| `company_contribution`: `fixed`, `percent`<br>`employee_deduction`: `fixed`, `percent`
**Section 125 Vision** | `company_contribution`: `fixed`, `percent`<br>`employee_deduction`: `fixed`, `percent`
**Commuter (pre-tax)** | `company_contribution`: `fixed`, `percent`<br>`employee_deduction`: `fixed`, `percent`
**Custom post-tax** | `company_contribution`: `fixed`, `percent`<br>`employee_deduction`: `fixed`, `percent`

<!-- type: tab-end -->

### ConnectPay

<!--
type: tab
title: Supported Operations
-->

Benefit | Read Company Benefits | Create Company Benefits | Read Individual Benefits | Enroll/Unenroll Individual Benefits
--------|----------|---------|------------|------------
**401(k)** | <strong><span style="color:red">x</span></strong> | * | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |
**Roth 401(k)** | <strong><span style="color:red">x</span></strong> | * | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |

<!--
type: tab
title: Supported Features
-->

Benefit | Features
--------|----------
**401(k)** | `company_contribution`: `percent`<br>`employee_deduction`: `fixed`, `percent`<br>`catch_up`<br>`annual_maximum`
**Roth 401(k)** | `employee_deduction`: `fixed`, `percent`<br>`catch_up`<br>`annual_maximum`

<!-- type: tab-end -->

### Gusto

<!--
type: tab
title: Supported Operations
-->

Benefit | Read Company Benefits | Create Company Benefits | Read Individual Benefits | Enroll/Unenroll Individual Benefits
--------|----------|---------|------------|------------
**401(k)** | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:green">✓</span></strong> |
**Roth 401(k)** | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:green">✓</span></strong> |
**403(b)** | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:green">✓</span></strong> |
**Roth 403(b)** | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:green">✓</span></strong> |
**457** | n/a | n/a | n/a | n/a |
**Roth 457**  | n/a | n/a | n/a | n/a |
**Simple IRA** | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:green">✓</span></strong> |
**HSA (post-tax)** | n/a | n/a | n/a | n/a |
**HSA (pre-tax)** | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:green">✓</span></strong> |
**FSA Dependent** | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:green">✓</span></strong> |
**FSA Medical** | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:green">✓</span></strong> |
**Section 125 Dental** | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:green">✓</span></strong> |
**Section 125 Medical** | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:green">✓</span></strong> |
**Section 125 Vision** | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:green">✓</span></strong> |
**Commuter (pre-tax)** | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:green">✓</span></strong> |
**Custom pre-tax** | n/a | n/a | n/a | n/a |
**Custom post-tax** | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:green">✓</span></strong> |

<!--
type: tab
title: Supported Features
-->

Benefit | Features
--------|----------
**401(k)** | `company_contribution`: `fixed`, `percent`<br>`employee_deduction`: `fixed`, `percent`<br>`catch_up`<br>`annual_maximum`
**Roth 401(k)** | `company_contribution`: `fixed`, `percent`<br>`employee_deduction`: `fixed`, `percent`<br>`catch_up`<br>`annual_maximum`
**403(b)** | `company_contribution`: `fixed`, `percent`<br>`employee_deduction`: `fixed`, `percent`<br>`catch_up`<br>`annual_maximum`
**Roth 403(b)**| `company_contribution`: `fixed`, `percent`<br>`employee_deduction`: `fixed`, `percent`<br>`catch_up`<br>`annual_maximum`
**457**| `company_contribution`: `fixed`, `percent`<br>`employee_deduction`: `fixed`, `percent`<br>`catch_up`<br>`annual_maximum`
**Roth 457** | `company_contribution`: `fixed`, `percent`<br>`employee_deduction`: `fixed`, `percent`<br>`catch_up`<br>`annual_maximum`
**Simple IRA**| `company_contribution`: `fixed`, `percent`<br>`employee_deduction`: `fixed`, `percent`<br>`catch_up`<br>`annual_maximum`
**HSA (pre-tax)**| `company_contribution`: `fixed`, `percent`<br>`employee_deduction`: `fixed`, `percent`<br>`catch_up`<br>`annual_maximum`<br>`hsa_contribution_limit`: `individual`, `family`
**FSA Dependent** | `company_contribution`: `fixed`<br>`employee_deduction`: `fixed`
**FSA Medical** | `company_contribution`: `fixed`<br>`employee_deduction`: `fixed`
**Section 125 Dental** | `company_contribution`: `fixed`<br>`employee_deduction`: `fixed`
**Section 125 Medical**| `company_contribution`: `fixed`<br>`employee_deduction`: `fixed`
**Section 125 Vision** | `company_contribution`: `fixed`<br>`employee_deduction`: `fixed`
**Commuter (pre-tax)** | `company_contribution`: `fixed` <br>`employee_deduction`: `fixed`
**Custom post-tax** | `employee_deduction`: `fixed`, `percent`<br>`annual_maximum`


<!-- type: tab-end -->

### Justworks

<!--
type: tab
title: Supported Operations
-->

Benefit | Read Company Benefits | Create Company Benefits | Read Individual Benefits | Enroll/Unenroll Individual Benefits
--------|----------|---------|------------|------------
**401(k)** | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |
**Roth 401(k)** | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |
**401(k) Loan** | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |
**403(b)** | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |
**Roth 403(b)** | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |
**457** | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |
**Roth 457**  | n/a | n/a | n/a | n/a |
**Simple IRA** | n/a | n/a | n/a | n/a |
**HSA (post-tax)** | n/a | n/a | n/a | n/a |
**HSA (pre-tax)** | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |
**FSA Dependent** | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |
**FSA Medical** | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |
**Section 125 Dental** | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |
**Section 125 Medical** | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |
**Section 125 Vision** | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |
**Commuter (pre-tax)** | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |
**Custom pre-tax** | n/a | n/a | n/a | n/a |
**Custom post-tax** | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |

<!--
type: tab
title: Supported Features
-->

Benefit | Features
--------|----------
**401(k)** | `employee_deduction`: `fixed`, `percent`<br>
**Roth 401(k)** | `employee_deduction`: `fixed`, `percent`<br>
**401(k) Loan** | `employee_deduction`: `fixed`, `percent`<br>
**403(b)** | `employee_deduction`: `fixed`, `percent`<br>
**Roth 403(b)**| `employee_deduction`: `fixed`, `percent`<br>
**457** | `employee_deduction`: `fixed`, `percent`<br>
**Section 125 Dental** | `employee_deduction`: `fixed` <br>
**Section 125 Medical**| `employee_deduction`: `fixed` <br>
**Section 125 Vision** | `employee_deduction`: `fixed` <br>
**HSA (pre-tax)**| `employee_deduction`: `fixed` <br>
**FSA Dependent** | `employee_deduction`: `fixed` <br>
**FSA Medical** | `employee_deduction`: `fixed` <br>
**Commuter** | `employee_deduction`: `fixed` <br>
**Custom post-tax** | `employee_deduction`: `fixed` <br>

<!-- type: tab-end -->

### Patriot

<!--
type: tab
title: Supported Operations
-->

Benefit | Read Company Benefits | Create Company Benefits | Read Individual Benefits | Enroll/Unenroll Individual Benefits
--------|----------|---------|------------|------------
**401(k)** | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |
**Roth 401(k)** | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |
**401(k) Loan** | n/a | n/a | n/a | n/a |
**403(b)** | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |
**Roth 403(b)** | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |
**457** | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |
**Roth 457**  | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |
**Simple IRA** | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |
**HSA (post-tax)** | n/a | n/a | n/a | n/a |
**HSA (pre-tax)** | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |
**FSA Dependent** | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |
**FSA Medical** | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |
**Section 125 Dental** | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |
**Section 125 Medical** | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |
**Section 125 Vision** | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |
**Commuter (pre-tax)** | n/a | n/a | n/a | n/a |
**Custom pre-tax** | n/a | n/a | n/a | n/a |
**Custom post-tax** | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |

<!--
type: tab
title: Supported Features
-->

Benefit | Features
--------|----------
**401(k)** | `company_contribution`: `fixed`, `percent`<br>`employee_deduction`: `fixed`, `percent`<br>`annual_maximum`
**Roth 401(k)** | `company_contribution`: `fixed`, `percent`<br>`employee_deduction`: `fixed`, `percent`<br>`annual_maximum`
**403(b)** | `employee_deduction`: `fixed`, `percent`<br>`annual_maximum`
**Roth 403(b)**| `employee_deduction`: `fixed`, `percent`<br>`annual_maximum`
**457** | `employee_deduction`: `fixed`, `percent`<br>`annual_maximum`
**Roth  457** | `employee_deduction`: `fixed`, `percent`<br>`annual_maximum`
**Section 125 Dental** | `employee_deduction`: `fixed`, `percent`<br>`annual_maximum`
**Section 125 Medical**| `company_contribution`: `fixed`, `percent`<br>`employee_deduction`: `fixed`, `percent`<br>`annual_maximum`
**Section 125 Vision** | `employee_deduction`: `fixed`, `percent`<br>`annual_maximum`
**HSA (pre-tax)**| `company_contribution`: `fixed`, `percent`<br>`employee_deduction`: `fixed`, `percent`<br>`annual_maximum`<br>`hsa_contribution_limit`: `individual`, `family`
**FSA Medical** | `employee_deduction`: `fixed`, `percent`<br>`annual_maximum`
**FSA Dependent Care** | `employee_deduction`: `fixed`, `percent`<br>`annual_maximum`
**Simple IRA** | `employee_deduction`: `fixed`, `percent`<br>`annual_maximum`
**Custom post-tax** | `employee_deduction`: `fixed`, `percent`

<!-- type: tab-end -->

### Paychex

<!--
type: tab
title: Supported Operations
-->

Benefit | Read Company Benefits | Create Company Benefits | Read Individual Benefits | Enroll/Unenroll Individual Benefits
--------|----------|---------|------------|------------
**401(k)** | <strong><span style="color:red">x</span></strong> | * | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |
**Roth 401(k)** | <strong><span style="color:red">x</span></strong> | * | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |
**401(k) Loan** | <strong><span style="color:red">x</span></strong> | * | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |
**403(b)** | <strong><span style="color:red">x</span></strong> | * | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |
**Roth 403(b)** | <strong><span style="color:red">x</span></strong> | * | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |
**457** | <strong><span style="color:red">x</span></strong> | * | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |
**Roth 457**  | <strong><span style="color:red">x</span></strong> | * | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |
**Simple IRA** | <strong><span style="color:red">x</span></strong> | * | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |
**HSA (post-tax)** | <strong><span style="color:red">x</span></strong> | * | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |
**HSA (pre-tax)** | <strong><span style="color:red">x</span></strong> | * | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |
**FSA Dependent** | <strong><span style="color:red">x</span></strong> | * | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |
**FSA Medical** | <strong><span style="color:red">x</span></strong> | * | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |
**Section 125 Dental** | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |
**Section 125 Medical** | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |
**Section 125 Vision** | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |
**Commuter (pre-tax)** | <strong><span style="color:red">x</span></strong> | * | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |
**Custom pre-tax** | <strong><span style="color:red">x</span></strong> | * | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |
**Custom post-tax** | <strong><span style="color:red">x</span></strong> | * | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |

<!--
type: tab
title: Supported Features
-->

Benefit | Features
--------|----------
**Section 125 Dental** | `employee_deduction`: `fixed`, `percent` <br>
**Section 125 Medical**| `employee_deduction`: `fixed`, `percent` <br>
**Section 125 Vision** | `employee_deduction`: `fixed`, `percent` <br>

<!-- type: tab-end -->

### Paycom

<!--
type: tab
title: Supported Operations
-->

Benefit | Read Company Benefits | Create Company Benefits | Read Individual Benefits | Enroll/Unenroll Individual Benefits
--------|----------|---------|------------|------------
**401(k)** | <strong><span style="color:red">x</span></strong> | * | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |
**Roth 401(k)** | <strong><span style="color:red">x</span></strong> | * | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |
**401(k) Loan** | <strong><span style="color:red">x</span></strong> | * | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |
**403(b)** | <strong><span style="color:red">x</span></strong> | * | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |
**Roth 403(b)** | <strong><span style="color:red">x</span></strong> | * | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |
**457** | <strong><span style="color:red">x</span></strong> | * | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |
**Roth 457**  | <strong><span style="color:red">x</span></strong> | * | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |
**Simple IRA** | <strong><span style="color:red">x</span></strong> | * | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |
**HSA (post-tax)** | <strong><span style="color:red">x</span></strong> | * | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |
**HSA (pre-tax)** | <strong><span style="color:red">x</span></strong> | * | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |
**FSA Dependent** | <strong><span style="color:red">x</span></strong> | * | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |
**FSA Medical** | <strong><span style="color:red">x</span></strong> | * | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |
**Section 125 Dental** | <strong><span style="color:red">x</span></strong> | * | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |
**Section 125 Medical** | <strong><span style="color:red">x</span></strong> | * | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |
**Section 125 Vision** | <strong><span style="color:red">x</span></strong> | * | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |
**Commuter (pre-tax)** | <strong><span style="color:red">x</span></strong> | * | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |
**Custom pre-tax** | <strong><span style="color:red">x</span></strong> | * | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |
**Custom post-tax** | <strong><span style="color:red">x</span></strong> | * | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |

<!--
type: tab
title: Supported Features
-->

Benefit | Features
--------|----------
**401(k)** | `company_contribution`: `fixed`, `percent`<br>`employee_deduction`: `fixed`, `percent`
**Roth 401(k)** | `company_contribution`: `fixed`, `percent`<br>`employee_deduction`: `fixed`, `percent`
**401(k) Loan** | 
**403(b)** | 
**Roth 403(b)**| 
**457** | 
**Roth  457** | 
**Section 125 Dental** | `employee_deduction`: `fixed`
**Section 125 Medical**| `employee_deduction`: `fixed`
**Section 125 Vision** | `employee_deduction`: `fixed`
**HSA (pre-tax)**| 
**HSA (post-tax)**| 
**FSA Dependent Care** | `employee_deduction`: `fixed`
**FSA Medical** | `employee_deduction`: `fixed`
**Simple IRA** | `employee_deduction`: `fixed`, `percent`
**Commuter** | `employee_deduction`: `fixed`
**Custom pre-tax** | 
**Custom post-tax** | `employee_deduction`: `fixed`

<!-- type: tab-end -->

### Paycor

<!--
type: tab
title: Supported Operations
-->

Benefit | Read Company Benefits | Create Company Benefits | Read Individual Benefits | Enroll/Unenroll Individual Benefits
--------|----------|---------|------------|------------
**401(k)** | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |
**Roth 401(k)** | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |
**401(k) Loan** | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |
**403(b)** | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |
**Roth 403(b)** | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |
**457** | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |
**Roth 457**  | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |
**Simple IRA** | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |
**HSA (post-tax)** | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |
**HSA (pre-tax)** | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |
**FSA Dependent** | n/a | n/a | n/a | n/a |
**FSA Medical** | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |
**Section 125 Dental** | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |
**Section 125 Medical** | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |
**Section 125 Vision** | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |
**Commuter (pre-tax)** | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |
**Custom pre-tax** | n/a | n/a | n/a | n/a |
**Custom post-tax** | n/a | n/a | n/a | n/a |

<!--
type: tab
title: Supported Features
-->

Benefit | Features
--------|----------
**401(k)** | `company_contribution`: `fixed`, `percent`<br>`employee_deduction`: `fixed`, `percent`<br>`catch_up`<br>`annual_maximum`
**Roth 401(k)** | `company_contribution`: `fixed`, `percent`<br>`employee_deduction`: `fixed`, `percent`<br>`catch_up`<br>`annual_maximum`
**401(k) Loan** | `company_contribution`: `fixed`, `percent`<br>`employee_deduction`: `fixed`, `percent`<br>
**403(b)** | `company_contribution`: `fixed`, `percent`<br>`employee_deduction`: `fixed`, `percent`<br>`catch_up`<br>`annual_maximum`
**Roth 403(b)**| `company_contribution`: `fixed`, `percent`<br>`employee_deduction`: `fixed`, `percent`<br>`catch_up`<br>`annual_maximum`
**457** | `company_contribution`: `fixed`, `percent`<br>`employee_deduction`: `fixed`, `percent`<br>`catch_up`<br>`annual_maximum`
**Roth  457** | `company_contribution`: `fixed`, `percent`<br>`employee_deduction`: `fixed`, `percent`<br>`catch_up`<br>`annual_maximum`
**Section 125 Dental** | `employee_deduction`: `fixed`, `percent`<br>
**Section 125 Medical**| `company_contribution`: `fixed`, `percent`<br>`employee_deduction`: `fixed`, `percent`<br>
**Section 125 Vision** | `employee_deduction`: `fixed`, `percent`<br>
**HSA (pre-tax)**| `employee_deduction`: `fixed`, `percent`
**HSA (post-tax)**| `employee_deduction`: `fixed`, `percent`
**FSA Medical** | `employee_deduction`: `fixed`, `percent`
**Simple IRA** | `employee_deduction`: `fixed`, `percent`
**Commuter** | `employee_deduction`: `fixed`, `percent`<br>

<!-- type: tab-end -->

### Paylocity

<!--
type: tab
title: Supported Operations
-->

Benefit | Read Company Benefits | Create Company Benefits | Read Individual Benefits | Enroll/Unenroll Individual Benefits
--------|----------|---------|------------|------------
**401(k)** | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |
**Roth 401(k)** | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |
**401(k) Loan** | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |
**403(b)** | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |
**Roth 403(b)** | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |
**457** | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |
**Roth 457**  | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |
**Simple IRA** | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |
**HSA (post-tax)** | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |
**HSA (pre-tax)** | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |
**FSA Dependent** | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |
**FSA Medical** | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |
**Section 125 Dental** | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |
**Section 125 Medical** | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |
**Section 125 Vision** | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |
**Commuter (pre-tax)** | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |
**Custom pre-tax** | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |
**Custom post-tax** | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |

<!--
type: tab
title: Supported Features
-->

Benefit | Features
--------|----------
**401(k)** | `company_contribution`: `fixed`, `percent`<br>`employee_deduction`: `fixed`, `percent`<br>`catch_up`<br>`annual_maximum`
**Roth 401(k)** | `company_contribution`: `fixed`, `percent`<br>`employee_deduction`: `fixed`, `percent`<br>`catch_up`<br>`annual_maximum`
**401(k) Loan** | `company_contribution`: `fixed`, `percent`<br>`employee_deduction`: `fixed`, `percent`<br>`catch_up`<br>`annual_maximum`
**403(b)** | `company_contribution`: `fixed`, `percent`<br>`employee_deduction`: `fixed`, `percent`<br>`catch_up`<br>`annual_maximum`
**Roth 403(b)**| `company_contribution`: `fixed`, `percent`<br>`employee_deduction`: `fixed`, `percent`<br>`catch_up`<br>`annual_maximum`
**457** | `company_contribution`: `fixed`, `percent`<br>`employee_deduction`: `fixed`, `percent`<br>`annual_maximum`
**Roth  457** | `company_contribution`: `fixed`, `percent`<br>`employee_deduction`: `fixed`, `percent`<br>`annual_maximum`
**Section 125 Dental** | `company_contribution`: `fixed`, `percent`<br>`employee_deduction`: `fixed`, `percent`<br>`annual_maximum`
**Section 125 Medical**| `company_contribution`: `fixed`, `percent`<br>`employee_deduction`: `fixed`, `percent`<br>`annual_maximum`
**Section 125 Vision** | `company_contribution`: `fixed`, `percent`<br>`employee_deduction`: `fixed`, `percent`<br>`annual_maximum`
**HSA (pre-tax)**| `company_contribution`: `fixed`, `percent`<br>`employee_deduction`: `fixed`, `percent`<br>`annual_maximum`
**HSA (post-tax)**| `company_contribution`: `fixed`, `percent`<br>`employee_deduction`: `fixed`, `percent`<br>`annual_maximum`
**FSA Medical** | `company_contribution`: `fixed`, `percent`<br>`employee_deduction`: `fixed`, `percent`<br>`annual_maximum`
**FSA Dependent Care** | `company_contribution`: `fixed`, `percent`<br>`employee_deduction`: `fixed`, `percent`<br>`annual_maximum`
**Simple IRA** | `company_contribution`: `fixed`, `percent`<br>`employee_deduction`: `fixed`, `percent`<br>`annual_maximum`
**Commuter** | `company_contribution`: `fixed`, `percent`<br>`employee_deduction`: `fixed`, `percent`
**Custom pre-tax** | `company_contribution`: `fixed`, `percent`<br>`employee_deduction`: `fixed`, `percent`
**Custom post-tax** | `company_contribution`: `fixed`, `percent`<br>`employee_deduction`: `fixed`, `percent`

<!-- type: tab-end -->

### Paytime

<!--
type: tab
title: Supported Operations
-->

Benefit | Read Company Benefits | Create Company Benefits | Read Individual Benefits | Enroll/Unenroll Individual Benefits
--------|----------|---------|------------|------------
**401(k)** | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |
**Roth 401(k)** | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |
**401(k) Loan** | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |
**403(b)** | n/a | n/a | n/a | n/a |
**Roth 403(b)** | n/a | n/a | n/a | n/a |
**457** | n/a | n/a | n/a | n/a |
**Roth 457**  | n/a | n/a | n/a | n/a |
**Simple IRA** | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |
**HSA (post-tax)** | n/a | n/a | n/a | n/a |
**HSA (pre-tax)** | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |
**FSA Dependent** | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |
**FSA Medical** | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |
**Section 125 Dental** | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |
**Section 125 Medical** | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |
**Section 125 Vision** | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |
**Commuter (pre-tax)** | n/a | n/a | n/a | n/a |
**Custom pre-tax** | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |
**Custom post-tax** | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |

<!--
type: tab
title: Supported Features
-->

Benefit | Features
--------|----------
**401(k)** | `company_contribution`: `percent`<br>`employee_deduction`: `fixed`, `percent`
**Roth 401(k)** | `company_contribution`: `percent`<br>`employee_deduction`: `fixed`, `percent`
**401(k) Loan** | `company_contribution`: `percent`<br>`employee_deduction`: `fixed`, `percent`

<!-- type: tab-end -->

### Quickbooks

<!--
type: tab
title: Supported Operations
-->

Benefit | Read Company Benefits | Create Company Benefits | Read Individual Benefits | Enroll/Unenroll Individual Benefits
--------|----------|---------|------------|------------
**401(k)** | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |
**Roth 401(k)** | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |
**401(k) Loan** | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |
**403(b)** | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |
**Roth 403(b)** | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |
**457** | n/a | n/a | n/a | n/a |
**Roth 457**  | n/a | n/a | n/a | n/a |
**Simple IRA** | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |
**HSA (post-tax)** | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |
**HSA (pre-tax)** | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |
**FSA Dependent** | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |
**FSA Medical** | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |
**Section 125 Dental** | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |
**Section 125 Medical** | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |
**Section 125 Vision** | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |
**Commuter (pre-tax)** | n/a | n/a | n/a | n/a |
**Custom pre-tax** | n/a | n/a | n/a | n/a |
**Custom post-tax** | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |

<!--
type: tab
title: Supported Features
-->

Benefit | Features
--------|----------
**401(k)** | `company_contribution`: `fixed`, `percent`<br>`employee_deduction`: `fixed`, `percent`<br>`catch_up`<br>`annual_maximum`
**Roth 401(k)** | `employee_deduction`: `fixed`, `percent`<br>`annual_maximum`
**401(k) Loan** | `employee_deduction`: `fixed`, `percent`<br>`annual_maximum`
**403(b)** | `company_contribution`: `fixed`, `percent`<br>`employee_deduction`: `fixed`, `percent`<br>`catch_up`<br>`annual_maximum`
**Roth 403(b)**| `employee_deduction`: `fixed`, `percent`<br>`annual_maximum`
**Simple IRA**| `company_contribution`: `fixed`, `percent`<br>`employee_deduction`: `fixed`, `percent`<br>`catch_up`<br>`annual_maximum`
**HSA (pre-tax)**| `employee_deduction`: `fixed`, `percent`<br>`annual_maximum`
**HSA (post-tax)**| `employee_deduction`: `fixed`, `percent`<br>`annual_maximum`
**FSA Dependent** | `employee_deduction`: `fixed`, `percent`
**FSA Medical** | `employee_deduction`: `fixed`, `percent`<br>`annual_maximum`
**Section 125 Dental** | `company_contribution`: `fixed`, `percent`<br>`employee_deduction`: `fixed`, `percent`<br>`annual_maximum`
**Section 125 Medical**| `company_contribution`: `fixed`, `percent`<br>`employee_deduction`: `fixed`, `percent`<br>`annual_maximum`
**Section 125 Vision** | `company_contribution`: `fixed`, `percent`<br>`employee_deduction`: `fixed`, `percent`<br>`annual_maximum`
**Custom post-tax** | `employee_deduction`: `fixed`, `percent`<br>`annual_maximum`


<!-- type: tab-end -->

### Trinet

<!--
type: tab
title: Supported Operations
-->

Benefit | Read Company Benefits | Create Company Benefits | Read Individual Benefits | Enroll/Unenroll Individual Benefits
--------|----------|---------|------------|------------
**401(k)** | <strong><span style="color:red">x</span></strong> | * | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |
**Roth 401(k)** | <strong><span style="color:red">x</span></strong> | * | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |

<!--
type: tab
title: Supported Features
-->

Benefit | Features
--------|----------
**401(k)** | `employee_deduction`: `fixed`, `percent`<br>`annual_maximum`
**Roth 401(k)** | `employee_deduction`: `fixed`, `percent`<br>`annual_maximum`

<!-- type: tab-end -->

### Zenefits

<!--
type: tab
title: Supported Operations
-->

Benefit | Read Company Benefits | Create Company Benefits | Read Individual Benefits | Enroll/Unenroll Individual Benefits
--------|----------|---------|------------|------------
**401(k)** | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |
**Roth 401(k)** | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |
**401(k) Loan** | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |
**403(b)** | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |
**Roth 403(b)** | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |
**457** | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |
**Roth 457**  | n/a | n/a | n/a | n/a |
**Simple IRA** | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |
**HSA (post-tax)** | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |
**HSA (pre-tax)** | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |
**FSA Dependent** | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |
**FSA Medical** | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |
**Section 125 Dental** | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |
**Section 125 Medical** | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |
**Section 125 Vision** | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |
**Commuter (pre-tax)** | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |
**Custom pre-tax** | n/a | n/a | n/a | n/a |
**Custom post-tax** | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |

<!--
type: tab
title: Supported Features
-->

Benefit | Features
--------|----------
**401(k)** | `company_contribution`: `fixed`, `percent`<br>`employee_deduction`: `fixed`, `percent`<br>`catch_up`<br>`annual_maximum`
**Roth 401(k)** | `company_contribution`: `fixed`, `percent`<br>`employee_deduction`: `fixed`, `percent`<br>`catch_up`<br>`annual_maximum`
**401(k) Loan** | `employee_deduction`: `fixed`, `percent`<br>`annual_maximum`
**403(b)** | `company_contribution`: `fixed`, `percent`<br>`employee_deduction`: `fixed`, `percent`<br>`catch_up`<br>
**Roth 403(b)**| `company_contribution`: `fixed`, `percent`<br>`employee_deduction`: `fixed`, `percent`<br>`catch_up`<br>
**457** | `company_contribution`: `fixed`, `percent`<br>`employee_deduction`: `fixed`, `percent`<br>`catch_up`<br>
**Section 125 Dental** | `company_contribution`: `fixed`, `percent`<br>`employee_deduction`: `fixed`, `percent`<br>
**Section 125 Medical**| `company_contribution`: `fixed`, `percent`<br>`employee_deduction`: `fixed`, `percent`<br>
**Section 125 Vision** | `company_contribution`: `fixed`, `percent`<br>`employee_deduction`: `fixed`, `percent`<br>
**HSA (pre-tax)**| `company_contribution`: `fixed`, `percent`<br>`employee_deduction`: `fixed`, `percent`<br>`annual_maximum`
**HSA (post-tax)**| `company_contribution`: `fixed`, `percent`<br>`employee_deduction`: `fixed`, `percent`<br>`annual_maximum`
**FSA Dependent** | `company_contribution`: `fixed`, `percent`<br>`employee_deduction`: `fixed`, `percent`<br>`annual_maximum`
**FSA Medical** | `company_contribution`: `fixed`, `percent`<br>`employee_deduction`: `fixed`, `percent`<br>`annual_maximum`
**Commuter** | `company_contribution`: `fixed`, `percent`<br>`employee_deduction`: `fixed`, `percent`<br>
**Custom post-tax** | `company_contribution`: `fixed`, `percent`<br>`employee_deduction`: `fixed`, `percent`<br>

<!-- type: tab-end -->

### Wave

<!--
type: tab
title: Supported Operations
-->

Benefit | Read Company Benefits | Create Company Benefits | Read Individual Benefits | Enroll/Unenroll Individual Benefits
--------|----------|---------|------------|------------
**401(k)** | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |
**Roth 401(k)** | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |
**401(k) Loan** | n/a | n/a | n/a | n/a |
**403(b)** | n/a | n/a | n/a | n/a |
**Roth 403(b)** | n/a | n/a | n/a | n/a |
**457** | n/a | n/a | n/a | n/a |
**Roth 457**  | n/a | n/a | n/a | n/a |
**Simple IRA** | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |
**HSA (post-tax)** | n/a | n/a | n/a | n/a |
**HSA (pre-tax)** | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |
**FSA Dependent** | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |
**FSA Medical** | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |
**Section 125 Dental** | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |
**Section 125 Medical** | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |
**Section 125 Vision** | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |
**Commuter (pre-tax)** | n/a | n/a | n/a | n/a |
**Custom pre-tax** | n/a | n/a | n/a | n/a |
**Custom post-tax** | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> | <strong><span style="color:red">x</span></strong> | <strong><span style="color:green">✓</span></strong> |

<!--
type: tab
title: Supported Features
-->

Benefit | Features
--------|----------
**401(k)** | `employee_deduction`: `fixed`<br>`annual_maximum`
**Roth 401(k)** | `employee_deduction`: `fixed`<br>`annual_maximum`
**Section 125 Dental** | `employee_deduction`: `fixed`<br>`annual_maximum`
**Section 125 Medical**| `employee_deduction`: `fixed`<br>`annual_maximum`
**Section 125 Vision** | `employee_deduction`: `fixed`<br>`annual_maximum`
**HSA (pre-tax)**| `employee_deduction`: `fixed`<br>`annual_maximum`<br>`hsa_contribution_limit`: `individual`, `family`
**FSA Medical** | `employee_deduction`: `fixed`<br>`annual_maximum`
**FSA Dependent Care** | `employee_deduction`: `fixed`<br>`annual_maximum`
**Simple IRA** | `employee_deduction`: `fixed`<br>`annual_maximum`
**Custom post-tax** | `employee_deduction`: `fixed`

<!-- type: tab-end -->

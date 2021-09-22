# Benefits

Finch's Benefits endpoints allows users to read and write benefits information under a single, unified API. The table below lays out which benefits features are supported for providers, along with any notable information. Note: One-time post-tax deductions are not currently supported for benefits.

`✓` - supported

`x` - not supported

`n/a` - not supported by provider

### Gusto

**Supported Operations**

Benefit | Read Company Benefits | Create Company Benefits | Read Individual Benefits | Enroll/Unenroll Individual Benefits
--------|----------|---------|------------|------------
**401(k)** | ✓ | ✓ | ✓ | ✓ |
**Roth 401(k)** | ✓ | ✓ | ✓ | ✓ |
**403(b)** | ✓ | ✓ | ✓ | ✓ |
**Roth 403(b)** | ✓ | ✓ | ✓ | ✓ |
**457** | n/a | n/a | n/a | n/a |
**Roth 457**  | n/a | n/a | n/a | n/a |
**Simple IRA** | ✓ | ✓ | ✓ | ✓ |
**HSA (post-tax)** | n/a | n/a | n/a | n/a |
**HSA (pre-tax)** | ✓ | ✓ | ✓ | ✓ |
**FSA Dependent** | ✓ | ✓ | ✓ | ✓ |
**FSA Medical** | ✓ | ✓ | ✓ | ✓ |
**Section 125 Dental** | ✓ | ✓ | ✓ | ✓ |
**Section 125 Medical** | ✓ | ✓ | ✓ | ✓ |
**Section 125 Vision** | ✓ | ✓ | ✓ | ✓ |
**Commuter (pre-tax)** | ✓ | ✓ | ✓ | ✓ |
**Custom pre-tax** | n/a | n/a | n/a | n/a |
**Custom post-tax** | ✓ | ✓ | ✓ | ✓ |

**Suppored Features**

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
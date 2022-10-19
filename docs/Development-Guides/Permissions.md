# Permissions

Each Finch `access_token` can only make API calls to endpoints the end-user has granted an application permission to. Permissions are specified by the `product` parameter when launching Connect. Valid permissions are—

<!--
type: tab
title: HRIS
-->

Permission | Endpoint | Description
---------|----------|---------
 `company` | `/employer/company` | Read basic company data
 `directory` | `/employer/directory` | Read company directory and organization structure
 `individual` | `/employer/individual` | Read individual data, excluding income and employment data
 `employment` | `/employer/employment` | Read individual employment and income data
 `payment` | `/employer/payment` | Read payroll and contractor related payments by the company
 `pay_statement` | `/employer/pay-statement` | Read detailed pay statements for each individual
 `benefits` | `/employer/benefits/*` | Create and manage benefits and benefit enrollment within a company
 `deduction` | `/employer/deduction/*` | (DEPRECATED) Previously used to manage deductions within a company. Please use **`benefits`**.

<!--
type: tab
title: ATS
-->

Permission | Endpoint | Description
---------|----------|---------
  `candidates` | `/ats/candidates` | Read candidate data
  `applications` | `/ats/applications` | Read detailed application data for candidates
  `jobs` | `/ats/jobs`, `/ats/stages` | Read job posting data, as well as existing stages of the job pipeline
  `offers` | `/ats/offers` | Read details about offers managed through the ATS

<!-- type: tab-end -->

  

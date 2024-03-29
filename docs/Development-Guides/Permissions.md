# Permissions

Each Finch `access_token` can only make API calls to endpoints the end-user has granted an application permission to. Permissions are specified by the `product` parameter when launching Connect. Valid permissions are—


Permission | Endpoints | Description
---------|----------|---------
 `company` | `/employer/company` | Read basic company data
 `directory` | `/employer/directory` | Read company directory and organization structure
 `individual` | `/employer/individual` | Read individual data, excluding income and employment data
 `ssn` | `/employer/individual` | Read SSN for individuals.
 `employment` | `/employer/employment` | Read individual employment and income data
 `payment` | `/employer/payment` | Read payroll and contractor related payments by the company
 `pay_statement` | `/employer/pay-statement` | Read detailed pay statements for each individual
 `benefits` | `/employer/benefits/*` | Create and manage benefits and benefit enrollment within a company

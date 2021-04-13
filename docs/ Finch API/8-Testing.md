# Testing

Finch offers three types of test environments for both developers and QA people alike. Each environment provides 
a different experience to help ensure you're able to iterate quickly against our API and gather confidence that
everything is working as expected. The three testing environments available are:

1. Finch Sandbox
2. Payroll Provider Sandbox
3. Live Account Testing

# Finch Sandbox

The Finch Sandbox environment abstracts away the concept of a Payroll provider so that you can focus on getting your
code working with the Finch API. The "Connect" flow is the same, however the credentials that you use to authenticate
will alter the behavior of the API.

To use the sandbox environment, simply open the connect flow appending `sandbox=1` or `sandbox=true` to the query string and select "Finch Sandbox":

![Sandbox flow - connect](../../assets/sandboxConnect.png "Sandbox flow - connect")

From there, enter the credentials for your testing scenario below, exchange your authorization code and start using the API!

![Sandbox flow - credentials](../../assets/sandboxCredentials.png "Sandbox flow - credentials")

## Scenarios

The Finch Sandbox allows for you to test specific scenarios allowing you to customize the area of the system that you'd like to test. The credentials that you use for authenticating your session determine the behavior of the API.

### Simple Scenario

Username             | Password
---------------------|-------------
 `authorized_simple` | `letmein` 

The most basic example to develop against is the simple scenario. The attributes of this scenario are:

* Once authorized, will not require reauthorization.
* A single company attached to the credentials.
* Within the company, a single employee.
* Consequently, a simple directory structure.
* Two sets of pay statements available.

### Complex

Username              | Password
----------------------|-------------
 `authorized_complex` | `letmein` 

The complex scenario provides a larger organization superset to work with. The attributes of this scenario are:

* Once authorized, will not require reauthorization.
* Two companies attached to the credentials. The "Small" company will return "simple scenario" data where as the "Large" company will return a larger data set.
* Consists of 100 employees.
* The directory structure contains multiple levels and departments.
* Some employees have no payments/statements, some have multiple.

### Reauthorization

Username              | Password
----------------------|-------------
 `reauthorization`    | `letmein` 

The reauthorization scenario is a contrived example whereby once connected, will always return a `401` error requesting reauthorization.

# Payroll Provider Sandbox

While the Finch sandbox tries to provide common scenarios for you develop against, it is sometimes useful to be able to set up specific scenarios relevant to your use case/environment. In particular while Finch offers a powerful intermediary format, it can also be useful to be able to test Payroll Provider idiosyncracies. In this case, we provide the ability to be able to 
connect directly to a Payroll Provider's sandbox or test environment so that you can provide both internal acceptance testing and if necessary, provider marketplace acceptance.

Currently the following providers support a sandbox or test environment that we can connect in to:

* ADP
* Workforce Now
* Bamboo HR
* ...

To connect to a payroll provider's sandbox environment simply open the connect flow appending `sandbox=1` or `sandbox=true` to the query string and select the Payroll Provider from the drop down:

![Sandbox flow - Bamboo HR connect](../../assets/sandboxBambooHRConnect.png "Sandbox flow - Bamboo HR connect")

From there, enter the credentials for your test environment and begin testing!

# Live Account Testing

Of course, sandbox testing is useful during development stages however for User Acceptance Testing it is always useful to be able to test against a real live account. If you're unable to 
secure yourself an account that you can use for UAT, Finch has some real account integrations that can be used for readonly acceptance testing.

Provider       |  Username              | Password
---------------|------------------------|----------------
 Gusto         | gusto@uat.tryfinch.com | `letmein2021!`
 Quickbooks    | qbo@uat.tryfinch.com   | `letmein2021!`

# Other scenarios

If you have any feedback, or a specific scenario that you're unsure how you'd test then please feel free to connect with us at testing@tryfinch.com.


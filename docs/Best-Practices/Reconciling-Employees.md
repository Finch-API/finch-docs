# Reconciling Employees

If you have employees or contractors in your database that you need to match with Finch's `individual_id`s, you will need a reliable method to reconcile the two. The following are two best practices for developers building with Finch.

### Recommended: full name + date of birth

All payroll systems require at least a first and last name, therefore, finding a match by full name is a good way of reconciling individuals. However, on rare occasions, naming collisions do happen even within the same company. Therefore, we recommend using a concatenation of `first_name`, `last_name`, and `dob`, all data points available from the `/individual` endpoint. 

<!-- theme: danger -->
> Finch returns `first_name`, `last_name`, and `dob` for all systems we support. However, sometimes all the data points not inputted into the system by the payroll administrator of a company. We recommend confirming with your customer that the data points are inputted into the system for all employees before reconciliation.


### Alternative: email address

Finch returns email addresses from the `/individual` endpoint. The uniqueness of emails, *if they are returned by the underlying employment system*, makes it a good data point to reconcile employees against. 

<!-- theme: danger -->
> Finch's API does not always return emails. We find `first_name`, `last_name`, and `dob` are more consistent than `email`s.

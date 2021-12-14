# Rate Limits

Finch will return a rate limit error with the HTTP status code `429` when the request rate limit for an application or `token` has been exceeded for a given `product`.

*** 

## Application

Applications are rate limited on a per `product` basis with the following limits.

Product | Max requests initiated per minute
-------|-------------
`company` | 20
`directory` | 20
`individual` | 20
`employment` | 20
`payment` | 12
`pay-statement` | 12

## Access Token

Access tokens are rate limited on a per `product` basis with the following limits.

Product | Max requests initiated per minute
-------|-------------
`company` | 4
`directory` | 4
`individual` | 4
`employment` | 4
`payment` | 2
`pay-statement` | 2

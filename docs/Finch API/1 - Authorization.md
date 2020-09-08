## Authorization

Authorization allows applications to authorize and interact with payroll and HRIS providers using the Finch API.

### Redirect URIs

To authorize with Finch, you'll need to provide one or more redirect URIs. The user will be redirected to the specified URI upon authorization. On redirect, the URI will contain an authorization code query parameter that must be exchanged with Finch's authorization server for an access token.

The redirect URIs must match one of the following formats—


Protocol | Format | Examples
---------|----------|---------
 HTTP | A localhost URI with protocol `http://` | `http://localhost:8000`
 A2 | B2 | C2
 A3 | B3 | C3
---
stoplight-id: 503f5ff508616
---

# Redirect URIs

To authorize with Finch, you'll need to provide one or more redirect URIs. The user will be redirected to the specified URI upon successfully authorizing your application access to their employment system. On redirect, the URI will contain an authorization `code` query parameter that must be exchanged with Finch's authorization server for an access token.

The default redirect URI is **`https://tryfinch.com`**. For a custom redirect URI, navigate to your application on the developer dashboard or send the team a message on Slack!

<!-- theme: info -->
> Users of the Finch React SDK don't need to set up redirect URI handling.

The redirect URIs must match one of the following formats—

Protocol | Format | Examples
---------|----------|---------
 HTTP | A localhost URI with protocol `http://` | `http://localhost:8000`
 HTTPS | A URI with protocol `https://` | `https://example.com`
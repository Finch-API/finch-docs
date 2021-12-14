# Assisted Connect Flow

Assisted Connect Flow (ACF) is our semi-automated product that expands coverage to 70+ providers. In contrast to our automated connections, the data for ACF providers is refreshed every 2 weeks. Our full list of coverage — for both API and ACF providers — can be found [here](https://tryfinch.notion.site/2484846e745343638e792ac0ff27481c?v=24efa5ea0cd44de89f3f8d3fbbf2ec6a).

Contact our team at `developers@tryfinch.com` to get started or for more questions regarding pricing, missing providers, etc.

---

## Integrating Assisted Connect into your application

### Application setup
Contact the Finch team at `developers@tryfinch.com` to setup your application to work with Assisted Connect.

### Launch Connect with the `manual` flag
<!-- theme: info -->
> For Assisted Connect providers on Connect, your users will see instructions on how they can manually connect their employment system to Finch.

Launch [Connect](../Integrating-with-Finch/Integrate-Finch-Connect/Redirect-to-Connect.md) with `manual=true` so your user can view all the Assisted Connect providers Finch supports. After granting your application access, you can retrieve an authorization `code` and exchange it for an `access_token` as usual.


### Handle API responses with a `202` status code
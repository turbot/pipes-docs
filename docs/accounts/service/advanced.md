---
title: Advanced
sidebar_label: Advanced
---

# Service Account Advanced Settings

Owners at the level the service account was created (organization or tenant) can modify the advanced settings for a service account.

## Credentials

Service accounts use API tokens for authentication.  You can create, view, and revoke API tokens for your service account from the **Credentials** page.

### Tokens

You can create API tokens for your service account which can be used to access the [Turbot Pipes API](/pipes/docs/reference/api). 

A service account can have up to 2 tokens at a time.

Click **New Token** to create a new API token. You will be prompted to enter an optional `Title` and select an `Expiration` date for the token. The expiration can be set to a specific duration or to `Never`, which means the token will not expire.

<img src="/images/docs/pipes/cloud-user-create-token.png" width="200pt"/>
<br />

> [!NOTE]
> If you're on an [Enterprise Plan](/pipes/docs/accounts/tenant#enterprise-plan) with a custom [Tenant](/pipes/docs/accounts/tenant), the [Maximum Token Expiration](/pipes/docs/accounts/tenant/authentication#maximum-token-expiration) setting will apply to the token expiration.

The token will be masked, but you can reveal it by clicking the eye icon or hovering over it and clicking the clipboard icon to copy it. Make a secure note of the token, as you will not be able to retrieve it again.

You can deactivate or delete a token from the list by clicking the options menu button ('three dots' button) and selecting **Deactivate** or **Delete** from the menu.
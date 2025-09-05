---
title: Manage
sidebar_label: Manage
---

# Manage Service Accounts

Management of a service account is available to owners of the billing entity (organization or tenant) in which the service account was created.

To manage a service account, navigate to the **Members** tab of the organization or tenant in which the service account was created. Select the cog button to the right of the service account you wish to manage.

<img src="/images/docs/pipes/pipes-service-account-member.png" width="400pt"/><br />

## Tokens

The **Tokens** tab allows you to create and manage API tokens for your service account. API tokens are used for authenticating API requests made by the service account.

A service account can have a maximum of **2** API tokens.

Click **New Token** to create a new API token. You will be prompted to enter an optional `Title` and select an `Expiration` date for the token. The expiration can be set to a specific duration or to `Never`, which means the token will not expire.

<img src="/images/docs/pipes/cloud-user-create-token.png" width="200pt"/>
<br />

> [!NOTE]
> If you're on an [Enterprise Plan](/pipes/docs/accounts/tenant#enterprise-plan) with a custom [Tenant](/pipes/docs/accounts/tenant), the [Maximum Token Expiration](/pipes/docs/accounts/tenant/authentication#maximum-token-expiration) setting will apply to the token expiration.

The token will be masked, but you can reveal it by clicking the eye icon or hovering over it and clicking the clipboard icon to copy it. Make a secure note of the token, as you will not be able to retrieve it again.

You can `deactivate` or `delete` a token from the list by clicking the options menu button ('three dots' button) and selecting **Deactivate** or **Delete** from the menu.

## Audit Log

The **Audit Log** tab provides a log of API activity associated with your service account including _who_ did _what_ and _when_.

<img src="/images/docs/pipes/pipes-service-account-audit.png" width="400pt"/><br />

## Settings

The **Settings** tab allows you to update or delete the service account.

<img src="/images/docs/pipes/pipes-service-account-settings.png" width="400pt"/><br />

You may update the **Title** or **Description** of the service account. Click **Save** to apply your changes.

You may delete the service account by clicking the **Delete Service Account** button. You will be prompted to confirm deletion; enter the service account identifier shown and click **Delete**.

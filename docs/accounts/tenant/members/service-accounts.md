---
title: Service Accounts
sidebar_label: Service Accounts
---

# Service Accounts

Service Accounts are a specialized type of user designed for programmatic access to Turbot Pipes.

The primary use case for service accounts is to enable automation and integration scenarios, where a non-human user needs to interact with the Pipes platform. 
Service accounts can be used in CI/CD pipelines, automated scripts, or other systems that require access to Pipes resources without human intervention.

Service accounts are managed within Turbot Pipes and, as such, do not require a provisioned user from your user directory (SAML, Google, GitHub, etc).

## Limitations

Service accounts have the following limitations:
- Cannot log in via the Console (web interface).
- Cannot create/manage personal resources, i.e., workspaces.
- Cannot modify themselves or other service accounts.
- Can only be created and managed from either the organization or tenant level, depending on your plan.
  - **[Team Plan](/pipes/docs/accounts/org#team-plan)**: Service accounts can be [created at the organization](/pipes/docs/accounts/org/members#service-accounts) level.
  - **[Enterprise Plan](/pipes/docs/accounts/tenant#enterprise-plan)**: Service accounts can be [created at the tenant](/pipes/docs/accounts/tenant/members#service-accounts) level.

## Billing Considerations

From a billing standpoint, each service account is classified as a user in your [Team](/pipes/docs/accounts/org#team-plan) or [Enterprise](/pipes/docs/accounts/tenant#enterprise-plan) plan. 

Service accounts are billed like any other user. They will count against the included users in your plan and are billed at the same rate as individual users.

## Creating Service Accounts

**Service Accounts** are a specialized type of user designed for programmatic access to Turbot Pipes.

To create a service account, navigate to **Members** from the **Tenant Settings** section. Click the **Add Member** button and select **Create Service Account** from the dropdown options, enter a title and if desired, an _optional_ description for the service account, and click **Create**.

<img src="/images/docs/pipes/pipes-service-account-create.png" width="300pt"/><br />

The service account will be created with the **Member** role by default. You can change the role if desired via the **Change Role** action on the options menu button ('three dots' button). 

You can then [manage](/pipes/docs/accounts/tenant/members/service-accounts#managing-service-accounts) the service account via the cog. This will allow access to various settings, such as amending the title or managing the service account's access tokens.

Once you have created a service account in your tenant, you can grant it permissions from the **Members** page for the [organizations](/pipes/docs/accounts/tenant/members) and [workspaces](/pipes/docs/workspaces/members) in the tenant.


## Managing Service Accounts

Management of a service account is available to owners of the billing entity (organization or tenant) in which the service account was created.

To manage a service account, navigate to the **Members** tab of the organization or tenant in which the service account was created. Select the cog button to the right of the service account you wish to manage.

<img src="/images/docs/pipes/pipes-service-account-member.png" width="400pt"/><br />

### Tokens

The **Tokens** tab allows you to create and manage API tokens for your service account. API tokens are used for authenticating API requests made by the service account.

A service account can have a maximum of **2** API tokens.

Click **New Token** to create a new API token. You will be prompted to enter an optional `Title` and select an `Expiration` date for the token. The expiration can be set to a specific duration or to `Never`, which means the token will not expire.

<img src="/images/docs/pipes/cloud-user-create-token.png" width="400pt"/>
<br />

> [!NOTE]
> If you're on an [Enterprise Plan](/pipes/docs/accounts/tenant#enterprise-plan) with a custom [Tenant](/pipes/docs/accounts/tenant), the [Maximum Token Expiration](/pipes/docs/accounts/tenant/authentication#maximum-token-expiration) setting will apply to the token expiration.

The token will be masked, but you can reveal it by clicking the eye icon or hovering over it and clicking the clipboard icon to copy it. Make a secure note of the token, as you will not be able to retrieve it again.

You can `deactivate` or `delete` a token from the list by clicking the options menu button ('three dots' button) and selecting **Deactivate** or **Delete** from the menu.

### Audit Log

The **Audit Log** tab provides a log of API activity associated with your service account, including _who_ did _what_ and _when_.

<img src="/images/docs/pipes/pipes-service-account-audit.png" width="400pt"/><br />

### Settings

The **Settings** tab allows you to update or delete the service account.

<img src="/images/docs/pipes/pipes-service-account-settings.png" width="400pt"/><br />

You may update the **Title** or **Description** of the service account. Click **Save** to apply your changes.

You may delete the service account by clicking the **Delete Service Account** button. You will be prompted to confirm deletion; enter the service account identifier shown and click **Delete**.


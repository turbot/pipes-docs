---
title: Members
sidebar_label: Members
---

# Tenant Members

You can add and remove users and service accounts from the **Members** tab on your **Tenant Settings** page. Select your profile picture at the top right of the Pipes console, and select **Tenant Settings** from the menu.

Only users that have been invited to the tenant or have logged in via a [trusted login domain](/pipes/docs/accounts/tenant/authentication#trusted-login-domains) will have access to the tenant.

A user can be invited as either a **Member** or an **Owner**, a service account will always be created as a **Member** by default but can be given an **Owner** role if desired.

## Tenant Roles

| Role     | Description
|----------|------------------------------------------------------
| `Member` |  The user has access to the tenant but no implied permissions. Members cannot see tenant settings, invite other tenant members, or create an organization.
| `Owner` |  The user has full ownership of the tenant and can manage tenant settings and tenant members.  Owners have full control of all organizations in the tenant.

## Inviting Tenant Members

To invite a new tenant member, navigate to **Members** from the **Tenant Settings** section. Click the **Add Member** button and then select **Invite Member** from the dropdown options. Enter the email address of the user you wish to invite and select the role you wish to assign them. Click **Invite**.

<img src="/images/docs/pipes/pipes-enterprise-people-invite-member.png" width="400pt"/><br />

## Service Accounts

To create a [service account](/pipes/docs/accounts/service), navigate to **Members** from the **Tenant Settings** section. Click the **Add Member** button and select **Create Service Account** from the dropdown options, enter a title and if desired, an _optional_ description for the service account and click **Create**.

<img src="/images/docs/pipes/pipes-service-account-create.png" width="200pt"/><br />

The service account will be created with the **Member** role by default. You can change the role to **Owner** if desired. 

You can then [manage](/pipes/docs/accounts/service/manage) via the cog, this will allow access to various settings such as amending the title or managing the service accounts access tokens.

<img src="/images/docs/pipes/pipes-service-account-member.png" width="400pt"/><br />

Service accounts are granted permissions in organizations and workspaces in the same way as users, via adding as a member and assigning the required role.

## Last Activity

The **Last Activity** column represents the most recent date on which an activity was performed by a user in the tenant. This includes any interaction or action initiated by a user, such as logging into the tenant, accessing an org / workspace, running a Steampipe query or performing any other activity on any resource under the tenant. The column serves as a timestamp to track the latest user engagement within the tenant, providing insights into user activity and system usage trends.
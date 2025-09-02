---
title: People
sidebar_label: People
---

# Tenant Members

You can add and remove users from the **People** tab on your **Tenant Settings** page. Select your profile picture at the top right of the Pipes console, and select **Tenant Settings** from the menu.

To invite a user to your organization, click **Invite User**. Enter an email
address or the user handle of an existing user and select a role for the user,
and click **Add**.

Only users that have been invited to the tenant or have logged in via a [trusted login domain](/pipes/docs/accounts/tenant/authentication#trusted-login-domains) will have access to the tenant.

A user can be invited as either a **Member** or an **Owner**.

## Tenant Roles

| Role     | Description
|----------|------------------------------------------------------
| `Member` |  The user has access to the tenant but no implied permissions. Members cannot see tenant settings, invite other tenant members, or create an organization.
| `Owner` |  The user has full ownership of the tenant and can manage tenant settings and tenant members.  Owners have full control of all organizations in the tenant.

## Inviting Tenant Members

To invite a new tenant member, navigate to **People** from the **Tenant Settings** section. Click **Invite Member**. Enter the email address of the user you wish to invite and select the role you wish to assign them. Click **Invite**.

<img src="/images/docs/pipes/pipes-enterprise-people-invite-member.png" width="400pt"/>

## Manage Service Accounts

To create a [service account](/pipes/docs/accounts/service), click the arrow on the **Invite Member** button and select **Create Service Account**, enter a title and if desired, an _optional_ description for the service account and click **Create**.

The service account will be created with the **Member** role by default.  You can change the role to **Owner** if desired, and you can also invite and assign permissions to the service account in individual organizations as needed as you would a regular user.

## Last Activity

The **Last Activity** column represents the most recent date on which an activity was performed by a user in the tenant. This includes any interaction or action initiated by a user, such as logging into the tenant, accessing an org / workspace, running a Steampipe query or performing any other activity on any resource under the tenant. The column serves as a timestamp to track the latest user engagement within the tenant, providing insights into user activity and system usage trends.
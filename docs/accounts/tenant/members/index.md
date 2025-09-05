---
title: Members
sidebar_label: Members
---

# Tenant Members

You can add and remove users and service accounts from the **Members** tab on your **Tenant Settings** page. Select your profile picture at the top right of the Pipes console, and select **Tenant Settings** from the menu.

Only users who have been invited to the tenant or have logged in via a [trusted login domain](/pipes/docs/accounts/tenant/authentication#trusted-login-domains) will have access to the tenant.

A user can be invited as either a **Member** or an **Owner**. A service account will always be created as a **Member** by default, but can be given an **Owner** role if desired.

## Tenant Roles

| Role     | Description
|----------|------------------------------------------------------
| `Member` |  The user has access to the tenant but no implied permissions. Members cannot see tenant settings, invite other tenant members, or create an organization.
| `Owner` |  The user has full ownership of the tenant and can manage tenant settings and tenant members.  Owners have full control of all organizations in the tenant.

## Inviting Tenant Members

To invite a new tenant member, navigate to **Members** from the **Tenant Settings** section. Click the **Add Member** button and then select **Invite Member** from the dropdown options. Enter the email address of the user you wish to invite and select the role you wish to assign them. Click **Invite**.

<img src="/images/docs/pipes/pipes-enterprise-people-invite-member.png" width="400pt"/><br />


## Managing Service Accounts

You can [create, delete, and manage service accounts](/pipes/docs/accounts/tenant/members/service-accounts) for your tenant from this page.  Service accounts are a specialized type of user designed for programmatic access to Turbot Pipes.


## Last Activity

The **Last Activity** column represents the most recent date on which an activity was performed by a user in the tenant. This includes any interaction or action initiated by a user, such as logging into the tenant, accessing an organization or workspace, running a Steampipe query, or performing any other activity on any resource under the tenant. The column serves as a timestamp to track the latest user engagement within the tenant, providing insights into user activity and system usage trends.
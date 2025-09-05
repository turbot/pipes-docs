---
title: Members
sidebar_label: Members
---

# Members

You can grant and revoke access to users and service accounts from the **Members** tab on your organization page.

## Organization Roles

| Role       | Description 
| ---------- | --------------------------------------------------------------------------------
| **Member** | Can be granted permissions in workspaces and see members of the organization. Members are not granted access to any workspaces by default.
| **Owner** | Have full administrative rights to the organization, including complete access to all workspaces, connections, users, groups, and permissions. Owners are essentially superusers in the organization- they have full implicit access to all workspaces, and their access cannot be removed at the workspace level.

**Org Owners** have implicit access to all workspaces in the organization, and you cannot revoke their access at the workspace level.  **Members**, on the other hand, are not granted access to any workspaces by default; you may [grant access to a workspace](/pipes/docs/workspaces/members) from the **Members** tab on your workspace after they have been added to your organization.



## Adding Organization Members [Enterprise plan]
If you are on an [Enterprise Plan](/pipes/docs/accounts/tenant#enterprise-plan), you can grant access to your organization to any users and [service accounts](/pipes/docs/accounts/tenant/members/service-accounts) in your tenant.  You cannot invite users or create services at the organization level - they must be members of the tenant. 

To add a user to your workspace, click **Add Member**. Enter an email address or user handle of an existing user or service account and select a [role](#organization-roles) for the user


## Inviting Organization Members [Team plan]

If you are on a [Team Plan](/pipes/docs/accounts/org#team-plan), you can invite users to your organization from this page.

To invite a user to your organization, click the **Add Member** button and then select **Invite Member** from the dropdown options. Enter an email address or the user handle of an existing user, select a [role](#organization-roles) for the user, and click **Add**.

To revoke access from a user, select the options menu button ('three dots' button) to the right of the user and click **Remove**. 

## Managing Service Accounts [Team plan]

If you are on a [Team Plan](/pipes/docs/accounts/org#team-plan), you can [create, delete, and manage service accounts](/pipes/docs/accounts/org/members/service-accounts) from this page.  Service accounts are a specialized type of user designed for programmatic access to Turbot Pipes.


## Last Activity

The **Last Activity** column represents the most recent date on which an activity was performed by a user in an organization. This includes interactions such as accessing the organization or any associated workspace, running a Steampipe query in a workspace belonging to the organization, or engaging with any other resources under the organization. This timestamp helps track the latest user engagement, offering valuable insights into activity trends and system usage within the organization.

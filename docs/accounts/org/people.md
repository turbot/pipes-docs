---
title: People
sidebar_label: People
---

# People

You can add and remove users from the **People** tab on your organization page.
To invite a user to your organization, click **Invite Member**. Enter an email
address or the user handle of an existing user, select a role for the user,
and click **Add**:

| Role       | Description 
| ---------- | --------------------------------------------------------------------------------
| **Member** | Can be granted permissions in workspaces and see members of the organization. Members are not granted access to any workspaces by default.
| **Owner** | Have full administrative rights to the organization, including complete access to all workspaces, connections, users, groups, and permissions. Owners are essentially superusers in the organization- they have full implicit access to all workspaces, and their access cannot be removed at the workspace level.


**Org Owners** have implicit access to all workspaces in the organization, and you cannot revoke their access at the workspace level.  **Members**, on the other hand, are not granted access to any workspaces by default; you may [grant access to a workspace](/pipes/docs/workspaces/people) from the **People** tab on your workspace after they have been added to your organization.

To revoke access from a user, select the options menu button ('three dots' button) to the
right of the user and click **Remove**. 

## Manage Service Accounts

If you are on a [Team Plan](/pipes/docs/accounts/org#team-plan) you can create or delete [service accounts](/pipes/docs/accounts/service) from this page.

To create a service account, click the arrow on the **Invite Member** button and select **Create Service Account**, enter a title and if desired, an _optional_ description for the service account and click **Create**.  

The service account will be created with the **Member** role by default.  You can change the role to **Owner** if desired, and you can also invite and assign permissions to the service account in individual workspaces as needed as you would a regular user.

## Last Activity

The **Last Activity** column represents the most recent date on which an activity was performed by a user in an organization. This includes interactions such as accessing the organization or any associated workspace, running a Steampipe query in a workspace belonging to the organization, or engaging with any other resources under the organization. This timestamp helps track the latest user engagement, offering valuable insights into activity trends and system usage within the organization.
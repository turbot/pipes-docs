---
title: Members
sidebar_label: Members
---

# Members

You can add and remove users from the **Members** tab on your organization page.

To invite a user to your organization, click Click the **Add Member** button and then select **Invite Member** from the dropdown options. Enter an email
address or the user handle of an existing user, select a role for the user,
and click **Add**:

| Role       | Description 
| ---------- | --------------------------------------------------------------------------------
| **Member** | Can be granted permissions in workspaces and see members of the organization. Members are not granted access to any workspaces by default.
| **Owner** | Have full administrative rights to the organization, including complete access to all workspaces, connections, users, groups, and permissions. Owners are essentially superusers in the organization- they have full implicit access to all workspaces, and their access cannot be removed at the workspace level.


**Org Owners** have implicit access to all workspaces in the organization, and you cannot revoke their access at the workspace level.  **Members**, on the other hand, are not granted access to any workspaces by default; you may [grant access to a workspace](/pipes/docs/workspaces/members) from the **Members** tab on your workspace after they have been added to your organization.

To revoke access from a user, select the options menu button ('three dots' button) to the
right of the user and click **Remove**. 

## Service Accounts

If you are on a [Team Plan](/pipes/docs/accounts/org#team-plan) you can create or delete [service accounts](/pipes/docs/accounts/service) from this page.

To create a service account, click the **Add Member** button and select **Create Service Account** from the dropdown options, enter a title and if desired, an _optional_ description for the service account and click **Create**.  

<img src="/images/docs/pipes/pipes-service-account-create.png" width="200pt"/><br />

The service account will be created with the **Member** role by default. You can change the role if desired via the **Change Role** action on the options menu button ('three dots' button).

You can then [manage](/pipes/docs/accounts/service/manage) the service account via the cog, this will allow access to various settings such as amending the title or managing the service accounts access tokens.

<img src="/images/docs/pipes/pipes-service-account-member.png" width="400pt"/><br />

Service accounts can then be granted permissions to workspaces within the organization in the same way as users, via adding as a member and assigning the required role.

## Last Activity

The **Last Activity** column represents the most recent date on which an activity was performed by a user in an organization. This includes interactions such as accessing the organization or any associated workspace, running a Steampipe query in a workspace belonging to the organization, or engaging with any other resources under the organization. This timestamp helps track the latest user engagement, offering valuable insights into activity trends and system usage within the organization.
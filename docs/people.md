---
title: People
sidebar_label: People
---

# People

You can add and remove users from the **People** tab on your organization page.
To invite a user to your organization, click **Invite User**. Enter an email
address or the user handle of an existing user and select a role for the user,
and click **Add**:

| Role       | Description                                                                                                                                                                                                                                                                                                          |
| ---------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Member** | Can be granted permissions in workspaces and see members of the organization. Members are not granted access to any workspaces by default.                                                                                                                                                                           |
| **Owner**  | Have full administrative rights to the organization including complete access to all workspaces, connections, users, groups and permissions. Owners are essentially superusers in the organization -- they have full access to all workspaces implicitly, and their access cannot be removed at the workspace level. |


**Org Owners** have implicit
access to all workspaces in the organization, and you cannot revoke their access
at the workspace level.  **Members**, on the other hand, are not granted access to any workspaces by default. You may [grant access to a workspace](#managing-workspace-users) from the **People** tab on your workspace after they have been added to your organization.

To revoke access from a user, select the options menu button ('three dots' button) to the
right of the user and click **Remove**. 

## Managing Workspace Users

Workspaces in an organization can be shared with other members of your
organization. 

To be granted workspace access, the user must first be added to your organization.
Once the user has been added to the organization, then you can grant them access to workspaces.

You can add and remove workspace users from the **People** tab on your workspace
page. To add a user to your workspace, click **Add Member**. 

<img src="/images/docs/pipes/pipes_workspace_add_user.png" width="400pt"/>
<br />

Enter an email
address or the user handle of an existing user and select a role for the user:

| Role         | Description                                                                                                                       |
| ------------ | --------------------------------------------------------------------------------------------------------------------------------- |
| **Reader**   | Has full read access to the workspace.                                                                                            |
| **Operator** | Has full read access to the workspace and can manage snapshots.                                                                   |
| **Owner**    | Has full administrative access to the workspace, aside from adding connections to the workspace which is reserved for org owners. |

Click **Add**. The user will receive an email invitation to join the
organization.

To remove a user from the organization, select the options menu button
('three dots' button) to the right of the user and click **Remove**.  Note that **Org Owners** have implicit
access to all workspaces in the organization, and you cannot revoke their access
at the workspace level.

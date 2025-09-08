---
title: Members
sidebar_label: Members
---

# Members

Workspaces in an organization can be shared with other members of your organization. 
If your workspace is part of an organization, you can manage access from the **Members** tab for your workspace. 

To be granted workspace access, the user must first be [added to your organization](/pipes/docs/accounts/org/members). 
Once the user has been added to the organization, then you can grant them access to workspaces.

You can add and remove workspace users from the **Members** tab on your workspace
page. To add a user to your workspace, click **Add Member**. 

<img src="/images/docs/pipes/pipes_workspace_add_user.png" width="400pt"/>
<br />

Enter an email
address or the user handle of an existing user and select a role for the user:

| Role         | Description                                                                                                                       |
| ------------ | --------------------------------------------------------------------------------------------------------------------------------- |
| **Reader** | Has full read access to the workspace.                                                                                            |
| **Operator** | Has full read access to the workspace and can manage snapshots.                                                                   |
| **Owner** | Has full administrative access to the workspace, aside from adding connections to the workspace, which is reserved for org owners. |

Click **Add**. The user will receive an email invitation to join the
organization.

To remove a user from the organization, select the options menu button
('three dots' button) to the right of the user and click **Remove**.  Note that **Org Owners** have implicit
access to all workspaces in the organization, and you cannot revoke their access
at the workspace level.

## Last Activity

The **Last Activity** column represents the most recent date on which an activity was performed by a user in a workspace. This includes actions such as accessing the workspace, running Steampipe queries, or interacting with any resources within the workspace. It serves as a useful indicator of user engagement, providing insights into workspace activity trends.

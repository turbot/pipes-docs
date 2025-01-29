---
title: Workspaces
sidebar_label: Workspaces
---

# Workspaces

The **Workspaces** page allows you to control various settings which applies to all workspaces across the tenant.


## Snapshot Visibility

**Snapshot Visibility** setting allows you to control the permitted snapshot visibility options across all workspaces in your tenant. By default, workspace admins can share snapshots with anyone using a private link, but you can restrict the same for a workspaces in your tenant.

The following [snapshot visibility](/pipes/docs/using/steampipe/snapshots#sharing-snapshots) settings are supported:

| Setting      | Description                                                                                                                       |
| ------------ | --------------------------------------------------------------------------------------------------------------------------------- |
| **Workspace** | The snapshot is accessible to all members of the workspace in which the snapshot is created.                                     |
| **Anyone with link** | The snapshot is visible to anyone who has the link.                                                                       |

**Workspace** is the minimum level of visibility required for snapshots and is not allowed to be unset.

Turning off **Anyone with link** will restrict users from sharing snapshots across all workspaces of the tenant. This will also prevent users from accessing snapshots that were shared prior to restricting the same.
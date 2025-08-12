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

Turning off **Anyone with link** will restrict users from sharing snapshots across all workspaces of the tenant. This will also prevent users from accessing snapshots that were shared prior to restricting **Anyone with link**.

## Workspace Configuration

The **Workspace Configuration** section allows you to control the permitted workspace configuration options across all workspaces in your tenant. 

<img src="/images/docs/pipes/cloud-tenant-workspace-configuration.png" width="400pt"/>
<br />

The **Personal Workspaces** checkbox allows you to enable or disable the ability for users to create personal workspaces. Disabling this option will prevent users from creating personal workspaces. New tenants have this option _disabled_ by default.

The **Steampipe PostgreSQL connectivity** checkbox allows you to enable or disable the ability for users to connect to the Steampipe PostgreSQL endpoint. Disabling this option will prevent users from connecting directly to the Steampipe PostgreSQL endpoint for all workspaces in the tenant. Additionally, all UI elements containing database endpoint connection information will be removed. New tenants have this option _enabled_ by default.

---
title:  Connections
sidebar_label: Connections
---

# Connections

A **[Connection](https://steampipe.io/docs/managing/connections)** represents a set of tables for a **single data source**.  To query data, you'll need at least one connection, as the other schema types depend on connections to provide credentials and other configuration information.

You can organize connections in **Connection Folders**. This makes it easier to share groups of connections across workspaces in your tenant or organization.

Connections and connection folders may be created at any level of the hierarchy:
- [Tenant-level connections and folders](/pipes/docs/tenants/connections.md) may be shared with any organizations or workspaces in the tenant.
- [Organization-level connections and folders](/pipes/docs/org-connections.md) may be shared with any workspaces in the organization.
- Workspace-level connections and folders may only be used within the workspace in which they are defined; they cannot be shared.



## Managing Connections

You can manage your workspace's connections from the **Advanced** tab.  Navigate to your workspace, go to the **Advanced** tab, then click **Connections** from the menu on the left to see a list of the connections that are currently available to the workspace.  This list will include all the connections that the workspace has permission to use, including tenant-level and organization-level connections and folders, as well as the ones created directly in the workspace.


## Creating Connections

You can create workspace-level connections and folders from the **Advanced/Connections** page for your workspace.

To create a workspace-level connection, ....
To create a workspace-level connection folder, ....

Worskpace-level connections are confined to the workspace in which they are defined, and they cannot be shared.  If you wish to re-use a connection across workspaces, you can create [tenant-level](/pipes/docs/tenants/connections.md) or[organization-level](/pipes/docs/org-connections.md) connections and folders instead, and assign permissions to share them with specific organizations or workspaces.  Tenant and organization connections can be created or deleted from the **Connections** tab for your tenant or organization.
 

You can create connections and folders manually, but they may also be created by [integrations](/pipes/docs/integrations/).  For example, the [AWS](/pipes/docs/integrations/aws), [Azure](/pipes/docs/integrations/azure), and [GCP](/pipes/docs/integrations/gcp) integrations create and manage folders and connections automatically to mirror the organizational structure of your cloud provider.  You can manage permissions to share these connections and folders just like the ones you create manually, but note that folders that are created by integrations are only managed by the integration; you cannot add or remove sub-folders or connections from them.


## Adding Schemas

Granting permissions on a connection or folder makes it available for a workspace to use, but it does not automatically add it as a schema to your workspace database.  After the connection or folder has been created and the permissions have been set, you can add the schema to your workspace from the **Advanced/Connections** page for your workspace.

To attach an individual connection, ...

Instead of attaching connections individually, you may attach a connection folder.  Doing so makes the schemas for all the descendent connections available as schemas in your workspace database.  Your workspace's schemas will remain synchronized when the folder changes;  If a connection is subsequently added to the folder, the schema will automatically be added to any workspace that has the folder attached.  Likewise, when connections are removed from the folder, the corresponding schemas are removed from the workspace.  To attach a folder...



## Removing Schemas
You can remove connection schemas from the **Advanced/Connections** page for your workspace.  Simply find the connection or folder in the list and then .......

You may only detach connections or folders at the level from which they were attached.  If a connection folder is attached, you cannot detach the connection schemas individually, you must detach the folder.


## Deleting Connections
You can delete workspace-level connections from the **Advanced/Connections** page for your workspace.  From the list, click the connection that you wish to delete.  ......  You will be prompted to confirm deletion; enter the connection name and click **Delete**.

Tenant and organization connections can be deleted from the **Connections** tab for the corresponding tenant or organization.
---
title:  Connections
sidebar_label: Connections
---

# Connections

A **[Connection](https://steampipe.io/docs/managing/connections)** represents a set of tables for a **single data source**.  To query data, you'll need at least one connection, as the other schema types depend on connections to provide credentials and other configuration information.

You can organize connections into **Connection Folders**. This makes it easier to share groups of connections across workspaces in your tenant or organization.

Connections and connection folders may be created at any level of the hierarchy:
- [Tenant-level connections and folders](/pipes/docs/tenants/connections) may be shared with any organizations or workspaces in the tenant.
- [Organization-level connections and folders](/pipes/docs/org-connections) may be shared with any workspaces in the organization.
- Workspace-level connections and folders may only be used within the workspace in which they are defined; they cannot be shared.



## Managing Workspace Connections

You can manage your workspace's connections from the **Advanced** tab.  Navigate to your workspace, go to the **Advanced** tab, then click **Connections** from the menu on the left to see a list of the connections that are currently available to the workspace.   The connections page will show the connections and folders in the tenant, arranged hierarchically, and you can click on folders to navigate the folder tree.   

This view will include all the connections that the workspace has permission to use, including tenant-level and organization-level connections and folders, as well as the ones created directly in the workspace. Note that you can add and remove the schemas for the tenant-level and organization-level connections and folders, but you cannot manage their settings here;  The connection properties and folder contents can only be managed on the object where they are defined.  Connections and folders that are created by integrations are dynamically managed by the integration and cannot be manually modified.


## Creating Connections & Folders

You can create workspace-level connections and folders from the **Advanced/Connections** page for your workspace.   The top-level connections and folders are listed by default, and you can click on folders to navigate the folder tree.

To create a workspace-level folder, navigate to the folder in which you would like to create the new folder, then click the **New Connection** button and select **New Folder**.  Give your folder a **Name** and click **Create**.

To create a workspace-level connection, navigate to the folder in which you would like to create the connection, then click the **New Connection** button and select **New Connection**.  Select the **Plugin**, enter a **Handle**, and enter any plugin-specific settings.  Click **Test Connection** to verify your credentials, then **Create** to create the connection.

Workspace-level connections are confined to the workspace in which they are defined, and they cannot be shared.  If you wish to re-use a connection across workspaces, you can create [tenant-level](/pipes/docs/tenants/connections.md) or [organization-level](/pipes/docs/org-connections.md) connections and folders instead, and assign permissions to share them with specific organizations or workspaces.  Tenant and organization connections can be created or deleted from the **Connections** tab for your tenant or organization.
 

You can create connections and folders manually, but they may also be created by [integrations](/pipes/docs/integrations/).  For example, the [AWS](/pipes/docs/integrations/aws), [Azure](/pipes/docs/integrations/azure), and [GCP](/pipes/docs/integrations/gcp) integrations create and manage folders and connections automatically to mirror the organizational structure of your cloud provider.  You can manage permissions to share these connections and folders just like the ones you create manually, but note that folders that are created by integrations are only managed by the integration; you cannot add or remove sub-folders or connections from them.


## Adding Schemas

Granting permissions on a connection or folder makes it available for a workspace to use, but it does not automatically add it as a schema to your workspace database.   After the connection or folder has been created and the permissions have been set, you can add the schema to your workspace from the **Advanced/Connections** page for your workspace. 

You may add schemas for a single connection or a folder.  Adding a folder schema makes the schemas for *all the descendent connections* available as schemas in your workspace database.  Your workspace's schemas will remain synchronized when the folder changes;  If a connection is subsequently added to the folder, the schema will automatically be added to any workspace that has the folder attached.  Likewise, when connections are removed from the folder, the corresponding schemas are removed from the workspace.

To add a schema, go to the **Advanced/Connections** page for your workspace, and navigate to the folder or connection you wish to add, then click **Add to Schema** from the list.



## Removing Schemas
You can remove connection schemas from the **Advanced/Connections** page for your workspace.  Simply find the connection or folder in the list and click **Remove from Schema**.

You may only detach connections or folders at the level from which they were attached.  If a connection folder is attached, you cannot detach the connection schemas individually, you must detach the folder.


## Deleting Connections & Folders
You can delete workspace-level connections and folders from the **Advanced/Connections** page for your workspace.  

To delete a connection, click the gear icon for the connection that you wish to delete.  On the **settings** tab, click  **Delete Connection**.  You will be prompted to confirm deletion. Enter the connection handle then click **Delete Connection**.

To delete a folder, click the gear icon for the folder that you wish to delete.  On the **settings** tab, click **Delete Folder**.  You will be prompted to confirm deletion. Enter the folder title, then click **Delete Folder**.

Tenant and organization connections can be deleted from the **Connections** tab for the corresponding tenant or organization.
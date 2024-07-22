---
title: Connections
sidebar_label: Connections
---



A **[Connection](/pipes/docs/connections)** represents a set of tables for a **single data source**.  To query data, you'll need at least one connection to provide credentials and other configuration information.

You can organize connections into **Connection Folders**. This makes it easier to share groups of connections across workspaces in your tenant.

Connections and folders that are created at the tenant level can be shared with any workspace or organization in the tenant.  You must be assigned the tenant **Owner** role to create, modify and delete tenant connections and folders.

You can create connections and folders manually, but they may also be created by [integrations](/pipes/docs/integrations/).  For example, the [AWS](/pipes/docs/integrations/aws), [Azure](/pipes/docs/integrations/azure), and [GCP](/pipes/docs/integrations/gcp) integrations create and manage folders and connections automatically to mirror the organizational structure of your cloud provider.  You can manage permissions to share these connections and folders just like the ones you create manually, but note that folders that are created by integrations are only managed by the integration; you cannot add or remove sub-folders or connections from them.


## Managing Connections

You can manage your tenant's connections and folders from the **Connections** tab.  Navigate to your tenant, then to the  **Connections** tab.  The connections page will show all the tenant-level connections and folders in the tenant, arranged hierarchically, and you can click on folders to navigate the folder tree.

This view will include all the connections and folders in the tenant, including connections and folders that are created by integrations.  Note that the resources created by an integration are dynamically managed by the integration and cannot be manually modified.


## Adding Connections

You can create connections from the **Connections** tab for your tenant.  The connections page displays the folder connection tree hierarchically.  To add a connection or folder, first navigate to the folder in which to create the new folder or connection.

To create a new folder, go to the folder in which you would like to create the new folder, then click the **New Connection** button and select **New Folder**.   Give your folder a **Name** and click **Create**.  Next, you are prompted to set permissions on the folder.  When you grant permissions on a folder, you also grant permissions for all of its descendent folders and connections.  This simplifies managing groups of connections across your tenant.  Choose workspaces that can use this folder and all of its connections:
- All organizations and organization workspaces
- Specific organizations and/or organization workspaces
- No workspaces

Click **Save**.

To create a connection, navigate to the folder in which you would like to create the connection, then click the **New Connection** button and select **New Connection**.  Select the **Plugin**, enter a **Handle**, and enter any plugin-specific settings.  Click **Test Connection** to verify your credentials, then **Create** to create the connection.  Next, you are prompted to set permissions on the connection.  You may set permissions on individual connections but remember that they also inherit the permissions of their parent folder; setting **No Workspaces** on the connection does not remove permissions if they have been granted on a parent folder, it merely does not grant permission on the individual connection.  Choose workspaces that can use this connection:
- All organizations and organization workspaces
- Specific organizations and/or organization workspaces
- No workspaces

Click **Save**.
 

Tenant-level connections are confined to the tenant in which they are defined, and they cannot be shared with other tenants.
 
You can create connections and folders manually, but they may also be created by [integrations](/pipes/docs/integrations/).  For example, the [AWS](/pipes/docs/integrations/aws), [Azure](/pipes/docs/integrations/azure), and [GCP](/pipes/docs/integrations/gcp) integrations create and manage folders and connections automatically to mirror the organizational structure of your cloud provider.  You can manage permissions to share these connections and folders just like the ones you create manually, but note that folders that are created by integrations are only managed by the integration; you cannot add or remove sub-folders or connections from them.



## Deleting Connections

To permanently delete a connection, navigate to the  **Connections** tab for your tenant. Browse the connection tree, and click the gear icon for the connection that you wish to delete.  On the **Settings/Advanced** tab, click  **Delete Connection**.  You will be prompted to confirm deletion. Enter the connection handle then click **Delete Connection**.

To delete a folder, click the gear icon for the folder that you wish to delete.  On the **Settings** tab, click **Delete Folder**.  You will be prompted to confirm deletion. Enter the folder title, then click **Delete Folder**.

You cannot delete folders or connections that were created by an [integration](/pipes/docs/integrations/) - they are automatically managed by the integration.
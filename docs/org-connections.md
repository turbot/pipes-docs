---
title: Connections
sidebar_label: Connections
---

# Connections

A **[Connection](/pipes/docs/connections)** represents a set of tables for a **single data source**.  To query data, you'll need at least one connection to provide credentials and other configuration information.

You can organize connections into **Connection Folders**. This makes it easier to share groups of connections across workspaces in your tenant or organization.

Connections and folders that are created at the organization level can be [shared](#permissions) with any workspace in the organization.  You must be assigned the organization **Owner** role to create, modify and delete organization connections and folders.

You can create connections and folders manually, but they may also be created by [integrations](/pipes/docs/integrations/).  For example, the [AWS](/pipes/docs/integrations/aws), [Azure](/pipes/docs/integrations/azure), and [GCP](/pipes/docs/integrations/gcp) integrations create and manage folders and connections automatically to mirror the organizational structure of your cloud provider.  You can manage [permissions](#permissions) to share these connections and folders just like the ones you create manually, but note that folders that are created by integrations are only managed by the integration; you cannot add or remove sub-folders or connections from them.


## Managing Connections

You can manage your organization's connections and folders from the **Connections** tab.  Navigate to your organization, then to the  **Connections** tab.  

![](/images/docs/pipes/org-connections-list.png)


The connections tree is arranged hierarchically, and you can click on folders to navigate the folder tree.  

![](/images/docs/pipes/org-connections-list-subfolder.png)


This view will include all the connections that the organization has permission to use, including tenant-level connections and folders, as well as the ones created directly in the organization.  Connections and folders that are created by integrations will also appear but note that these are dynamically managed by the integration and cannot be manually modified.


## Adding Connections

You can create connections from the **Connections** tab for your organization.  The connections page displays the folder connection tree hierarchically.  To add a connection or folder, first navigate to the folder in which to create the new folder or connection.

To create a new folder, go to the folder in which you would like to create the new folder, then click the **New Connection** button and select **New Folder**.   Give your folder a **Name** and click **Create**.  Next, you are prompted to set [permissions](#permissions) on the folder.  When you grant permissions on a folder, you also grant permissions for all of its descendent folders and connections.  This simplifies managing groups of connections across your organizations.  Choose the desired permissions and click **Save**.

To create a connection, navigate to the folder in which you would like to create the connection, then click the **New Connection** button and select **New Connection**.  Select the **Plugin**, enter a **Handle**, and enter any plugin-specific settings.  Click **Test Connection** to verify your credentials, then **Create** to create the connection.  Next, you are prompted to set [permissions](#permissions) on the connection.  You may set permissions on individual connections but remember that they also inherit the permissions of their parent folder; you can revoke permissions that have been granted on a parent folder, though you can add additional permissions. Choose the desired permissions and click **Save**.

Organization-level connections are confined to the organization in which they are defined, and they cannot be shared with other organizations.  If you wish to re-use a connection across organizations, you can create [tenant-level](/pipes/docs/tenants/connections.md) connections and folders instead, and assign permissions to share them with specific organizations or workspaces.  Tenant connections can be created or deleted from the **Connections** tab for your tenant.
 
You can create connections and folders manually, but they may also be created by [integrations](/pipes/docs/integrations/).  For example, the [AWS](/pipes/docs/integrations/aws), [Azure](/pipes/docs/integrations/azure), and [GCP](/pipes/docs/integrations/gcp) integrations create and manage folders and connections automatically to mirror the organizational structure of your cloud provider.  You can manage permissions to share these connections and folders just like the ones you create manually, but note that folders that are created by integrations are only managed by the integration; you cannot add or remove sub-folders or connections from them.


## Deleting Connections

To permanently delete a connection, navigate to the  **Connections** tab for your organization. Browse the connection tree, and click the gear icon for the connection that you wish to delete.  On the **Settings/Advanced** tab, click  **Delete Connection**.  You will be prompted to confirm deletion. Enter the connection handle then click **Delete Connection**.

To delete a folder, click the gear icon for the folder that you wish to delete.  On the **Settings** tab, click **Delete Folder**.  You will be prompted to confirm deletion. Enter the folder title, then click **Delete Folder**.

You cannot delete folders or connections that were created by an [integration](/pipes/docs/integrations/) - they are automatically managed by the integration.  

Tenant-level connections and folders must be deleted from the **Connections** tab for the corresponding tenant.


## Permissions

Connections defined at the organization level can be shared with any workspace in the organization.  Organization-level connections are confined to the organization in which they are defined, and they cannot be shared with other organizations ([Tenant-level connections](/pipes/docs/tenants/connections) provide this capability).

You can make connections available to workspaces by setting permissions, either on individual connections or folders.  When you grant permissions on a folder, all the folders and connections that are members of that folder inherit the same permissions; granting access to a folder implicitly grants access to its sub-folders and connections.  Note that permissions are additive and can only be granted, not denied. If you grant permissions to a workspace for a folder you cannot revoke access for these individual connections, only to the folder as a whole.

You can set permissions for folders and connections from their settings page. Navigate to the desired tenant or org and browse the **Connections** to find the resource you wish to manage.  Click the gear icon for the connection or folder you would like to permission.  From the **Settings** tab, select **Permissions**.


![](/images/docs/pipes/org-connections-perms-toplevel.png)


Select the desired permission: 
- **All workspaces**: Allow access to all existing workspaces in the organization, as well as any new workspaces that are created subsequently.
- **Specific workspaces**:  Allow specific workspaces. You will be prompted to select the workspaces from a list.
- **No permissions**: Do not set any permissions on this connection or folder.

If the folder or connection is a descendant of a folder that has already been shared, you cannot revoke those permissions on the child folder or connection, but you may grant additional access:

![](/images/docs/pipes/org-connections-perms-inherited.png)


Click **Save** to commit the changes.

Note that setting permissions for a connection or folder does not attach its schema to the workspaces, it merely makes it visible to the workspaces so that [it may be attached](/pipes/docs/connections#adding-schemas).
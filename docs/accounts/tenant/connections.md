---
title: Connections
sidebar_label: Connections
---

# Connections

[Connections](/pipes/docs/workspaces/connections) provide the credentials, scope, and configuration information for interacting with an external system.

You can organize connections into **Connection Folders**. This makes it easier to [share](#permissions) groups of connections across workspaces in your tenant.

Connections and folders that are created at the tenant level can be shared with any workspace or organization in the tenant.  You must be assigned the tenant **Owner** role to create, modify and delete tenant connections and folders.

You can create connections and folders manually, but they may also be created by [integrations](/pipes/docs/integrations/).  For example, the [AWS](/pipes/docs/integrations/aws), [Azure](/pipes/docs/integrations/azure), and [GCP](/pipes/docs/integrations/gcp) integrations create and manage folders and connections automatically to mirror the organizational structure of your cloud provider.  You can manage [permissions](#permissions) to share these connections and folders just like the ones you create manually, but note that folders that are created by integrations are only managed by the integration; you cannot add or remove sub-folders or connections from them.


## Managing Connections

You can manage your tenant's connections and folders from the **Connections** tab.  Navigate to your tenant by clicking the double arrow button from the tenant switcher at the top of the Pipes console.  Select your tenant, and then select **Tenant Settings**. This option will only be visible in a custom tenant for which you are a [tenant owner](/pipes/docs/accounts/tenant/people#tenant-roles).  

The **Connections** tab will show all the tenant-level connections and folders.

![](/images/docs/pipes/tenant-connections-list.png)


The connections tree is arranged hierarchically, and you can click on folders to navigate the folder tree.  

![](/images/docs/pipes/tenant-connections-list-subfolder.png)


This view will include all the connections and folders in the tenant, including connections and folders that are created by integrations.  Note that the resources created by an integration are dynamically managed by the integration and cannot be manually modified.


## Adding Connections

You can create connections from the **Connections** tab for your tenant.  The connections page displays the folder connection tree hierarchically.  To add a connection or folder, first navigate to the folder in which to create the new folder or connection.

To create a new folder, go to the folder in which you would like to create the new folder, then click the **New Connection** button and select **New Folder**.   Give your folder a **Name** and click **Create**.  Next, you are prompted to set [permissions](#permissions) on the folder.  When you grant permissions on a folder, you also grant permissions for all of its descendent folders and connections.  This simplifies managing groups of connections across your tenant.  Choose the desired [permissions](#permissions) and click **Save**.

To create a connection, navigate to the folder in which you would like to create the connection, then click the **New Connection** button and select **New Connection**.  Select the **Plugin**, enter a **Handle**, and enter any plugin-specific settings.  Click **Test Connection** to verify your credentials, then **Create** to create the connection.  Next, you are prompted to set [permissions](#permissions) on the connection.   You may set permissions on individual connections but remember that they also inherit the permissions of their parent folder; you can revoke permissions that have been granted on a parent folder, though you can add additional permissions.  Choose the desired [permissions](#permissions) and click **Save**.

 
Tenant-level connections are confined to the tenant in which they are defined, and they cannot be shared with other tenants.
 
You can create connections and folders manually, but they may also be created by [integrations](/pipes/docs/integrations/).  For example, the [AWS](/pipes/docs/integrations/aws), [Azure](/pipes/docs/integrations/azure), and [GCP](/pipes/docs/integrations/gcp) integrations create and manage folders and connections automatically to mirror the organizational structure of your cloud provider.  You can manage permissions to share these connections and folders just like the ones you create manually, but note that folders that are created by integrations are only managed by the integration; you cannot add or remove sub-folders or connections from them.


## Deleting Connections

To permanently delete a connection, navigate to the  **Connections** tab for your tenant. Browse the connection tree, and click the gear icon for the connection that you wish to delete.  On the **Settings/Advanced** tab, click  **Delete Connection**.  You will be prompted to confirm deletion. Enter the connection handle then click **Delete Connection**.

To delete a folder, click the gear icon for the folder that you wish to delete.  On the **Settings** tab, click **Delete Folder**.  You will be prompted to confirm deletion. Enter the folder title, then click **Delete Folder**.

You cannot delete folders or connections that were created by an [integration](/pipes/docs/integrations/) - they are automatically managed by the integration.


## Permissions

Connections defined at the tenant level can be shared with any organization or organization workspace in the tenant.  Tenant-level connections are confined to the tenant in which they are defined, and they cannot be shared with other tenants.

You can make connections available to workspaces by setting permissions, either on individual connections or folders.  When you grant permissions on a folder, all the folders and connections that are members of that folder inherit the same permissions; granting access to a folder implicitly grants access to its sub-folders and connections.  Note that permissions are additive and can only be granted, not denied. If you grant permissions to an identity or workspace for a folder you cannot revoke access for these individual connections, only to the folder as a whole.

You can set permissions for folders and connections from their settings page. Navigate to the desired tenant or org and browse the **Connections** to find the resource you wish to manage.  Click the gear icon for the connection or folder you would like to permission.  From the **Settings** tab, select **Permissions**. 


![](/images/docs/pipes/tenant-connections-perms-toplevel.png)


Select the desired permission: 
- **All organizations and their workspaces**: Allow access to all existing organizations and their workspaces, as well as any new organizations or workspaces that are created subsequently.
- **Specific organizations and their workspaces**:  Allow specific organizations and/or workspaces.  You will be prompted to select the organizations and workspaces from a list.
- **No permissions**: Do not set any permissions on this connection or folder.

If the folder or connection is a descendant of a folder that has already been shared, you cannot revoke those permissions on the child folder or connection, but you may grant additional access:

![](/images/docs/pipes/tenant-connections-perms-inherited.png)

Click **Save** to commit the changes.

Note that setting permissions for a connection or folder does not attach its schema to the workspaces, it merely makes it visible to the workspaces so that [it may be attached](/pipes/docs/workspaces/connections#adding-schemas).
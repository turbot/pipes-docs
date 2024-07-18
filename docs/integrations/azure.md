---
title: Azure Integration
sidebar_label: Azure
---

# Azure Integration

The Azure Integration allows you to automatically import a connection folder hierarchy that mirrors your Azure Organization folder structure, with a connection folder for each Azure management group and a [connection](/pipes/docs/connections) for each subscription in your Azure organization.

The Azure integration will automatically keep the configuration up to date as your organization changes, adding, removing, and modifying connections and folders as subscriptions and management groups are created, deleted, or changed in your Azure Organization.


## Creating the Azure Integration

You can create an integration for a [tenant](/pipes/docs/tenants/) or an [organization]((/pipes/docs/organizations)), and where you create the integration affects the scope of the resources it creates; the resulting connections and folders can only be shared within the entity in which it was created.

| Level                        | Plan                       | Description
|------------------------------|----------------------------|----------------
| [Tenant](/pipes/docs/tenants) | [Enterprise](/pipes/docs/plans/enterprise) | Selectively share Azure connections and folders with any (or all) organization or workspace in the tenant.
| [Org](/pipes/docs/organizations) | [Team](/pipes/docs/plans/team) or [Enterprise](/pipes/docs/plans/enterprise)  | Selectively share Azure connections and folders with any (or all) workspace in the organization.


First, navigate to the **Integrations** page for the appropriate resource:
- To configure an Azure integration for your **Tenant**, click the double arrow button from the tenant switcher at the top of the Pipes console, select your tenant, and then select **Tenant Settings**. This option will only be visible in a custom tenant for which you are a [tenant owner](people#tenant-roles).  Once you've selected your tenant, go to the **Integrations** tab to manage the integrations for the tenant.
- To configure an Azure integration for your **Organization**, click the double arrow button from the organization switcher at the top of the page and select the organization from the dropdown.  Once you've selected your organization, go to the **Integrations** tab to manage the integrations for the organization.



![](/images/docs/integrations_blank.png)

Next, click the **New Integration** button. You will be asked to select an integration to create.

![](/images/docs/integrations_new_Azure.png)

Select **Azure** and click **Next**.

Provide a **Handle** for the integration.  This handle should be meaningful and must be unique for all integrations in the tenant (including any org-level integrations).

Specify the **environment** - **Public Cloud**,  **US Gov Cloud**, or **China Cloud**.

Enter the **Azure Credentials**. At a minimum, the credential must have `Global Reader` access.

?? how do you set this up in Azure????

Enter the **Tenant ID**, **Client ID**, and **Client Secret**.


Optionally, provide a **Handle Prefix** to be pre-pended to the names of connections created from this integration. This is optional but may be useful for organizational purposes, or to ensure the uniqueness of the generated connection handles.

Click the **Test Connection** button to verify that the credentials are configured correctly, then click **Next**.

Finally, select the [Permissions](#permissions) to assign to the root folder created from this Azure integration.  Note that you do not have to set the permissions now and you can change them later.

- **All Organizations and Workspaces**
- **Specific Organizations and Workspaces**
- **No Workspaces**

The permissions on this screen apply to the root folder, thus *all connections and folders* discovered by this integration.  If you want to assign permissions more granular, on a per-subfolder or per-connection basis, select **No Workspaces** at this time, and then manage the permissions on the connections and folders once they have been discovered.

Note also that **All** will not only add permissions for the existing identities and workspaces but will also allow access for any new connections and folders that are created when they are added to the Azure organization.

[screenshot...]

After you have made your selections, click **Create Integration**.  Pipes will begin discovering your subscriptions and management groups and creating folders and connections.


---------

## Modifying the Azure Integration

After you have created an integration, you can change its **Handle**, **Handle Prefix**, or **Credentials**.  You can also change the **Permissions** and **Handle** individually for each child folder or connection.

*Modifying the integration after it has been created will potentially impact any workspaces that use its connections!*
- Changing the **Handle Prefix** will change the handles of all of its connections.
This means that the schema names will change in any workspace to which they are attached.  The schema names, in turn, impact the search path and aggregators that use wildcards.
- Discovery of subscriptions and management groups occurs using the supplied **Credentials**.  If changing the credentials affects access to these subscriptions and management groups that will be reflected in the folders and connections. For example, if the new credentials do not have access to some management groups or subscriptions that were visible to the previous credentials, then the corresponding folders and connections will be deleted and removed from any workspaces where they are attached.

To modify the integration, navigate to the **Integrations** page for the appropriate resource:
- To configure an Azure integration for your **Tenant**, click the double arrow button from the tenant switcher at the top of the Pipes console, select your tenant, and then select **Tenant Settings**. This option will only be visible in a custom tenant for which you are a [tenant owner](people#tenant-roles).  Once you've selected your tenant, go to the **Integrations** tab to manage the integrations for the tenant.
- To configure an Azure integration for your **Organization**, click the double arrow button from the organization switcher at the top of the page and select the organization from the dropdown.  Once you've selected your organization, go to the **Integrations** tab to manage the integrations for the organization.


You can change the **Credentials** or **Handle Prefix** from the **Config** tab.  Make the desired changes and click **Save**.

You can modify the **Handle** from the **Advanced** tab.  Enter the new handle and click **Save**.

You can view the connection tree from the **Connections** tab.  Click on a connection or folder to view or change its properties. You can change the **Permissions** and **Handle** from its **Settings** tab.


## Deleting the Azure Integration

You can delete an integration from its **Advanced** page.

*If you delete an integration, all of its associated folders and connections will be deleted and removed from all workspaces.  This action is not reversible!*

Navigate to the **Integrations** page for the appropriate resource:
- To configure an Azure integration for your **Tenant**, click the double arrow button from the tenant switcher at the top of the Pipes console, select your tenant, and then select **Tenant Settings**. This option will only be visible in a custom tenant for which you are a [tenant owner](people#tenant-roles).  Once you've selected your tenant, go to the **Integrations** tab to manage the integrations for the tenant.
- To configure an Azure integration for your **Organization**, click the double arrow button from the organization switcher at the top of the page and select the organization from the dropdown.  Once you've selected your organization, go to the **Integrations** tab to manage the integrations for the organization.


Go to the **Advanced** page and click the **Delete Integration** button. You will be asked to enter the handle to confirm deletion.  If you wish to *permanently delete the integration and all of its resources*, click **Delete**.

----------


## Permissions
You can create an integration for a tenant or an organization, and where you create the integration affects the scope of the resources it creates; the resulting connections and folders can only be shared within the entity in which it was created.  When creating the integration, you can set **Permissions** for the connections and folders that it creates:
  - Tenant-level connections and folders can be shared with any identity or workspace within the tenant.
  - Org-level connections and folders can be shared with any workspace within the org, but not with other orgs.

When you grant permissions on a folder, all the connections that are members of that folder inherit the same permissions; granting access to a folder implicitly grants access to its connections.  Note that permissions are additive and can only be granted, not denied. If you grant permissions to an identity or workspace for a folder you cannot revoke access for these individual connections, only to the folder as a whole.

You can set permissions for folders and connections from their settings page. Navigate to the desired tenant or org and browse the **Connections** to find the resource you wish to manage.  Click the connection or folder.  From the **Settings** tab, select **Permissions**.  Select the desired permissions and click **Save**.

Note that setting permissions for a connection or folder does not attach its schema to the workspaces, it merely makes it visible to the workspaces so that [it may be attached](/pipes/docs/connections#adding-schemas).

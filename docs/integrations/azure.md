---
title: Azure Integration
sidebar_label: Azure
---

# Azure Integration

The Azure Integration allows you to automatically import a connection folder hierarchy that mirrors your Azure Organization folder structure, with a connection folder for each Azure management group and a [connection](/pipes/docs/connections) for each subscription in your Azure organization.

The Azure integration will automatically keep the configuration up to date as your organization changes, adding, removing, and modifying connections and folders as subscriptions and management groups are created, deleted, or changed in your Azure organization.


## Creating the Azure Integration

You can create an integration for a [tenant](/pipes/docs/tenants/) or an [organization]((/pipes/docs/accounts/org)), and where you create the integration affects the scope of the resources it creates; the resulting connections and folders can only be shared within the entity in which it was created.

| Level                        | Plan                       | Description
|------------------------------|----------------------------|----------------
| [Tenant](/pipes/docs/accounts/tenant) | [Enterprise](/pipes/docs/plans/enterprise) | Selectively share Azure connections and folders with any (or all) organization or workspace in the tenant.
| [Org](/pipes/docs/accounts/org) | [Team](/pipes/docs/plans/team) or [Enterprise](/pipes/docs/plans/enterprise)  | Selectively share Azure connections and folders with any (or all) workspace in the organization.


First, navigate to the **Integrations** page for the appropriate resource:
- To configure an Azure integration for your **Tenant**, click the double arrow button from the tenant switcher at the top of the Pipes console, select your tenant, and then select **Tenant Settings**. This option will only be visible in a custom tenant for which you are a [tenant owner](people#tenant-roles).  Once you've selected your tenant, go to the **Integrations** tab to manage the integrations for the tenant.
- To configure an Azure integration for your **Organization**, click the double arrow button from the organization switcher at the top of the page and select the organization from the dropdown.  Once you've selected your organization, go to the **Integrations** tab to manage the integrations for the organization.




![](/images/docs/pipes/org-integrations-tab.png)

Next, click the **New Integration** button. You will be asked to select an integration to create.

![](/images/docs/pipes/org-integrations-new-azure.png)


Select **Azure** and click **Next**.


![](/images/docs/pipes/org-integrations-azure-setup.png)


Provide a **Handle** for the integration.  This handle should be meaningful and must be unique for all integrations in the tenant (including any org-level integrations).

Specify the **environment** - **Public Cloud**,  **US Gov Cloud**, or **China Cloud**.

Enter the **Azure Credentials**.  Pipes requires a Client ID and Client secret with sufficient permission to access your Azure resources:
- [Create an Entra App Registration](https://learn.microsoft.com/en-us/entra/identity-platform/quickstart-register-app?tabs=client-secret#register-an-application) for Pipes.
- [Create Client Secret credentials](https://learn.microsoft.com/en-us/entra/identity-platform/quickstart-register-app?tabs=client-secret#add-credentials) for the Entra App.
- [Configure permissions](https://learn.microsoft.com/en-us/azure/role-based-access-control/role-assignments-portal) for the App's Service Principal to the appropriate Management Group(s) and/or Subscription(s) in the Azure portal:
  - `Reader`
  - `Reader and Data Access`

Enter the **Tenant ID**, **Client ID**, and **Client Secret**.

Optionally, provide a **Handle Prefix** to be pre-pended to the names of connections created from this integration. This is optional but may be useful for organizational purposes, or to ensure the uniqueness of the generated connection handles.

Click the **Test Connection** button to verify that the credentials are configured correctly, then click **Next**.

Finally, select the [Permissions](/pipes/docs/tenants/connections#permissions).  

![](/images/docs/pipes/org-integrations-perms.png)

The permissions on this screen apply to the top-level folders and therefore to *all connections and folders* discovered by this integration.  If you want to assign permissions more granularly, on a per-subfolder or per-connection basis, select **No Permissions** at this time, and then manage the permissions on the connections and folders once they have been discovered.

Note also that **All Workspaces** will not only add permissions for the existing organization workspaces but will also allow access for any new workspaces that are created.

After you have made your selections, click **Create Integration**.  Pipes will begin discovering your subscriptions and management groups and creating folders and connections.


## Modifying the Azure Integration

After you have created an integration, you can change its **Handle**, **Handle Prefix**, or **Credentials**.  You can also change the **Permissions** and **Handle** individually for each child folder or connection.

*Modifying the integration after it has been created will potentially impact any workspaces that use its connections!*
- Changing the **Handle Prefix** will change the handles of all of its connections.
This means that the schema names will change in any workspace to which they are attached.  The schema names, in turn, impact the search path and aggregators that use wildcards.
- Discovery of subscriptions and management groups occurs using the supplied **Credentials**.  If changing the credentials affects access to these subscriptions and management groups that will be reflected in the folders and connections. For example, if the new credentials do not have access to some management groups or subscriptions that were visible to the previous credentials, then the corresponding folders and connections will be deleted and removed from any workspaces where they are attached.

To modify the integration, navigate to the **Integrations** page for the appropriate resource:
- To configure an Azure integration for your **Tenant**, click the double arrow button from the tenant switcher at the top of the Pipes console, select your tenant, and then select **Tenant Settings**. This option will only be visible in a custom tenant for which you are a [tenant owner](people#tenant-roles).  Once you've selected your tenant, go to the **Integrations** tab to manage the integrations for the tenant.
- To configure an Azure integration for your **Organization**, click the double arrow button from the organization switcher at the top of the page and select the organization from the dropdown.  Once you've selected your organization, go to the **Integrations** tab to manage the integrations for the organization.

You can change the **Credentials** or **Handle Prefix** from the **Config** tab.

![](/images/docs/pipes/org-integrations-azure-settings-config.png)

Make the desired changes and click **Save**.

You can modify the **Handle** from the **Advanced** tab.  

![](/images/docs/pipes/org-integrations-azure-settings-advanced.png)

Enter the new handle and click **Save**.

You can view the connection tree from the **Connections** tab.  Click on a connection or folder to view or change its properties. You can change the **Permissions** and **Handle** from its **Settings** tab.


## Deleting the Azure Integration

You can delete an integration from its **Advanced** page.

*If you delete an integration, all of its associated folders and connections will be deleted and removed from all workspaces.  This action is not reversible!*

Navigate to the **Integrations** page for the appropriate resource:
- To delete an Azure integration for your **Tenant**, click the double arrow button from the tenant switcher at the top of the Pipes console, select your tenant, and then select **Tenant Settings**. This option will only be visible in a custom tenant for which you are a [tenant owner](people#tenant-roles).  Once you've selected your tenant, go to the **Integrations** tab to manage the integrations for the tenant.
- To delete an Azure integration for your **Organization**, click the double arrow button from the organization switcher at the top of the page and select the organization from the dropdown.  Once you've selected your organization, go to the **Integrations** tab to manage the integrations for the organization.

Go to the **Advanced** page and click the **Delete Integration** button. 

![](/images/docs/pipes/org-integrations-azure-settings-advanced.png)

You will be asked to enter the handle to confirm deletion. 

![](/images/docs/pipes/org-integrations-azure-delete-confirm.png)

If you wish to *permanently delete the integration and all of its resources*, click **Delete**.

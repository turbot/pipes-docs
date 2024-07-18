---
title: AWS Integration
sidebar_label: AWS
---

# AWS Integration


The AWS Integration allows you to automatically import a connection folder hierarchy that mirrors your AWS Organization folder structure, with a connection folder for each AWS OU and a [connection](/pipes/docs/connections) for each account in your AWS organization.

The AWS integration will automatically keep the configuration up to date as your organization changes, adding, removing, and modifying connections and folders as accounts and OUs are created, deleted, or changed in your AWS Organization.




## Creating the AWS Integration

You can create an integration for a [tenant](/pipes/docs/tenants/) or an [organization]((/pipes/docs/organizations)), and where you create the integration affects the scope of the resources it creates; the resulting connections and folders can only be shared within the entity in which it was created.

| Level                        | Plan                       | Description
|------------------------------|----------------------------|----------------
| [Tenant](/pipes/docs/tenants) | [Enterprise](/pipes/docs/plans/enterprise) | Selectively share AWS connections and folders with any (or all) organization or workspace in the tenant.
| [Org](/pipes/docs/organizations) | [Team](/pipes/docs/plans/team) or [Enterprise](/pipes/docs/plans/enterprise)  | Selectively share AWS connections and folders with any (or all) workspace in the organization.


First, navigate to the **Integrations** page for the appropriate resource:
- To configure an AWS integration for your **Tenant**, click the double arrow button from the tenant switcher at the top of the Pipes console, select your tenant, and then select **Tenant Settings**. This option will only be visible in a custom tenant for which you are a [tenant owner](people#tenant-roles).  Once you've selected your tenant, go to the **Integrations** tab to manage the integrations for the tenant.
- To configure an AWS integration for your **Organization**, click the double arrow button from the organization switcher at the top of the page and select the organization from the dropdown.  Once you've selected your organization, go to the **Integrations** tab to manage the integrations for the organization.



![](/images/docs/integrations_blank.png)

Next, click the **New Integration** button. You will be asked to select an integration to create.

![](/images/docs/integrations_new_AWS.png)

Select **AWS** and click **Next**.

Provide a **Handle** for the integration.  This handle should be meaningful and must be unique for all integrations in the tenant (including any org-level integrations).


Configure the **Discovery Settings**, including the credentials that Pipes should use to discover the organization's resources.  These credentials need access to read the organizations data in the AWS Organizations master account.  You may either authenticate using a cross-account role (recommended) or an access key pair.

- To use a cross-account role, select **Cross-Account Role** from the **Access Mode** dropdown.  You will need to create a role in the account that has the correct trust policy and permissions.  You can do this manually, or Pipes can generate a Terraform or CloudFormation template for you to download and run.  Depending on your preference, follow the **Automatic Setup** or **Manual Setup** instructions, then enter the **Role ARN** and **External ID**.  Click the **Test Discovery** button to verify that the credentials are configured correctly, then click **Next**.

- To use a key pair, select **Access Key** from the **Access Mode** dropdown, enter the **Access Key** and **Secret Key** and click **Next**.

Next, configure the **Connection settings**.

Optionally, provide a **Handle Prefix** to be pre-pended to the names of connections created from this integration. This is optional but may be useful for organizational purposes, or to ensure the uniqueness of the generated connection handles.

Next, set up the trust relationship for the discovered accounts.  In order for Pipes to access the discovered accounts, a cross-account role must be created in each discovered account.  You can set these roles up manually, or Pipes can generate a CloudFormation StackSet to help automate the process. Depending on your preference, follow the **Automatic Setup** or **Manual Setup** instructions, then enter the **Role ARN** and **External ID**, and choose the **Regions** that you would like configured in the child connections.

If desired, you can set advanced options for the child connections.  These options will be inherited by all connections imported by the integration.  You can also set or change these options on a per-connection basis after the connections have been imported:
- **Default region**: This region will be used for calls to global APIs. Defaults to us-east-1 for commercial accounts, the closest region to Turbot Pipes, and us-gov-west-1 for GovCloud accounts.
- **Max retry attempts**: The maximum number of attempts (including the initial call)Turbot Pipes will make for failing API calls. Defaults to 9 and must be greater than or equal to 1.
- **Min error retry delay**: The minimum retry delay in milliseconds after which retries will be performed. Defaults to 25ms and must be greater than or equal to 1ms.
- **Ignore error codes**: List of AWS error codes to ignore for all queries. By default, common not found error codes are ignored and will still be ignored even if this option is not set.

Click the **Test Connection** button to verify that the credentials are configured correctly, then click **Next**.


Finally, select the [Permissions](#permissions) to assign to the root folder created from this AWS integration.  Note that you do not have to set the permissions now and you can change them later.

- **All Organizations and Workspaces**
- **Specific Organizations and Workspaces**
- **No Workspaces**

The permissions on this screen apply to the root folder, thus *all connections and folders* discovered by this integration.  If you want to assign permissions more granular, on a per-subfolder or per-connection basis, select **No Workspaces** at this time, and then manage the permissions on the connections and folders once they have been discovered.

Note also that **All** will not only add permissions for the existing identities and workspaces but will also allow access for any new connections and folders that are created when they are added to the AWS organization.

[screenshot...]

After you have made your selections, click **Create Integration**.  Pipes will begin discovering your accounts and OUs and creating folders and connections.


---------

## Modifying the AWS Integration

After you have created an integration, you can change its **Handle**, **Handle Prefix**, or **Credentials**.  You can also change the **Permissions** and **Handle** individually for each child folder or connection.

*Modifying the integration after it has been created will potentially impact any workspaces that use its connections!*
- Changing the **Handle Prefix** will change the handles of all of its connections.
This means that the schema names will change in any workspace to which they are attached.  The schema names, in turn, impact the search path and aggregators that use wildcards.
- Discovery of accounts and OUs occurs using the supplied **Credentials**.  If changing the credentials affects access to these accounts and OUs that will be reflected in the folders and connections. For example, if the new credentials do not have access to some OUs or accounts that were visible to the previous credentials, then the corresponding folders and connections will be deleted and removed from any workspaces where they are attached.

To modify the integration, navigate to the **Integrations** page for the appropriate resource:
- To configure an AWS integration for your **Tenant**, click the double arrow button from the tenant switcher at the top of the Pipes console, select your tenant, and then select **Tenant Settings**. This option will only be visible in a custom tenant for which you are a [tenant owner](people#tenant-roles).  Once you've selected your tenant, go to the **Integrations** tab to manage the integrations for the tenant.
- To configure an AWS integration for your **Organization**, click the double arrow button from the organization switcher at the top of the page and select the organization from the dropdown.  Once you've selected your organization, go to the **Integrations** tab to manage the integrations for the organization.


You can change the **Credentials** or **Handle Prefix** from the **Config** tab.  Make the desired changes and click **Save**.

You can modify the **Handle** from the **Advanced** tab.  Enter the new handle and click **Save**.

You can view the connection tree from the **Connections** tab.  Click on a connection or folder to view or change its properties. You can change the **Permissions** and **Handle** from its **Settings** tab.


## Deleting the AWS Integration

You can delete an integration from its **Advanced** page.

*If you delete an integration, all of its associated folders and connections will be deleted and removed from all workspaces.  This action is not reversible!*

Navigate to the **Integrations** page for the appropriate resource:
- To configure an AWS integration for your **Tenant**, click the double arrow button from the tenant switcher at the top of the Pipes console, select your tenant, and then select **Tenant Settings**. This option will only be visible in a custom tenant for which you are a [tenant owner](people#tenant-roles).  Once you've selected your tenant, go to the **Integrations** tab to manage the integrations for the tenant.
- To configure an AWS integration for your **Organization**, click the double arrow button from the organization switcher at the top of the page and select the organization from the dropdown.  Once you've selected your organization, go to the **Integrations** tab to manage the integrations for the organization.


Go to the **Advanced** page and click the **Delete Integration** button. You will be asked to enter the handle to confirm deletion.  If you wish to *permanently delete the integration and all of its resources*, click **Delete**.

----------


## Permissions
You can create an integration for a tenant or an organization, and where you create the integration affects the scope of the resources it creates; the resulting connections and folders can only be shared within the entity in which it was created.  When creating the integration, you can set **Permissions** for the connections and folders that it creates:
  - Tenant-level connections and folders can be shared with any identity or workspace within the tenant.
  - Org-level connections and folders can be shared with any workspace within the org, but not with other orgs.

When you grant permissions on a folder, all the connections that are members of that folder inherit the same permissions; granting access to a folder implicitly grants access to its connections.  Note that permissions are additive and can only be granted, not denied. If you grant permissions to an identity or workspace for a folder you cannot revoke access for these individual connections, only to the folder as a whole.

You can set permissions for folders and connections from their settings page. Navigate to the desired tenant or org and browse the **Connections** to find the resource you wish to manage.  Click the connection or folder.  From the **Settings** tab, select **Permissions**.  Select the desired permissions and click **Save**.

Note that setting permissions for a connection or folder does not attach its schema to the workspaces, it merely makes it visible to the workspaces so that [it may be attached](/pipes/docs/connections#adding-schemas).

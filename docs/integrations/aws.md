---
title: AWS Integration
sidebar_label: AWS
---

# AWS Integration

The AWS Integration allows you to automatically import a connection folder hierarchy that mirrors your AWS Organization folder structure, with a connection folder for each AWS OU and a [connection](/pipes/docs/workspaces/connections) for each account in your AWS organization.

The AWS integration will automatically keep the configuration up to date as your organization changes, adding, removing, and modifying connections and folders as accounts and OUs are created, deleted, or changed in your AWS Organization.


## Creating the AWS Integration

You can create an integration for a [tenant](/pipes/docs/accounts/tenant/) or an [organization](/pipes/docs/accounts/org), and where you create the integration affects the scope of the resources it creates; the resulting connections and folders can only be shared within the entity in which it was created.

| Level                        | Plan                       | Description
|------------------------------|----------------------------|----------------
| [Tenant](/pipes/docs/accounts/tenant) | [Enterprise](/pipes/docs/accounts/tenant#enterprise-plan) | Selectively share AWS connections and folders with any (or all) organization or workspace in the tenant.
| [Org](/pipes/docs/accounts/org) | [Team](/pipes/docs/accounts/org#team-plan) or [Enterprise](/pipes/docs/accounts/tenant#enterprise-plan)  | Selectively share AWS connections and folders with any (or all) workspace in the organization.


## Step 1: Navigate to the Integrations page

Navigate to the **Integrations** page for the appropriate resource:
- To configure an AWS integration for your **Tenant**, click the double arrow button from the tenant switcher at the top of the Pipes console, select your tenant, and then select **Tenant Settings**. This option will only be visible in a custom tenant for which you are a [tenant owner](/pipes/docs/accounts/tenant/people#tenant-roles).  Once you've selected your tenant, go to the **Integrations** tab to manage the integrations for the tenant.
- To configure an AWS integration for your **Organization**, click the double arrow button from the organization switcher at the top of the page and select the organization from the dropdown.  Once you've selected your organization, go to the **Integrations** tab to manage the integrations for the organization.

![](/images/docs/pipes/org-integrations-tab.png)

## Step 2: Create a new AWS integration

Next, click the **New Integration** button. You will be asked to select an integration to create.

![](/images/docs/pipes/org-integrations-new-aws.png)

Select **AWS** and click **Next**.

Provide a **Handle** for the integration.  

![](/images/docs/pipes/org-integrations-aws-handle.png)

This handle should be meaningful and must be unique for all integrations in the tenant (including any org-level integrations).  Click **Next**.

## Step 3: Setup Access to Your Organization Management Account

In this step, Pipes uses:

- **`External ID`** ensures secure access between Pipes and AWS accounts. Refer to AWS documentation on [Access to AWS accounts owned by third parties](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_roles_common-scenarios_third-party.html) for further information.
- **`IAM Role with Cross Account Trust`** allows Turbot Pipes to access resources across accounts. For additional context, see AWS's guide on [Cross-account resource access in IAM](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies-cross-account-resource-access.html).

![Cross Account Trust](/images/docs/pipes/integrations/aws-setup-org-access.png)

### Cross Account Trust

The IAM role must grant cross-account access for the Turbot Pipes main AWS account to assume into your AWS account.

- Turbot Pipes customers, you must allow the Turbot Pipes AWS Account ID: `316881668097`

### External ID Considerations

The External ID is a security measure that helps prevent unauthorized access. It consists of two parts:
- Your organization ID `o_cugqnt0sb890gkker123` (automatically added)
- A random 8-character string (you can customize this)

This combination ensures that only authorized users can assume the role.

### Required Permissions to Grant

The IAM role needs the following permissions:

- `arn:aws:iam::aws:policy/ReadOnlyAccess`

Now as next steps:

- Enter the IAM Role Name.
- Provide External ID.

## Step 4: Create IAM Role in Management Account or Delegated Account

You can create the IAM role beforehand or during the importing process in the Pipes integration UI. However, it is recommended to create the IAM roles prior to initiating the import process. This ensures that the required IAM role is ready as part of the prerequisites.

To create the IAM role:

- Download the CloudFormation template file, which will be updated with the two values you provided (i.e., Role Name and External ID) in previous [Step 3](#step-3-setup-access-to-your-organization-management-account).

## Step 5: Enter the IAM Role ARN

- Enter the IAM Role ARN obtained after the Role is created.
- Click the Test Connection button to verify that the credentials are configured correctly.
- Click **Next**.

## Step 6: Setup Access to Your Member Accounts

This step follows a similar process as **Step 4**.

![Setup Access to Your Member Accounts](/images/docs/pipes/integrations/aws-setup-member-accounts.png)

### Create IAM Role in Member Accounts

You can create the required IAM role beforehand or during the importing process in the Pipes integration UI. However, it is recommended to create the IAM roles **prior to initiating the import process** to ensure the required IAM role is ready.

To create the IAM role:

**Download the CloudFormation Template**:
   The template will be pre-configured with the values you provided (i.e., `Role Name` and `External ID`).

**Execute the CloudFormation Template**:
   Use [CloudFormation StackSets](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/stacksets-getting-started-create-self-managed.html#stacksets-getting-started-create-self-managed-console) in the AWS management or delegated account to deploy the template across member accounts. This creates the required IAM role in each member account.

## Step 7: Configure the Connection Settings

Optionally, provide a **Handle Prefix** to be pre-pended to the names of connections created from this integration. This is optional but may be useful for organizational purposes or to ensure the uniqueness of the generated connection handles.

Choose the **Regions** that you would like configured in the child connections.  

If desired, you can set advanced options for the child connections.  

![](/images/docs/pipes/org-integrations-aws-setup-advanced.png)

These options will be inherited by all connections imported by the integration.  You can also set or change these options on a per-connection basis after the connections have been imported.


Click the **Test Connection** button to verify that the credentials are configured correctly, then click **Next**.


Finally, select the [Permissions](/pipes/docs/accounts/tenant/connections#permissions).  

![](/images/docs/pipes/org-integrations-perms.png)


The permissions on this screen apply to the top-level folders and, therefore, to *all connections and folders* discovered by this integration.  If you want to assign permissions more granularly, on a per-subfolder or per-connection basis, select **No Permissions** at this time, and then manage the permissions on the connections and folders once they have been discovered.

Note also that **All Workspaces** will not only add permissions for the existing organization workspaces but will also allow access for any new workspaces that are created.

After you have made your selections, click **Create Integration**.  Pipes will begin discovering your accounts and OUs and creating folders and connections.


## Modifying the AWS Integration

After you have created an integration, you can change its **Handle**, **Handle Prefix**, or **Credentials**.  You can also change the **Permissions** and **Handle** individually for each child folder or connection.

*Modifying the integration after it has been created will potentially impact any workspaces that use its connections!*
- Changing the **Handle Prefix** will change the handles of all of its connections.
This means that the schema names will change in any workspace to which they are attached.  The schema names, in turn, impact the search path and aggregators that use wildcards.
- Discovery of accounts and OUs occurs using the supplied **Credentials**.  If changing the credentials affects access to these accounts and OUs, that will be reflected in the folders and connections. For example, if the new credentials do not have access to some OUs or accounts that were visible to the previous credentials, then the corresponding folders and connections will be deleted and removed from any workspaces where they are attached.

To modify the integration, navigate to the **Integrations** page for the appropriate resource:
- To configure an AWS integration for your **Tenant**, click the double arrow button from the tenant switcher at the top of the Pipes console, select your tenant, and then select **Tenant Settings**. This option will only be visible in a custom tenant for which you are a [tenant owner](/pipes/docs/accounts/tenant/people#tenant-roles).  Once you've selected your tenant, go to the **Integrations** tab to manage the integrations for the tenant.
- To configure an AWS integration for your **Organization**, click the double arrow button from the organization switcher at the top of the page and select the organization from the dropdown.  Once you've selected your organization, go to the **Integrations** tab to manage the integrations for the organization.


In the list of integrations, click the gear icon next to the integration that you want to modify.

You can change credentials used for discovery in the **Discovery Settings** section of the **Config** tab.
![](/images/docs/pipes/org-integrations-aws-settings-config-discovery.png)

You can also change the **Connection Settings** from the **Config** tab, including the **Handle Prefix**, **Regions**, the connection credentials, and the **Advanced Options**,

![](/images/docs/pipes/org-integrations-aws-settings-config-connection.png)

Make the desired changes and click **Save**.


You can modify the **Handle** from the **Advanced** tab.

![](/images/docs/pipes/org-integrations-aws-settings-advanced.png)

Enter the new handle and click **Save**.

You can view the connection tree from the **Connections** tab.  Click on a connection or folder to view or change its properties. You can change the **Permissions** and **Handle** from its **Settings** tab.


## Deleting the AWS Integration

You can delete an integration from its **Advanced** page.

*If you delete an integration, all of its associated folders and connections will be deleted and removed from all workspaces.  This action is not reversible!*

Navigate to the **Integrations** page for the appropriate resource:
- To delete an AWS integration for your **Tenant**, click the double arrow button from the tenant switcher at the top of the Pipes console, select your tenant, and then select **Tenant Settings**. This option will only be visible in a custom tenant for which you are a [tenant owner](/pipes/docs/accounts/tenant/people#tenant-roles).  Once you've selected your tenant, go to the **Integrations** tab to manage the integrations for the tenant.
- To delete an AWS integration for your **Organization**, click the double arrow button from the organization switcher at the top of the page and select the organization from the dropdown.  Once you've selected your organization, go to the **Integrations** tab to manage the integrations for the organization.


Go to the **Advanced** page and click the **Delete Integration** button. 

![](/images/docs/pipes/org-integrations-aws-settings-advanced.png)

You will be asked to enter the handle to confirm deletion. 

![](/images/docs/pipes/org-integrations-aws-delete-confirm.png)

If you wish to *permanently delete the integration and all of its resources*, click **Delete**.
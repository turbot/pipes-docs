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

## Navigate to the Integrations page

Navigate to the **Integrations** page for the appropriate resource:
- To configure an AWS integration for your **Tenant**, click the double arrow button from the tenant switcher at the top of the Pipes console, select your tenant, and then select **Tenant Settings**. This option will only be visible in a custom tenant for which you are a [tenant owner](/pipes/docs/accounts/tenant/people#tenant-roles).  Once you've selected your tenant, go to the **Integrations** tab to manage the integrations for the tenant.
- To configure an AWS integration for your **Organization**, click the double arrow button from the organization switcher at the top of the page and select the organization from the dropdown.  Once you've selected your organization, go to the **Integrations** tab to manage the integrations for the organization.

![](/images/docs/pipes/org-integrations-tab.png)

## Choose AWS integration type

Click the **New Integration** button to create a new integration.

![](/images/docs/pipes/org-integrations-new-aws.png)

In the integration selection screen, you'll see several integration options:
- AWS - Discover your AWS organization and automatically create aggregators and connections
- Azure - Discover your Azure tenant and automatically create aggregators and connections
- GCP - Discover your GCP organization and automatically create aggregators and connections
- GitHub - Access to your private/public GitHub repositories to find and install custom mods
- GitLab - Access to your private/public GitLab projects to find and install custom mods
- Slack - Access to your Slack workspace and send notifications to specified channels

Select **AWS** and click **Next**.

## Choose a handle

Provide a unique handle for the integration. This handle must be unique for all integrations in the tenant (including any org-level integrations).

![](/images/docs/pipes/org-integrations-aws-handle.png)

Enter a handle in the input field (for example, "aws-integration") and click **Next**.

## Configure discovery settings

Pipes needs read-only access to your AWS Organization so it can enumerate all accounts and OUs under your management (or delegated) account. In this step, you'll create an IAM role in your AWS Organization management account.

![Setup Access to Your Organization](/images/docs/pipes/integrations/aws-setup-discovery-settings.png)

Pipes uses the following security measures:

1. **Role Name**: Enter a name for the IAM role that will be created in your AWS Organization management account (default: `turbot_pipes`).

2. **External ID**: A security measure that helps prevent unauthorized access. It consists of two parts:
   - Your organization ID (automatically added)
   - A random 8-character alphanumeric string (you can customize this)

This combination ensures that only authorized users can assume the role.

### Deploy the Role

You have two options to create the IAM role:

- **Terraform Plan**: Download and run the Terraform plan to create the IAM role
- **CloudFormation Template**: Download and run the CloudFormation template to create the IAM role

Alternatively, you can create the role manually with your preferred settings by following the [manual setup guide](#manual-setup-guide).
After creating the role, enter the full ARN of the newly created role in the **Role ARN** field, and click **Next**.

## Configure connection settings

In this step, you'll configure settings for the connections that will be created by this integration.

### Setup access to your member accounts

Pipes requires an IAM role in each AWS account under your organization so it can perform the integration tasks you've enabled.

![Setup Access to Your Member Accounts](/images/docs/pipes/integrations/aws-setup-connection-settings.png)

#### Create Roles

Download and run the CloudFormation StackSet to create the IAM role in the member accounts:

1. Click the **CloudFormation StackSet** button to download the template
2. Use this template to create the required IAM role across all member accounts

Alternatively, you can create the role manually in the accounts with your preferred settings by following the [manual setup guide](#manual-setup-guide).

1. **Handle Prefix** (Optional): This will be prepended to connections/aggregators created from this integration. Helps avoid conflicting handles.

2. **Choose your regions**: Select the AWS regions you want to configure in the child connections.
   - By default, "(All regions)" is selected
   - Select specific regions for better performance

3. **Advanced options** (Optional): Click to configure additional connection settings that will be inherited by all connections imported by the integration.
![Connection Settings](/images/docs/pipes/org-integrations-aws-setup-advanced.png)

After configuring the settings, click **Test Connection** to verify the credentials are configured correctly, then click **Next**.

## Set permissions

Choose workspaces that should have permissions to the root connection folder(s) created from this AWS integration.

![Set Permissions](/images/docs/pipes/org-integrations-perms.png)

You have three options:
- **All workspaces**: Grant access to all current and future workspaces
- **Specific workspaces**: Select individual workspaces to grant access
- **No permissions**: Don't set any permissions at this level (you can configure them later)

The permissions on this screen apply to the top-level folders and, therefore, to *all connections and folders* discovered by this integration. If you want to assign permissions more granularly, on a per-subfolder or per-connection basis, select **No Permissions** at this time, and then manage the permissions on the connections and folders once they have been discovered.

After making your selections, click **Create Integration**. Pipes will begin discovering your accounts and OUs and creating folders and connections.

## Manual Setup Guide

### 1. Create Required IAM Roles

You'll need to create two IAM roles:

1. **Discovery Role** (For example, `turbot_pipes_discovery`): Used to discover AWS accounts and OUs
2. **Connection Role** (For example, `turbot_pipes_connection`): Used for AWS resource access and queries

#### Role creation CloudFormation Template for Management Account
```yaml
AWSTemplateFormatVersion: '2010-09-09'
Resources:
  TurbotPipesRole:
    Type: AWS::IAM::Role
    Properties:
      RoleName: ${YOUR_ROLE_NAME}
      AssumeRolePolicyDocument:
        Version: '2012-10-17'
        Statement:
          - Effect: Allow
            Principal:
              AWS:
                - arn:aws:iam::316881668097:root
            Action:
              - sts:AssumeRole
            Condition:
              StringEquals:
                sts:ExternalId: ${YOUR_EXTERNAL_ID}
      ManagedPolicyArns:
        - arn:aws:iam::aws:policy/ReadOnlyAccess
```

#### Role creation CloudFormation StackSet for Member Accounts
```yaml
AWSTemplateFormatVersion: 2010-09-09
Description: Turbot Pipes AWS integration role setup stack.

Parameters:
  RoleName:
    Type: String
    Default: ${YOUR_ROLE_NAME}
    Description: The IAM role name to create in each account.

Resources:
  TurbotPipesRole:
    Type: AWS::IAM::Role
    Properties:
      RoleName: !Ref RoleName
      AssumeRolePolicyDocument:
        Version: '2012-10-17'
        Statement:
          - Effect: Allow
            Principal:
              AWS:
                - arn:aws:iam::316881668097:root
            Action:
              - sts:AssumeRole
            Condition:
              StringEquals:
                sts:ExternalId: ${YOUR_EXTERNAL_ID}
      ManagedPolicyArns:
        - arn:aws:iam::aws:policy/ReadOnlyAccess
```

### 2. Create the Integration via Terraform

You can create the integration using Terraform resources. Choose the appropriate resource based on whether you're creating the integration at the organization or tenant level:

#### Organization Integration
```hcl
resource "pipes_organization_integration" "aws" {
  org_handle = "your-org-handle"
  type       = "aws"
  handle     = "awsi"
  config = {
    permitted_external_id_identifiers = [
      "${YOUR_ORGANIZATION_ID}"
    ]
    discovery_mode        = "role"
    discovery_role_arn    = "${YOUR_DISCOVERY_ROLE_ARN}"
    discovery_role_name   = "${YOUR_DISCOVERY_ROLE_NAME}"
    discovery_external_id = "${YOUR_DISCOVERY_EXTERNAL_ID}"
    discovery_access_key  = ""
    discovery_secret_key  = ""
    handle_prefix         = ""
    role_name            = "${YOUR_CONNECTION_ROLE_NAME}"
    external_id          = "${YOUR_CONNECTION_EXTERNAL_ID}"
    regions              = ["*"]
    permissions = [
      {
        identity_handle = "${YOUR_ORGANIZATION_HANDLE}"
      }
    ]
  }
}
```

#### Tenant Integration
```hcl
resource "pipes_tenant_integration" "aws" {
  tenant_handle = "your-tenant-handle"
  type         = "aws"
  handle       = "awsi"
  config = {
    permitted_external_id_identifiers = [
      "${YOUR_ORGANIZATION_ID}"
    ]
    discovery_mode        = "role"
    discovery_role_arn    = "${YOUR_DISCOVERY_ROLE_ARN}"
    discovery_role_name   = "${YOUR_DISCOVERY_ROLE_NAME}"
    discovery_external_id = "${YOUR_DISCOVERY_EXTERNAL_ID}"
    discovery_access_key  = ""
    discovery_secret_key  = ""
    handle_prefix         = ""
    role_name            = "${YOUR_CONNECTION_ROLE_NAME}"
    external_id          = "${YOUR_CONNECTION_EXTERNAL_ID}"
    regions              = ["*"]
    permissions = [
      {
        identity_handle = "${YOUR_ORGANIZATION_HANDLE}"
      }
    ]
  }
}
```

### Required Configuration Values

- `discovery_role_arn`: The ARN of your discovery IAM role
- `discovery_role_name`: Name of the discovery role (e.g., `turbot_pipes_discovery`)
- `discovery_external_id`: Your external ID for discovery role
- `external_id`: Your external ID for connection role
- `handle`: Unique identifier for this integration
- `identity_handle`: Your organization's handle in Pipes

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

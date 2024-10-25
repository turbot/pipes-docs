---
title: Advanced
sidebar_label: Advanced
---

# Advanced Settings
To manage your organization's advanced settings, click the double arrow button from the navigation at the top of the page, select the organization from the dropdown, and then go to the **Advanced** tab.


## Org Profile

On the **Advanced** tab for your organization, click **Org Profile** from the left-hand menu to manage your profile data. You can modify your organization's **Avatar**, **Display Name** or **Handle**.

### Updating Your Avatar
You can modify your organization's Avatar at any time. Click the avatar image to change it. You can click **Reset** to change back to the default generated image.


### Changing your Display Name

You can modify the display name from the **Org Profile** section.  Enter your preferred name and click **Save**


### Updating Your Org Handle
You can update your organization's handle at any time. Note, however, that your workspace DNS names all contain your organization handle; changing it will result in changing the DNS name for ALL of your organization's workspaces.


## Usage 

Pipes provides **Usage** information to help you view and understand your workspace usage, including used storage, compute time, and the number of users in your organization. 

On the **Advanced** tab for your organization, click **Usage** from the
left-hand menu to view [usage information](/pipes/docs/accounts/org/usage) for your organization.

## Billing 

The **Billing** page provides visibility into the current state of billing for your organization. 

On the **Advanced** tab for your organization, click **Billing** from the
left-hand menu to view [billing information](/pipes/docs/accounts/org/billing) for your organization.  The billing page will only be available if your organization was purchased on the [Team Plan](/pipes/docs/accounts/org#team-plan).



## Reset Authentication

Once users have been added to your organization, they will be able to
authenticate against it according to the permissions they were granted. They can authenticate using either temporary tokens issued via console or [CLI login](https://steampipe.io/docs/reference/cli/login#steampipe-login), or with [tokens](/pipes/docs/accounts/developer/advanced#tokens) managed via their user profile settings.

If you wish to reset authentication in your organization for any currently issued tokens, you can do so by going to the **Advanced** page for your organization and then clicking **Authentication** from the left-hand menu.  Click the
`Reset authentication` button to reset authentication for all existing
temporary and user tokens.

This will immediately remove console access to the organization for all users, prompting them to log in again. Any users who wish to access your organization via the API will also be required to generate a new user [token](/pipes/docs/accounts/developer/advanced#tokens).

<img src="/images/docs/pipes/cloud-organization-reset-authentication.png" width="400pt"/>
<br />

## Deleting an Organization

To delete an organization, select the double arrow button from the navigation at the top of the page and select the organization. Go to the **Advanced** tab and click **Org Profile**. Click **Delete Organization**. You will be prompted to confirm deletion. Enter the organization handle and click **Delete**.

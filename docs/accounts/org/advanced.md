---
title: Advanced
sidebar_label: Advanced
---

# Advanced Settings
To manage your organization's advanced settings, click the double arrow button from the navigation at the top of the page, select the organization from the dropdown, and then go to the **Advanced** tab.


## Org Profile

On the **Advanced** tab for your organization, click **Org Profile** from the left hand menu to manage your profile data. You can modify your organization's **Avatar**, **Display Name** or **Handle**.

You can update your organization handle at any time. Note, however, that your workspace DNS names all contain your organization handle; changing it will result in changing the DNS name for ALL of your organization's workspaces.

## Usage 

On the **Advanced** tab for your organization, click **Usage** from the
left hand menu to view [usage information](/pipes/docs/accounts/org/usage) for to your organization.


## Reset Authentication

Once users have been added to your organization, they will be able to
authenticate against it according to the permissions they were granted. They can authenticate using either temporary tokens issued via console or [CLI login](https://steampipe.io/docs/reference/cli/login#steampipe-login), or with [tokens](/pipes/docs/da-settings#tokens) managed via their user profile settings.

If you wish to reset authentication in your organization for any currently issued tokens, you can do so by going to the **Advanced** page for your organization, then clicking **Authentication** from the left hand menu.  Click the
`Reset authentication` button to reset authentication for all existing
temporary and user tokens.

This will immediately remove console access to the organization for all users, prompting them to log in again. Any users who wish the access your organization via the API will also be required to generate a new user [token](/pipes/docs/da-settings#tokens).

<img src="/images/docs/pipes/cloud-organization-reset-authentication.png" width="400pt"/>
<br />

## Deleting an Organization

To delete an organization, select the double arrow button from the navigation at the top of the page and select the organization. Go to the **Advanced** tab and click **Org Profile**. Click **Delete Organization**. You will be prompted to confirm deletion. Enter the organization handle and click **Delete**.

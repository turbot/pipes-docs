---
title: Settings
sidebar_label: Settings

---

# Organization Settings
To manage your organization's settings, click the double arrow button from the navigation at the top of the page, select the organization from the dropdown, and then select **Settings** from the menu on the left.


## Profile

On the **Settings** page for your organization, click **Profile** from the left
hand menu to manage your profile data. You can modify your organization's
**Display Name** or **Avatar URL**.

## Usage 

On the **Settings** page for your organization click **Usage** from the
left hand menu to view [usage information](/pipes/docs/usage) for to your organization.


## Audit Log

On the **Settings** page for your organization click **Audit Log** from the
left hand menu to view the [audit log](/pipes/docs/activity#audit-log) of API activity associated to your organization.


## Advanced

The **Advanced Settings** page for your organization allows you to change your handle, reset all authentication tokens, and delete the organization. These are potentially disruptive activities.  Proceed carefully when changing these settings!

### Updating Your Organization Handle

You can update your organization handle at any time. Note, however, that your
workspace DNS names all contain your organization handle; changing it will
result in changing the DNS name for ALL of your organization's workspaces.

On the **Settings** page for your user, click **Advanced** from the left hand
menu. Enter your new handle and click **Save**.


### Reset Authentication

Once users have been added to your organization, they will be able to
authenticate against it according to the permissions they were granted. This can
be using either temporary tokens issued via console or
[CLI login](https://steampipe.io/docs/reference/cli/login#steampipe-login), or with
[tokens](/pipes/docs/da-settings#tokens) managed via their user profile settings.

If you wish to reset authentication in your organization for any currently
issued tokens, you can do so by going to the **Settings** page for your
organization, then clicking **Advanced** from the left hand menu. From here
you'll find a `Reset authentication` section. Clicking the
`Reset authentication` button will reset authentication for all existing
temporary and user tokens.

This will immediately remove console access to the organization for all users,
prompting them to log in again. Any users who wish the access your organization
via the API will also be required to generate a new user
[token](/pipes/docs/da-settings#tokens).

<img src="/images/docs/pipes/cloud-organization-reset-authentication.png" width="400pt"/>
<br />

### Deleting Organizations

To delete an organization, select the double arrow button from the navigation at
the top of the page and select the organization. Go to the **Settings** tab and
click **Advanced**. Click **Delete Organization**. You will be prompted to
confirm deletion. Enter the organization handle and click **Delete**.

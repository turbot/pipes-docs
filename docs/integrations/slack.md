---
title: Slack Integration
sidebar_label: Slack
---

# Slack Integration

The Slack Integration allows Turbot Pipes to send notifications to specified Slack channels.  Once the Slack integration has been configured, you can configure [notifiers](/pipes/docs/workspaces/notifiers) to send messages to your Slack workspace.




## Creating the Slack Integration


You can create an integration for a [tenant](/pipes/docs/accounts/tenant/) or an [organization](/pipes/docs/accounts/org), and where you create the integration affects the scope where it can be used; the resulting integration can only be added to notifiers within the entity in which it was created.

| Level                        | Plan                       | Description
|------------------------------|----------------------------|----------------
| [Tenant](/pipes/docs/accounts/tenant) | [Enterprise](/pipes/docs/accounts/tenant#enterprise-plan) | The Integration is available to any notifier in any organization or workspace in the tenant.
| [Org](/pipes/docs/accounts/org) | [Team](/pipes/docs/accounts/org#team-plan) or [Enterprise](/pipes/docs/accounts/tenant#enterprise-plan)  |  The Integration is available to any notifier in any workspace in the organization.
| [User (Developer Account)](/pipes/docs/accounts/developer) | any | The Integration is available to any notifier in any workspace in the account.


First, navigate to the **Integrations** page for the appropriate resource:
- To configure a Slack integration for your **Tenant**, click the double arrow button from the tenant switcher at the top of the Pipes console, select your tenant, and then select **Tenant Settings**. This option will only be visible in a custom tenant for which you are a [tenant owner](/pipes/docs/accounts/tenant/people#tenant-roles).  Once you've selected your tenant, go to the **Integrations** tab to manage the integrations for the tenant.
- To configure a Slack integration for your **Organization**, click the double arrow button from the organization switcher at the top of the page and select the organization from the dropdown.  Once you've selected your organization, go to the **Integrations** tab to manage the integrations for the organization.


![](/images/docs/pipes/org-integrations-tab.png)

Next, click the **New Integration** button. You will be asked to select an integration to create.

![](/images/docs/pipes/org-integrations-new-slack.png)

Select **Slack** and click **Next**.

![](/images/docs/pipes/org-integrations-slack-setup.png)

Provide a **Handle** for the integration.  This handle should be meaningful and must be unique for all integrations in the tenant (including any org-level integrations).  Click **Create Integration**.

You will be prompted to grant permission to access the Slack workspace.  If you are a member of multiple workspaces, you can select a Slack workspace from the select box at the top right of the screen.  After selecting the workspace, select a default **channel** for the integration.  Review the permissions and click **Allow**.


![](/images/docs/pipes/slack_oauth_perms.png)


> [!IMPORTANT]  Note:  After the Slack integration has been created and the app has been added to your Slack workspace, you must [add the integration to any channel](https://slack.com/help/articles/201980108-Add-people-to-a-channel) to which you wish to send messages (you can use the `/invite @turbot-pipes` slash command)!

## Modifying the Slack Integration


After you have created an integration, you can change its **Handle**.

Navigate to the **Integrations** page for the appropriate resource:
- To configure a Slack integration for your **Tenant**, click the double arrow button from the tenant switcher at the top of the Pipes console, select your tenant, and then select **Tenant Settings**. This option will only be visible in a custom tenant for which you are a [tenant owner](/pipes/docs/accounts/tenant/people#tenant-roles).  Once you've selected your tenant, go to the **Integrations** tab to manage the integrations for the tenant.
- To configure a Slack integration for your **Organization**, click the double arrow button from the organization switcher at the top of the page and select the organization from the dropdown.  Once you've selected your organization, go to the **Integrations** tab to manage the integrations for the organization.
- To configure a Slack integration for your **Developer Account**, click the double arrow button from the navigation at the top of the page, select your account from the dropdown, and then select **Settings** from the menu on the left.  On the organization settings page, select **Integrations**.

You can modify the **Handle** from the **Advanced** tab.  Enter the new handle and click **Save**.


## Deleting the Slack Integration


You can delete an integration from its **Advanced** page.

Navigate to the **Integrations** page for the appropriate resource:
- To configure a Slack integration for your **Tenant**, click the double arrow button from the tenant switcher at the top of the Pipes console, select your tenant, and then select **Tenant Settings**. This option will only be visible in a custom tenant for which you are a [tenant owner](/pipes/docs/accounts/tenant/people#tenant-roles).  Once you've selected your tenant, go to the **Integrations** tab to manage the integrations for the tenant.
- To configure a Slack integration for your **Organization**, click the double arrow button from the organization switcher at the top of the page and select the organization from the dropdown.  Once you've selected your organization, go to the **Integrations** tab to manage the integrations for the organization.
- To configure a Slack integration for your **Developer Account**, click the double arrow button from the navigation at the top of the page, select your account from the dropdown, and then select **Settings** from the menu on the left.  On the organization settings page, select **Integrations**.

Go to the **Advanced** page and click the **Delete Integration** button. You will be asked to enter the handle to confirm deletion.  If you wish to *permanently delete the integration and all of its resources*, click **Delete**.


---
title: GitLab Integration
sidebar_label: GitLab
---


# GitLab Integration

The GitLab Integration allows Turbot Pipes access to your GitLab projects to be able to search and install custom mods from private and public projects.

Once a GitLab integration has been added, you will be able to browse and install both private and public mods from the projects in scope and constrain them by either a semantic version constraint or branch. Pipes will detect changes to the source repository and automatically synchronize these changes to your workspaces!


## Creating the GitLab Integration

You can create an integration for a tenant or an identity (organization or developer account). Where you create the integration affects the scope of the resources it creates; the resulting mods are only visible within the entity in which it was created.

| Level                        | Plan                       | Description
|------------------------------|----------------------------|----------------
| [Tenant](/pipes/docs/accounts/tenant) | [Enterprise](/pipes/docs/accounts/tenant#enterprise-plan) | Mods are available to all workspaces in the tenant.
| [Org](/pipes/docs/accounts/org) | [Team](/pipes/docs/accounts/org#team-plan) or [Enterprise](/pipes/docs/accounts/tenant#enterprise-plan)  | Mods are available to all workspaces in the organization.
| [User (Developer Account)](/pipes/docs/accounts/developer) | any | Mods are available to all workspaces in the account.

First, navigate to the **Integrations** page for the appropriate resource:
- To configure a GitLab integration for your **Developer Account**, click the double arrow button from the navigation at the top of the page, select your account from the dropdown, and then select the **Integrations** tab to manage integrations for your account.
- To configure a GitLab integration for your **Organization**, click the double arrow button from the organization switcher at the top of the page and select the organization from the dropdown. Once you've selected your organization, go to the **Integrations** tab to manage the integrations for the organization.
- To configure a GitLab integration for your **Tenant**, click the double arrow button from the tenant switcher at the top of the Pipes console, select your tenant, and then select **Tenant Settings**. This option will only be visible in a custom tenant for which you are a [tenant owner](/pipes/docs/accounts/tenant/people#tenant-roles).  Once you've selected your tenant, go to the **Integrations** tab to manage the integrations for the tenant.

Next, click the **New Integration** button. You will be asked to select the type of integration to be created.

![](/images/docs/pipes/integrations_new_gitlab.png)

Select **GitLab** and click **Next**.

GitLab Integration configuration management form shows up. Enter the following information:
- **Handle** for the integration. This handle should be meaningful and must be unique for all integrations in the tenant (including any org-level integrations).
- **Host** for your GitLab installation which defaults to **gitlab.com**.
- **Token** to be used by Pipes to discover projects. Please note that the token must be granted `api` scope which is required to create and manage webhooks that enables Pipes to keep the mods managed by the integration up-to-date. Pipes supports [user](https://docs.gitlab.com/ee/user/profile/personal_access_tokens.html), [group](https://docs.gitlab.com/ee/user/group/settings/group_access_tokens.html) or [project](https://docs.gitlab.com/ee/user/project/settings/project_access_tokens.html) access tokens.
- **Token Scope** is an optional section which allows you to further scope a token down to a GitLab `group` / `project`. The following cases require you to configure this section:
    - Using a **Personal Access Token** you need to mention the group / project where Pipes will setup the webhook. 
        - Enter the group path in the **Group scope** field if you want to track all projects in the group and its sub-groups.
        - Enter the project path in the **Project** field if you want to track only a single project.
    - Using a **Group Access Token** and you want to further scope the webhook creation down to a sub-group / project.
        - Enter the sub-group path in the **Group scope** field if you want to tracj all projects in the sub-group and its descendants.
        - Enter the project path in the **Project** field if you want to track only a single project.

![](/images/docs/pipes/integrations_gitlab_config.png)

Click on **Test** to verify whether your configuration is accurate before creating the integration. Click on **Create** after entering the appropriate information.

After clicking on **Create**, Pipes will validate the configuration and setup the necessary webhook at the desired level. You will then be re-directed back to the integration list page with the new GitLab integration setup and ready for usage.

---------

## Modifying the GitLab Integration

After you have created a GitLab integration, you are only allowed to change its **Handle** and **Access Token**.

Navigate to the **Integrations** page for the appropriate resource:
- To configure a GitLab integration for your **Developer Account**, click the double arrow button from the navigation at the top of the page, select your account from the dropdown, and then select the **Integrations** tab to manage integrations for your account.
- To configure a GitLab integration for your **Organization**, click the double arrow button from the organization switcher at the top of the page and select the organization from the dropdown. Once you've selected your organization, go to the **Integrations** tab to manage the integrations for the organization.
- To configure a GitLab integration for your **Tenant**, click the double arrow button from the tenant switcher at the top of the Pipes console, select your tenant, and then select **Tenant Settings**. This option will only be visible in a custom tenant for which you are a [tenant owner](/pipes/docs/accounts/tenant/people#tenant-roles).  Once you've selected your tenant, go to the **Integrations** tab to manage the integrations for the tenant.

Click on the appropriate GitLab integration which you want to modify.
- **Token** can be modified in the **Config** tab.
- **Handle** can be edited from the **Advanced** tab.


## Deleting the GitLab Integration

You can delete an integration from its **Advanced** page.

*If you delete a GitLab integration, all of its associated mods will be removed from all workspaces the next time they are rebooted.  This action is not reversible!*

Navigate to the **Integrations** page for the appropriate resource:
- To configure a GitLab integration for your **Developer Account**, click the double arrow button from the navigation at the top of the page, select your account from the dropdown, and then select the **Integrations** tab to manage integrations for your account.
- To configure a GitLab integration for your **Organization**, click the double arrow button from the organization switcher at the top of the page and select the organization from the dropdown. Once you've selected your organization, go to the **Integrations** tab to manage the integrations for the organization.
- To configure a GitLab integration for your **Tenant**, click the double arrow button from the tenant switcher at the top of the Pipes console, select your tenant, and then select **Tenant Settings**. This option will only be visible in a custom tenant for which you are a [tenant owner](/pipes/docs/accounts/tenant/people#tenant-roles).  Once you've selected your tenant, go to the **Integrations** tab to manage the integrations for the tenant.

Click on the appropriate GitLab integration which you want to delete. Go to the **Advanced** page and click the **Delete Integration** button. You will be asked to enter the handle to confirm deletion.  If you wish to *permanently delete the integration and all of its resources*, click **Delete**.
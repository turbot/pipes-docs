---
title: Notifiers
sidebar_label: Notifiers
---

# Notifiers


Pipelines may need to send notification messages or requests for input.  You may want to route these notifications to multiple users, groups, or channels, perhaps via more than one delivery mechanism. For instance, you may want to request approval via [Slack](/pipes/docs/integrations/slack) and email.  Mods can send these messages to a **notifier**, which provides a way for the mod to send the message in a standard way, without needing to be aware of the details of the particular delivery channels or destinations.

The [notifier](https://flowpipe.io/docs/reference/config-files/notifier) allows you to define a list of [integrations](/pipes/docs/integrations/) to send notifications to.  Each notifier contains a list of integrations and related settings used to send and receive data to one or more integrations.

You can manages your workspace's notifiers from the **Notifiers** tab on your workspace.

![](/images/docs/pipes/notifiers_list.png)


## Default Notifier

Many [mods use the default notifier](https://flowpipe.io/docs/reference/config-files/notifier#using-notifiers-in-mods) by default, but allow you to override it via a [variable](https://flowpipe.io/docs/flowpipe-hcl/variable) or [param](https://flowpipe.io/docs/flowpipe-hcl/pipeline#parameters). 

Pipes includes a built-in notifier named `workspace_admins` that is configured to send email to the [Workspace Owners](/pipes/docs/workspaces/people).  This notifier is configured as the default notifier so that
it works out of the box with no configuration necessary.

If you would prefer to use a different default notifier in your workspace, you can do so;
Pipes allows you to mark *any* notifier as the default for your workspace.  Navigate to the **Settings** page for the notifier that you would like to use.  From the **Workspace precedence** section, click  **Set Default**.




## Creating a Notifier

You can create notifiers at the [tenant](/pipes/docs/accounts/tenant/notifiers), [organization](/pipes/docs/accounts/org/notifiers), [developer account](/pipes/docs/accounts/developer/notifiers), or workspace. Notifiers that are create in a tenant, organization, or developer account are available in all child workspaces.

To create a notifier, navigate to the **Notifiers** for the tenant, organization, developer account or workspace where you wish to create it, and click **New Notifier**

![](/images/docs/pipes/notifiers_list.png)

Enter a unique name for your notifier and click **Next**.

![](/images/docs/pipes/create_notifier_handle.png)

Choose the type of target you want to create.

![](/images/docs/pipes/create_notifier_add_target.png)

Enter the details for the target, the click **Create** to create the notifier.

![](/images/docs/pipes/create_notifier_add_target_slack.png)


## Modifying a Notifier

Find the notifier from the list on the **Notifiers** tab and click its title or gear icon.  From the **Settings** sub-tab, you can edit the notifier's name, or set it as the [default for your workspace](#default-notifier).

![](/images/docs/pipes/notifier_settings.png)

You can add or remove notification targets from the **Targets** sub-tab.

![](/images/docs/pipes/notifier_targets.png)


## Deleting a Notifier
 
You can delete a notifier from its **Settings** page. Find the notifier from the list on the **Notifiers** tab and click its title or gear icon.  From the **Settings** sub-tab, click **Delete Notifier**.  You will be prompted to confirm by entering the handle and clicking **Delete**.
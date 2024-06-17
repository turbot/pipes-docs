---
title: Mods
sidebar_label: Mods
---

# Managing Mods

Your workspace includes a hosted [Powerpipe](https://powerpipe.io/) dashboard server, allowing you to [view interactive dashboards and benchmarks](/pipes/docs/dashboards#viewing-dashboards), [save and share snapshots](/pipes/docs/dashboards#saving--sharing-snapshots) and even [schedule them to run and deliver via Slack or Teams](/pipes/docs/dashboards#scheduling-snapshots).   You can add and remove dashboards and benchmarks from your workspace by installing and removing [mods](https://powerpipe.io/docs/build). 


## Installing Recommended Mods

You can install mods from the **Settings** tab of your workspace. On the settings page, click **Mods**, then click the **Install Mods** button.

Within the install mods screen, you will be presented with a list of the
recommended mods that are compatible with the
[connections](/pipes/docs/workspaces#managing-workspace-connections) that are currently present
in your workspace. 

![](/images/docs/pipes/mod_install_1.png)

To install them, choose one or more mods, then click the **Install Mods** button.

Installation should typically only take a few seconds. You can then head over to
the **Dashboards** tab where you'll see a list of the available dashboards for
the mod(s) you installed.


## Installing a Custom Mod from an Integration

Rather than selecting an official mod within the install mods screen, you can choose to install a [custom mod](https://powerpipe.io/docs/build).  If you have set up a [GitHub Integration](/pipes/docs/integrations/github), this can be *any* mod that the Integration can access (including mods in private repos).  

You can install custom mods from the **Settings** tab of your workspace. On the settings page, click **Mods**, then click the **Install Mods** button.  From the mod installation page, click the **Custom** tab.

![](/images/docs/pipes/mod_install_custom_filled_integration.png)

Choose the **Integration** that hosts the repo for the mod you wish to install, then select the **Mod Repo** from the dropdown list.  

Choose the **Branch or Version Constraint** for the mod.  Unlike recommended mods which are only updated once a day, custom mods from integrations are updated in Pipes whenever the source repository is modified. 

When finished, click **Install Mods**.


## Installing a Mod from a GitHub Link

You can install a mod from *any* public GitHub repo by clicking on **Install from a GitHub Link** from the mod installation page. Turbot Pipes supports the installation of custom mods subject to the following rules:

- The repo must be publicly hosted on GitHub.
- There must be at least [one semver tag](https://devhints.io/semver) (not a
  pre-release) satisfying the provided semver constraint.
- The tagged version must contain a `mod.pp` or `mod.sp` file at the root of the repo.

Installed mods are updated every day to the latest version satisfied by the
semver constraint. The default of `*` means that the latest tagged version will
be installed daily.


![](/images/docs/pipes/mod_install_custom_filled_no_int.png)


Enter your custom mod publicly hosted GitHub URL and a version constraint if
applicable (if left empty, will default to `*`). When finished, click **Install Mods**.


Installation should typically only take a few seconds. You can then head over to
the **Dashboards** tab where you'll see a list of the available dashboards for
the custom mod you installed.


## Managing Mod Variables

When you install a mod in a workspace, any [variables](https://powerpipe.io/docs/build/mod-variables) that the mod uses will be visible in Turbot Pipes.

Go to the **Settings** tab of your workspace and then to the **Mods** sub-tab.
From there you can click the mod you wish to view/manage the variables for.

Within the mod detail screen, you will see a list of the available variables,
with a section per variable. You'll see the current value and can edit this and
**Save** if you are an owner of the workspace (implicit for personal workspaces,
but [explicit within an organization](/pipes/docs/organizations#managing-users)).

Depending on the type of the variable, the editor will change, but you'll
typically see either a text, a number or a text/number list editor that will
allow you to easily manage the value.

Once you've saved a mod variable, this should take effect in your workspace
within a matter of seconds. If you head back to the workspace **Dashboards**
tab, you will see the impact of that change in any dashboards that depend on it.

## Uninstalling Mods

You can delete a workspace from its detail view. First, go to the **Settings**
tab. You should be on the **Mods** sub-tab by default. From there you'll see a
list of mods installed in the workspace. Click on the mod you wish to delete and
in the detail screen that's shown, scroll to the bottom and click **Uninstall
Mod**. Follow the confirmation instructions in the modal and the mod will be
uninstalled from your workspace.

After this has completed, you'll no longer see any dashboards for this mod in
the **Dashboards** tab.

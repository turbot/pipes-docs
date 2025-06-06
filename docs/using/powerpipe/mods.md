---
title: Mods
sidebar_label: Mods
---

# Managing Mods

Your workspace includes a hosted [Powerpipe](https://powerpipe.io/) dashboard server, allowing you to [view interactive dashboards and benchmarks](/pipes/docs/using/powerpipe/dashboards), [save and share snapshots](/pipes/docs/using/powerpipe/dashboards#saving-snapshots) and even [schedule them to run and deliver via Slack or Teams](/pipes/docs/using/powerpipe/dashboards#scheduling-snapshots).   You can add and remove dashboards and benchmarks from your workspace by installing and removing [mods](https://powerpipe.io/docs/build). 

You can manage mods from the **Mods** tab for the Powerpipe service in your workspace.

Navigate to your workspace, then to the **Pipes** tab, and choose **Powerpipe**.  The **Mods** tab will list the mods that you have installed, as well as information about the version or branch that is installed.  You can type a search string or filter in the search box to filter the list.

![](/images/docs/pipes/powerpipe/powerpipe_mods_list.png)

## Installing Recommended Mods

You can install mods from the **Settings** tab of your workspace. On the settings page, click **Mods**, then click the **Install Mods** button.

Within the install mods screen, you will be presented with a list of the
recommended mods that are compatible with the
[connections](/pipes/docs/workspaces/connections) that are currently present
in your workspace. 

![](/images/docs/pipes/powerpipe/powerpipe_mod_install_recommended.png)


To install them, choose one or more mods, then click the **Install** button.

Installation should typically only take a few seconds. You can then head over to
the **Dashboards** tab, where you'll see a list of the available dashboards for
the mod(s) you installed.


## Installing a Custom Mod from an Integration

Rather than selecting an official mod within the install mods screen, you can choose to install a [custom mod](https://powerpipe.io/docs/build).  If you have set up a [GitHub Integration](/pipes/docs/integrations/github), this can be *any* mod that the Integration can access (including mods in private repos).  

You can install custom mods from the **Settings** tab of your workspace. On the settings page, click **Mods**, then click the **Install Mods** button.  From the mod installation page, click the **Custom** tab.

![](/images/docs/pipes/powerpipe/mod_install_custom_filled_integration.png)

Choose the **Integration** that hosts the repo for the mod you wish to install, then select the **Mod Repo** from the dropdown list.  

Choose the **Branch or Version Constraint** for the mod.  Unlike recommended mods, which are only updated once a day, custom mods from integrations are updated in Pipes whenever the source repository is modified. 

When finished, click **Install**.


## Installing a Mod from a GitHub Link

You can install a mod from *any* public GitHub repo by clicking on **Install from a GitHub Link** from the mod installation page. Turbot Pipes supports the installation of custom mods subject to the following rules:

- The repo must be publicly hosted on GitHub.
- There must be at least [one semver tag](https://devhints.io/semver) (not a
 pre-release) satisfying the provided semver constraint.
- The tagged version must contain a `mod.pp` or `mod.sp` file at the root of the repo.

Installed mods are updated every day to the latest version that is satisfied by the
semver constraint. The default of `*` means that the latest tagged version will
be installed daily.


![](/images/docs/pipes/powerpipe/mod_install_custom_filled_no_int.png)


Enter your custom mod publicly hosted GitHub URL and a version constraint if
applicable (if left empty, will default to `*`). When finished, click **Install**.


## Installing a Mod from an Archive File

You can install an archived mod by selecting **Upload a mod archive** option. This will allow you to upload your own archived mod file subject to the following rules:

- The mod archive file must be of `.zip` format.
- The archive must contain a `mod.pp` or `mod.sp` file at the root location and it should not be nested inside any folder.
- Size of the archive file should not exceed 20MB.

Best practices to follow when creating an archived mod file:

- Archive the mod file by navigating to the directory containing the `mod.pp` or `mod.sp` file to prevent it from being nested inside any folder.
- Ignore any hidden / unnecessary files or directories that are not required for the mod.

Please follow the steps below to create an archived mod file:
```
$ cd {mod-directory}
$ zip -r "$(basename "$PWD").zip" * -x ".*" -x "*/.*"
```

![](/images/docs/pipes/powerpipe/powerpipe_mod_install_archive.png)

Drop the archived file or select the file from your local system which is to be uploaded. Click **Install**.

Installation should typically only take a few seconds. You can then head over to
the **Dashboards** tab, where you'll see a list of the available dashboards for
the custom mod you installed.


## Managing Mod Variables

When you install a mod in a workspace, any [variables](https://powerpipe.io/docs/build/mod-variables) that the mod uses will be visible in Turbot Pipes.

From the Powerpipe **Mods** tab, you can click the mod you wish to view/manage the variables for.

![](/images/docs/pipes/powerpipe/powerpipe_mod_variables.png)


Within the mod detail screen, you will see a list of the available variables,
with a section per variable. You'll see the current value and can edit this and
**Save** if you are an owner of the workspace.

Depending on the type of the variable, the editor will change, but you'll
typically see either a text, a number, or a text/number list editor that will
allow you to easily manage the value.

Once you've saved a mod variable, this should take effect in your workspace
within a matter of seconds. If you head back to the workspace **Dashboards**
tab, you will see the impact of that change in any dashboards that depend on it.

## Uninstalling Mods

You can delete a mod from its detail view. From the list of installed mods in the Powerpipe **Mods** tab, click on the mod you wish to delete to go to the mod detail page.

![](/images/docs/pipes/powerpipe/powerpipe_mod_settings.png)

On the detail screen, scroll to the bottom and click **Uninstall Mod**. Follow the confirmation instructions in the modal, and the mod will be uninstalled from your workspace.

After this has been completed, you'll no longer see any dashboards for this mod in
the **Dashboards** tab.

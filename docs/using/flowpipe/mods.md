---
title: Mods
sidebar_label: Mods
---

# Managing Mods

Flowpipe pipelines are defined in [mods](https://flowpipe.io/docs/build).  You can add and remove Flowpipe pipelines from your workspace by installing and removing mods.  You can find mods on the [Flowpipe Hub](https://hub.flowpipe.io/), but you can also [write your own mods](https://flowpipe.io/docs/build) and run them in Pipes.


## Viewing Installed Mods

You can view the mods that are installed in your workspace from the **Mod** tab for the Flowpipe service in your workspace.  Navigate to your workspace, then to the **Pipes** tab, and choose **Flowpipe**.  The **Mods** tab will list the mods that you have installed, as well as information about the version or branch that is installed.  You can type a search string or filter in the **Query** box to filter the list.

![](/images/docs/pipes/flowpipe/flowpipe_mod_list.png)


## Installing Recommended Mods

You can install mods from the Flowpipe **Mods** tab of your workspace. On the **Mods** page, click the **Install Mod** button.

Within the install mods screen, you will be presented with a list of the
recommended mods that are compatible with the
[connections](/pipes/docs/workspaces#managing-workspace-connections) that are currently present
in your workspace. 

![](/images/docs/pipes/flowpipe/flowpipe_mod_install_recommended.png)

To install one, select it and then click the **Install Mod** button.  Installation should typically take about 30-60 seconds.

After the mod is installed, you will be prompted to [set its variables](#managing-mod-variables).

![](/images/docs/pipes/flowpipe/flowpipe_mod_install_variables.png)


## Installing a Custom Mod from an Integration

Rather than selecting an official mod within the install mods screen, you can choose to install a custom mod.  If you have set up a [GitHub Integration](/pipes/docs/integrations/github), this can be *any* mod that the Integration can access (including mods in private repos).  

You can install mods from the Flowpipe **Mods** tab of your workspace. On the **Mods** page, click the **Install Mod** button.  From the mod installation page, click the **Custom** tab.

![](/images/docs/pipes/flowpipe/flowpipe_mod_install_custom_integration.png)

Choose the **Integration** that hosts the repo for the mod you wish to install, then select the **Mod Repo** from the dropdown list.  

Choose the **Branch or Version Constraint** for the mod.  Unlike recommended mods, which are only updated once a day, custom mods from integrations are updated in Pipes whenever the source repository is modified. 

When finished, click **Install Mod**.

After the mod is installed, you will be prompted to [set its variables](#managing-mod-variables).


## Installing a Mod from a GitHub Link

You can install a mod from *any* public GitHub repo by clicking on **Install from a GitHub Link** from the mod installation page. Turbot Pipes supports the installation of custom mods subject to the following rules:

- The repo must be publicly hosted on GitHub.
- There must be at least [one semver tag](https://devhints.io/semver) (not a
 pre-release) satisfying the provided semver constraint.
- The tagged version must contain a `mod.fp` file at the root of the repo.

The default of `*` means that the latest tagged version will
be installed.


![](/images/docs/pipes/flowpipe/flowpipe_mod_install_custom_link.png)

Enter your custom mod publicly hosted GitHub URL and a version constraint if
applicable (if left empty, will default to `*`). When finished, click **Install Mod**.  Installation should typically take about 30-60 seconds.

After the mod is installed, you will be prompted to [set its variables](#managing-mod-variables).

## Installing a Mod from an Archive File

You can install an archived mod by selecting **Install from mod archive** option. This will allow you to upload your own archived mod file subject to the following rules:

- The mod archive file must be of `.zip` format.
- The archive must contain a `mod.fp` file at the root location and it should not be nested inside any folder.
- Size of the archive file should not exceed 20MB.

Best practices to follow when creating an archived mod file:

- Archive the mod file by navigating to the directory containing the `mod.fp` file to prevent it from being nested inside any folder.
- Ignore any hidden / unnecessary files or directories that are not required for the mod.
Please follow the below steps to create an archived mod file:
```
$ cd {mod-directory}
$ zip -r "$(basename "$PWD").zip" * -x ".*" -x "*/.*"
```

Drop the archived file or select the file from your local system which is to be uploaded. Click **Install**.

After the mod is installed, you will be prompted to [set its variables](#managing-mod-variables).

## Managing Mod Variables

When you install a mod in a workspace, any [variables](https://flowpipe.io/docs/build/mod-variables) that the mod uses will be visible in Turbot Pipes.

Go to the Flowpipe **Mods** tab for your workspace.  From the list of installed mods, click the mod for which you wish to view/manage variables.

![](/images/docs/pipes/flowpipe/flowpipe_mod_variables.png)

Within the mod detail screen, you will see a list of the available variables,
with a section per variable. You'll see the current value and can edit this and
**Save** if you are an owner of the workspace.

Depending on the type of the variable, the editor will change, but you'll
typically see either a text, a number, or a text/number list editor that will
allow you to easily manage the value.

Once you've saved a mod variable, this should take effect in your workspace
within a matter of seconds.

## Uninstalling Mods

You can delete a workspace from its detail view. From the list of installed mods in the Flowpipe **Mods** tab, click on the mod you wish to delete.

![](/images/docs/pipes/flowpipe/flowpipe_mod_settings.png)

In the detail screen that's shown, scroll to the bottom and click **Uninstall Mod**.  Follow the confirmation instructions in the modal, and the mod will be uninstalled from your workspace.

After this has been completed, you'll no longer see any pipelines for this mod in
the **Pipelines** tab.

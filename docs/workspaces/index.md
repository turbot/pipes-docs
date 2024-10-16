---
title: Workspaces
sidebar_label: Workspaces
---

# Workspaces

The **Workspace** is where work gets done!  A **Workspace** provides a secure, independent set of Pipes resources.  Workspaces allow you to separate your Steampipe instances for
security, operational, or organizational purposes.  Your workspace includes:
- A dedicated [Steampipe](/pipes/docs/using/steampipe/) database instance hosted in Turbot Pipes and available via a public Postgres endpoint. You can query the workspace database from the Turbot Pipes
web console, run queries or controls from a remote Powerpipe or Steampipe CLI instance, or
connect to your workspace from many third-party tools.
- Your own hosted [Powerpipe](/pipes/docs/using/powerpipe/) server, providing secure access to your benchmarks and dashboards from any mod hosted in a public or private Github repository.
- Your own hosted [Flowpipe](/pipes/docs/using/flowpipe/) server allowing you to run pipelines and set up always-on triggers to run your pipelines automatically on a schedule or in response to events.


## Creating Workspaces

You can create workspaces from the **Workspaces** tab for your developer account or
organization. From the **Workspaces** tab, click **New Workspace**. Note that if
the **New Workspace** button is disabled, you have likely reached a limit for
your plan.

<img src="/images/docs/pipes/pipes_workspace_create_2.png" width="400pt"/>
<br />

If you are on a paid plan, you may select the **instance type** for your workspace.  Select the instance type that meets your capacity, performance, capability, and cost requirements.

Each workspace must have a **handle**. The workspace handle is a friendly
identifier for your workspace, and must be unique across your workspaces. You
can change the handle later, but note that the DNS name for your workspace
includes the handle. If you change the handle, your workspace's DNS name will
also change. Enter a handle for your workspace and click **Create Workspace**.

If you have no connections defined, you will be prompted to create one. In order
to query data, you'll need at least one connection. Click one of the plugins
from the list. Enter the required settings for the plugin. You can verify your
credentials using the **Test Connection** button, and then click **Create**.

You will be prompted to add a connection to the workspace that you just created.
Select the connection that you wish to add and click **Add to Workspace** if you would like to add a connection to your
workspace at this time.

<img src="/images/docs/pipes/pipes_workspace_add_connection.png" width="400pt"/>
<br />

If the connection you added has mods associated with it, you will be prompted to add mods to the workspace that you just created.
Select the mods you wish to install and click **Install Mods** if you would like to add mods to your
workspace at this time.

<img src="/images/docs/pipes/pipes_workspace_install_mods.png" width="400pt"/>
<br />


## Deleting Workspaces

You can delete a workspace from its **Advanced** tab. From the **Workspaces**
tab for your developer account or organization, click on the workspace you wish to
delete. On the workspace page, go to the **Advanced** tab, select **Workspace**
from the menu on the left, and click **Delete workspace**. You will be prompted
to confirm deletion; enter the workspace name and click **Delete**.



## Workspace Maintenance

Your workspace may be updated and rebooted during the weekly maintenance window,
Sundays 2:00am - 5:00am EST/EDT. This window is not currently configurable.

During maintenance, your workspaces will be updated to the latest Steampipe
version and the latest plugin versions. At this time, you cannot opt out of the
weekly update.

## Sleeping, Waking, and Rebooting Workspaces

After a workspace has been created, it is in the `enabled` state - the workspace database is running and available and any scheduled pipelines will run.  If no one accesses the database for 4 days, the workspace will be put to sleep and the status changed to `disabled`.  You can wake up (enable) the workspace from the console.  Simply click **Wake Up** in the banner that appears at the top of your sleeping workspace.

<img src="/images/docs/pipes/pipes_workspace_sleeping_banner.png" width="400pt"/>
<br />

You can also **Wake Up** (enable), **Sleep** (disable) or **Reboot** your workspace from the **Advanced** / **Workspace** page for your workspace.

<img src="/images/docs/pipes/pipes_workspace_settings_advanced.png" width="400pt"/>
<br />

### Workspace States

| State       | Description
|-------------|----------------------------
| `creating`  | The workspace is being created but is not yet available.
| `enabling`  | The workspace database is being started. Pipelines and datatanks are being enabled to run as scheduled.
| `enabled`   | The workspace database is running and available in the API and via SQL.  Pipelines and datatanks are running as scheduled.
| `disabling` | The workspace database is being shut down . All pipelines and datatanks are being disabled.
| `disabled`  | The workspace database is shut down and users cannot access it. All pipelines and datatanks are disabled.
| `deleted`   | The workspace has been deleted.


<!--
 | `pausing`   | The workspace database is running, but all pipelines and datatanks are being paused.
| `paused` ?   | [Future??] The workspace database is running, but all pipelines and datatanks are paused.
-->
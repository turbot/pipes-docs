---
title: Steampipe
sidebar_label: Steampipe
---


# Steampipe

Your workspace includes a hosted [Steampipe](https://steampipe.io) database.  Steampipe exposes APIs and services as a high-performance relational database, enabling you to write SQL-based queries to explore dynamic data.

Your Steampipe instance is built on PostgreSQL, and it is available via a publicly available endpoint, allowing you to connect from a remote Steampipe, Powerpipe, or Flowpipe client or from many other [third-party tools](https://turbot.com/pipes/docs/connect).

Your Steampipe database is accessible from all the pipes in your workspace. You can query your Steampipe database from the Turbot Pipes web console, share snapshots of your queries, and even run snapshots on a schedule. You can visualize your data with Powerpipe benchmarks and dashboards and query the database in your Flowpipe pipelines.   

You can accelerate your queries with a Datatank. With Datatank, you can proactively query connections at regular intervals and store the results in a persistent schema. You can then query the stored results instead of the live schemas, resulting in reduced query latency (at the expense of data freshness).



## Steampipe Database Search Path

Your workspace includes a Steampipe database, and this database may include many schemas.  When querying the database, any unqualified table names are resolved using the schema [search path](https://steampipe.io/docs/guides/search-path).  Mods are written using unqualified names, which allows you to target specific [datatanks](/pipes/docs/using/steampipe/datatank), [connections](/pipes/docs/using/steampipe/connections), and [aggregators](/pipes/docs/using/steampipe/aggregators).  Pipes is opinionated on the search path because *usually* you want to use a table from the datatank if it exists, otherwise an aggregator if one exists, otherwise a connection.

By default, Pipes builds the search path as follows:
1. The `public` schema
2. Datatank schemas, alphabetically
2. Aggregator schemas, alphabetically
2. Connection schemas, alphabetically

Usually, this is the desired order. However, you can set a default [search path prefix](https://steampipe.io/docs/guides/search-path#search-path-prefix) if you want to customize the search path

You can set the prefix from the Steampipe **Advanced** / **Status** page for your workspace.  Navigate to your workspace, and from the **Pipes** tab, select **Steampipe**.  From the Steampipe **Advanced** tab, select **Status** from the left-hand menu.

![](/images/docs/pipes/steampipe/steampipe_settings_advanced.png)


The active default search path is displayed.  To add or change the prefix, click **edit**, select the schemas from the list in the order you would like them to appear, then click **Save**.

Setting a search path prefix above will update the search path for the entire workspace and will apply to all users with access to it.
To set a prefix for an individual query instead, use the query editor: go to the Query tab and click the search path prefix selector icon next to the `Format` button. This allows you to define a prefix specific to the current query.
For more details, see [Exploring Schemas](/pipes/docs/using/steampipe/query#exploring-schemas).
## Workspace Maintenance

Your workspace may be updated and rebooted during the weekly maintenance window,
Sundays 2:00am - 5:00am EST/EDT. This window is not currently configurable.

During maintenance, your workspaces will be updated to the latest Steampipe
version and the latest plugin versions. At this time, you cannot opt out of the
weekly update.

## Sleeping, Waking, Upgrading and Rebooting Workspace

After a workspace has been created, it is in the `enabled` state - the workspace's Steampipe database is running and available, and any scheduled snapshots will run.  If no one accesses the database for 4 days, it will be put to sleep, and the status will be changed to `disabled.`  You can wake up (enable) the workspace from the console.  Simply click **Wake Up** in the banner that appears at the top of your sleeping workspace.

![](/images/docs/pipes/pipes_workspace_sleeping_banner.png)

<br />

You can also **Wake Up** (enable), **Sleep** (disable), **Upgrade** or **Reboot** your workspace from the Steampipe **Advanced** page for your workspace. Navigate to your workspace, and from the **Pipes** tab, select **Steampipe**.  From the Steampipe **Advanced** tab, select **Status** from the left-hand menu.

> Note: Upgrading your workspace will cause it to be rebooted, and all pipelines and datatanks will be disabled while the upgrade is in progress. The upgrade process may take several minutes to complete.

![](/images/docs/pipes/steampipe/steampipe_advanced_status.png)


<br />

### Workspace States

| State       | Description
|-------------|----------------------------
| `creating` | The workspace is being created but is not yet available.
| `enabling` | The workspace database is being started. Pipelines and datatanks are being enabled to run as scheduled.
| `enabled` | The workspace database is running and available in the API and via SQL.  Pipelines and datatanks are running as scheduled.
| `disabling` | The workspace database is being shut down. All pipelines and datatanks are being disabled.
| `disabled` | The workspace database is shut down, and users cannot access it. All pipelines and datatanks are disabled.
| `deleted` | The workspace has been deleted.


## Query Log

Turbot Pipes provides a log of the queries that have been run against your
Steampipe workspace database. You can view the query logs from the Steampipe **Advanced** tab for your workspace.  Navigate to your workspace, and from the **Pipes** tab, select **Steampipe**.  From the Steampipe **Advanced** tab, select **Query Log** from the left-hand menu.

![](/images/docs/pipes/steampipe/steampipe_query_log.png)

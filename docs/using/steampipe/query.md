---
title: Query
sidebar_label: Query
---


# Running Queries

Once you've [added a connection](/pipes/docs/using/steampipe/connections), you will be able to run [SQL queries](https://steampipe.io/docs/sql/steampipe-sql) to explore your data, either interactively in the console or [via any PostgreSQL-compatible client](/pipes/docs/connect).


## Exploring Schemas
 
If you navigate to your workspace and then select Steampipe from the **Pipes** tab, you'll land on the interactive **Query** console. By default, the **Schema** tab will be selected on the left-hand side panel, with the query editor to the right.

<img src="/images/docs/pipes/steampipe/pipes_schemas_landing.png" />
<br />

The schema tab allows you to explore and inspect [schemas](/pipes/docs/using/steampipe/connections#adding-a-connection-schema) available in your workspace.

Clicking on a schema will expand it to reveal the tables it contains. You can then click on a table to view its columns along with their respective data types.  Hovering over a table displays a tooltip with its name and a few commonly used queries.

<img src="/images/docs/pipes/steampipe/pipes_schemas_explore.png" />
<br />

Clicking on an example query from the tooltip will automatically populate it in the Query editor on the right and will execute it for you. This is a great way to quickly explore the data in a table without having to write the query yourself.  You can edit the query in the editor to experiment and explore further.

<img src="/images/docs/pipes/steampipe/pipes_schemas_execute_example.png" />
<br />

Hovering over a column shows a tooltip containing its name, data type, and a brief description.

<!--- This needs a screenshot -->

The schema list supports flexible searching across schemas, tables, and columns. For example, if you search for `hackernews`, you will find matching results displayed for the `hackernews` schema and its tables.

<img src="/images/docs/pipes/steampipe/pipes_schemas_search.png" />
<br />

By default, the schema list displays [Datatanks](/pipes/docs/using/steampipe/datatank), [Aggregators](/pipes/docs/using/steampipe/aggregators) and any non-aggregated [Connections](/pipes/docs/using/steampipe/connections). The connections are listed in the order they appear in the [search path](/pipes/docs/using/steampipe#steampipe-database-search-path).  You can choose to show all schemas by clicking the **Settings** icon and selecting **Show aggregated connections** from the dropdown.

<img src="/images/docs/pipes/steampipe/pipes_schemas_showall.png" />
<br />


## Exploring Queries

The **Queries** tab on the sidebar lets you explore and run example queries, as well as queries from your history.

The **History** folder displays a list of queries you have executed, with the most recent first. This gives you a quick way to view, edit, and re-run queries you have run in the past.  Click on a query to populate the query editor and run it.

<img src="/images/docs/pipes/steampipe/pipes_query_history.png" />
<br />

The example queries are grouped by plugin. Clicking a folder will expand it to reveal the queries it contains. Depending on the plugin, you may also find the examples grouped by service. For example, the `AWS` plugin has queries grouped by `EC2`, `S3`, `IAM` and so on.

<img src="/images/docs/pipes/steampipe/pipes_query_landing.png" />
<br />

You can search for queries by name or description from the search box at the top of the sidebar.

<img src="/images/docs/pipes/steampipe/pipes_query_execute_example.png" />
<br />


Click on a query to populate the query editor and run it.

## Downloading Results

After you've run a query, you can download the results to a CSV file by clicking the **Download** button at the top right corner of the query results pane.

## Saving Snapshots

To take a snapshot, click the **Snap** button at the top right of the query results pane after you have run the query you wish to snap.

<img src="/images/docs/pipes/steampipe/pipes_schemas_query_result_toolbar.png" width="200pt"/>
<br />

This will then take you to the dashboard snapshot view.

<img src="/images/docs/pipes/steampipe/pipes_query_snapshot.png" />
<br />

You can manage this snapshot and browse others from the [snapshots](/pipes/docs/using/steampipe/snapshots) tab.

## Scheduling Query Snapshots

Rather than manually capture query snapshots, Turbot Pipes allows you to schedule them and be notified when they are complete.

Scheduling a snapshot is as simple as navigating to the **Query** page, executing a query, and choosing the **Schedule** dropdown from the toolbar in the results pane.

<img src="/images/docs/pipes/steampipe/pipes_query_schedule_snapshot.png" width="200pt"/>
<br />

From here, you can either choose to create a new schedule or view all scheduled snapshots.

If you select **New Schedule**, you'll be presented with the following screen.

<img src="/images/docs/pipes/steampipe/pipes_query_new_schedule_snapshot.png" width="200pt"/>
<br />

<table>
  <tr>
    <th>Option</th>
    <th>Description</th>
  </tr>
  <tr>
    <td nowrap="true">Title</td>
    <td>The title of the schedule.</td>
  </tr>

  <tr>
    <td nowrap="true">Frequency</td>
    <td>How often scheduled snapshot should run: 
       <inlineCode>Weekly</inlineCode>, <inlineCode>Daily</inlineCode>, <inlineCode>Hourly</inlineCode>, <inlineCode>Custom</inlineCode><br/>
 For <inlineCode>Weekly</inlineCode>, <inlineCode>Daily</inlineCode> and <inlineCode>Hourly</inlineCode> frequencies, Turbot Pipes will automatically allocate a random time for these, with <inlineCode>Weekly</inlineCode> schedules being run at that time on a Sunday. For a <inlineCode>Custom</inlineCode> frequency, you can supply a cron schedule (not more than once every 15 minutes).
    </td>

  </tr>

  <tr>
    <td nowrap="true">Visibility</td>
    <td>Optionally choose the visibility of the snapshot generated. By default, visibility is restricted to only those with access to your workspace, but you can choose to share it so that anyone on the internet with the link can view it.</td>
  </tr>

  <tr>
    <td nowrap="true">Notifications</td>
    <td>Optionally send a summary notification to a Slack and/or Microsoft Teams webhook. This will contain a link back to the Snapshot.
    </td>
  </tr>

  <tr>
    <td nowrap="true">Snapshot tags</td>
    <td>Add optional tags to the created snapshot. These can be used to easily find snapshots at a later date via the search functionality.</td>
  </tr>
</table>

After scheduling a snapshot, you will be taken to the schedule detail page, which shows you editable details of the schedule, information on its next run and last run status, and a link to the process logs.

When the schedule runs, Pipes will upload the snapshot to your workspace as the `system` user rather than attribute the activity to the user creating the schedule.

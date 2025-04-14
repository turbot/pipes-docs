---
title: Query
sidebar_label: Query
---


# Running Queries

Once you've [added a connection](/pipes/docs/using/steampipe/connections) you will be able to run
[SQL queries](https://steampipe.io/docs/sql/steampipe-sql) to explore your data, either interactively in
the console, or [via any PostgreSQL-compatible client](/pipes/docs/connect).



## Exploring Schemas
 

If you navigate to your workspace and then select Steampipe from the **Pipes** tab, you'll land on the interactive **Query** console with the **Schema** table selected on the left.

<img src="/images/docs/pipes/steampipe/pipes_schemas_landing.png" width="400pt"/>
<br />

The **Schema** tab on the left allows you to explore and inspect schemas available in your workspace. Alternatively, you can also test your own queries in the editor on the right.
The schema list supports flexible searching across schemas, tables and columns. For example, if you search for `hackernews`, you will find matching results displayed for the `hackernews` schema and its tables.

<img src="/images/docs/pipes/steampipe/pipes_schemas_search.png" width="400pt"/>
<br />

Note that the schema list displays `Datatanks`, `Aggregators` and `Non-aggregated Connections` by default conforming to the search path settings for the workspace. This allows to highlight key schemas whilst also improving readability of the list, specially in workspaces with a large number of agggregated connections.
You can choose to show all schemas by clicking the **Settings** icon and selecting `Show aggregated connections` from the dropdown.

<img src="/images/docs/pipes/steampipe/pipes_schemas_showall.png" width="400pt"/>
<br />

Clicking on a schema will expand it to reveal the tables it contains. You can then click on a table to view its columns along with their respective data types.
Hovering over a table displays a tooltip with its name and a few commonly used queries. Similarly, hovering over a column shows a tooltip containing its name, data type, and a brief description.
Once you have searched for `hackernews`, click `hackernews_item` to view its columns. You can then hover over the table to display the tooptip along with the commonly used queries.

<img src="/images/docs/pipes/steampipe/pipes_schemas_explore.png" width="400pt"/>
<br />

Clicking on an example query from the tooltip will automatically populate it in the Query editor on the right and will also execute it for you. This is a great way to quickly explore the data in a table without having to write the query yourself. 
Notice that the text mentioning `Query` on top of the Query editor tab is now changed to display a description of the query executed.
You can also edit the query in the editor to experiment and explore further. Click on the `Run` button to execute the query.

<img src="/images/docs/pipes/steampipe/pipes_schemas_execute_example.png" width="400pt"/>
<br />

## Exploring Queries

Switching to the **Queries** tab on the left allows you to explore and inspect various example queries.
Note that the queries are grouped by the plugin to which they cater. For example, the workspace in question has connections of plugins `aws`, `hackernews` and `net` and hence the queries are grouped under them.
Clicking on a plugin folder will expand it to reveal the queries it contains. Depending on the plugin, you may find the example grouped by the service to which they cater. For example, the `AWS` plugin has queries grouped by `EC2`, `S3`, `IAM` and so on.

<img src="/images/docs/pipes/steampipe/pipes_query_landing.png" width="400pt"/>
<br />

You can search for queries by name or description from the search tab.
Searching with the text `S3 bucket public` lists all matching queries, with context around the particular service to which it caters.

<img src="/images/docs/pipes/steampipe/pipes_query_execute_example.png" width="400pt"/>
<br />

The **History** folder displays a list of queries executed by you in most recent first order. This gives you a quick way to access queries you have run in the past.

<img src="/images/docs/pipes/steampipe/pipes_query_history.png" width="400pt"/>
<br />

## Downloading Results

After you've run a query, you can download the results to a CSV file by clicking the **Download** button at the top right corner of the query results pane.


## Saving Snapshots

To take a snapshot, click the **Snap** button at the top right of the query results pane after you have run the query you wish to snap.

<img src="/images/docs/pipes/steampipe/pipes_schemas_query_result_toolbar.png" width="200pt"/>
<br />

This will then take you to the dashboard snapshot view.

<img src="/images/docs/pipes/steampipe/pipes_query_snapshot.png" width="400pt"/>
<br />

You can manage this snapshot and browse others from the [snapshots](/pipes/docs/using/steampipe/snapshots) tab.

## Scheduling Query Snapshots

Rather than manually capture query snapshots, Turbot Pipes allows you to
schedule them and be notified when complete.

Scheduling a snapshot is as simple as navigating to the **Query** page, executing an example query for a table or writing and executing a query from scratch.
The choose the **Schedule** dropdown from the toolbar in the results pane.

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

After scheduling a snapshot, you will be taken to the
schedule detail page, which shows you editable details
of the schedule, information on its next run and last run status, along with a
link out to the process logs.

When the schedule runs, Pipes will upload the snapshot to your workspace as
the `system` user, rather than attribute the activity to the user creating the
schedule. 

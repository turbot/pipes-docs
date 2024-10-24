---
title: Query
sidebar_label: Query
---


# Running Queries

Once you've [added a connection](/pipes/docs/using/steampipe/connections) you will be able to run
[SQL queries](https://steampipe.io/docs/sql/steampipe-sql) to explore your data, either interactively in
the console, or [via any PostgreSQL-compatible client](/pipes/docs/connect).



## Exploring Schemas
 

If you navigate to your workspace, then select Steampipe from the **Pipes** tab, you'll land on on the interactive **Query** console.

<img src="/images/docs/pipes/cloud-query-editor.png" width="400pt"/>
<br />

From here you can either explore your schemas on the left, or dive right in and
test out your own queries in the editor. The schema list supports flexible
searching across all the tables in your schemas. For example, if you search for
`hack new`, that will find a match for the `hackernews_show_hn` table in our
`hackernews` schema.

<img src="/images/docs/pipes/cloud-query-schema-search.png" width="200pt"/>
<br />

Clicking the search result will automatically generate a query to select all the
columns from that schema table, limited to 100 rows and will automatically run
it for you.

<img src="/images/docs/pipes/cloud-query-table-results.png" width="400pt"/>
<br />

If you click the `Edit` button you can amend the query, perhaps by selecting
just the columns you're interested in, or adding a `where` clause to filter the
results. Please note that we limit queries to 5,000 rows in the interactive
query console.

<img src="/images/docs/pipes/cloud-query-custom-query.png" width="400pt"/>
<br />

## Downloading Results

After you've run a query, you can download the results to a CSV file by clicking
the **Download** button at the bottom of the query editor.


## Saving Snapshots

To take a snapshot, click the **Snap** button at the top of the query editor
after you have run the query you wish to snap.

<img src="/images/docs/pipes/cloud-query-toolbar.png" width="200pt"/>
<br />

This will then take you to the dashboard snapshot view.

<img src="/images/docs/pipes/cloud-query-snapshot.png" width="400pt"/>
<br />

You can manage this snapshot and browse others from the [snapshots](/pipes/docs/using/steampipe/snapshots) tab.

## Scheduling Query Snapshots

Rather than manually capture query snapshots, Turbot Pipes allows you to
schedule them and be notified when complete.

Scheduling a snapshot is as simple as navigating to the query editor, selecting
a table or writing a query and choosing the **Schedule** dropdown from the query
toolbar.

<img src="/images/docs/pipes/cloud-query-snapshot-schedule-dropdown.png" width="300pt"/>
<br />

From here you can either choose to create a new schedule, or see any existing
schedules that are configured for this query.

If you select **New Schedule** you'll be presented with the following screen.

<img src="/images/docs/pipes/cloud-query-snapshot-schedule-new.png" width="300pt"/>
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
    <td>Optionally choose the visibility of the snapshot generated. By default, visibility is restricted to only those with access to your workspace, but you can choose to share it such that anyone on the internet with the link can view it.</td>
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


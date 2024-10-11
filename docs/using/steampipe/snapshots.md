---
title: Snapshots
sidebar_label: Snapshots
---


## Saving Snapshots

Turbot Pipes allows you to save and share query **snapshots** that are
dashboards containing a table generated from your query results.

To take a snapshot, click the **Snap** button at the top of the query editor
after you have run the query you wish to snap.

<img src="/images/docs/pipes/cloud-query-toolbar.png" width="200pt"/>
<br />

This will then take you to the dashboard snapshot view.

<img src="/images/docs/pipes/cloud-query-snapshot.png" width="400pt"/>
<br />

You can [manage](/pipes/docs/dashboards#managing-snapshots) this snapshot and
[browse](/pipes/docs/dashboards#browsing-snapshots) others from the
**Dashboards** page.

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
    <td>The title of the <a href="/pipes/docs/pipelines">pipeline</a> that will run this schedule.</td>
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
[pipeline detail](/pipes/docs/pipelines) page, which shows you editable details
of the schedule, information on its next run and last run status, along with a
link out to the [process](/pipes/docs/activity#processes) logs.

The scheduled snapshot pipeline will upload the snapshot to your workspace as
the `system` user, rather than attribute the activity to the user creating the
schedule. We will retry steps in the pipeline where possible e.g. any 5xx series
errors from a call to a notification webhook will retry up to a maximum of 2
times, whereas a 400 error would not retry.


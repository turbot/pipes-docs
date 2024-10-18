---
title: Snapshots
sidebar_label: Snapshots
---


# Snapshots

Turbot Pipes allows you to save and share dashboard **snapshots**. A snapshot is
a saved view of a dashboard at a point in time with a given set of inputs and
variables.

To take a snapshot, click the **Snap** button at the top of the dashboard after
the dashboard is fully loaded (the button will be disabled until the dashboard
has finished loading).

<img src="/images/docs/pipes/dash_snapshot_header.png" width="400pt"/>
<br />

Alternately, you can click the **Share** button to take a snapshot and share a
link with others. You can set the visibility of the snapshot to restrict access
to only those with access to your workspace, or share it such that anyone on the
internet with the link can view it.

<img src="/images/docs/pipes/dash_snapshot_share.png" width="400pt"/>
<br />

## Browsing Snapshots

From any dashboard, you can browse and navigate its snapshot history. Click the
**View** button at the top of the dashboard to display the menu. You can select
a date from the calendar and the snapshots from that date are listed beneath.
Click any snapshot to open it.

<img src="/images/docs/pipes/dash_snapshot_dropdown.png" width="400pt"/>
<br />

Clicking **All matching snapshots** at the bottom of the menu will take you to
the snapshots page (you can also navigate to this page by clicking the
**Snapshots** button at the top of the **Dashboards** pane).

## Managing Snapshots

You can browse and search all snapshots in your workspace. From the main
dashboard page, click the **Snapshots** button at the top of the page.

<img src="/images/docs/pipes/dash_header_snap.png" width="400pt"/>
<br />

The Snapshots page allows you to manage all snapshots in your workspace. The
**Query** box allows you to enter a [query filter](/pipes/docs/reference/query-filter) to
search and filter the snapshot list.

<img src="/images/docs/pipes/dash_snap_list.png" width="400pt"/>
<br />

Click any snapshot to view it.

To delete a snapshot, click the trash can icon for the snapshot you wish to
delete. You will be prompted to confirm deletion.

<img src="/images/docs/pipes/dash_snap_delete_confirm.png" width="400pt"/>
<br />

## Scheduling Snapshots

Rather than manually capture dashboard snapshots, Turbot Pipes allows you to
schedule them and be notified when complete.

Scheduling a snapshot is as simple as navigating to the dashboard you wish to
schedule, optionally setting it up with any required inputs and choosing the
**Schedule** dropdown from the dashboard toolbar.

<img src="/images/docs/pipes/dash-snapshot-schedule-dropdown.png" width="400pt"/>
<br />

From here you can either choose to create a new schedule, or see any existing
schedules that are configured for this dashboard.

If you select **New Schedule** you'll be presented with the following screen.

<img src="/images/docs/pipes/dash-snapshot-schedule-new.png" width="400pt"/>
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
    <td>Optionally send a summary notification to a Slack and/or Microsoft Teams webhook. We will send a summary of all the card values in the dashboard with a link back to the Snapshot.
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





<!--
------



## Viewing and Editing Pipelines

To view your currently defined pipelines, head to your workspace and navigate to
the **Pipelines** tab. Here you'll see a list of all the defined pipelines, with
information on when they last run and when they are next due to run. Clicking on
the **Last run** option will take you to the
[process](/pipes/docs/activity#processes) for that run.

<img src="/images/docs/pipes/cloud-pipelines.png" width="400pt"/>
<br />

If you navigate into a pipeline, you'll get an overview of 2 main areas. The
left section shows details about the task that this pipeline is performing and
on the right you'll get metadata about the pipeline, such as its run frequency.

<img src="/images/docs/pipes/cloud-pipeline-detail.png" width="400pt"/>
<br />

Depending on the type of pipeline being run, certain properties may be editable,
such as **Snapshot Tags**, **Visibility** and **Notifications**. Clicking the
edit icon will bring up a modal that will allow you to edit the property.

<img src="/images/docs/pipes/cloud-pipeline-detail-frequency.png" width="400pt"/>
<br />


## Manual Pipeline Run

If desired, you can manually initiate a Pipeline run by clicking the **Run now**
button at the top of the page. This allows you to run a pipeline on an ad hoc
basis, and is useful for testing and troubleshooting. As with other Turbot Pipes
APIs, **Run now** is rate-limited, with per-plan limits.

## Deleting Pipelines

If you wish to delete the pipeline, click the **Delete pipeline** at the bottom
of the metadata section. You'll be asked to confirm before it's deleted.

<img src="/images/docs/pipes/cloud-pipeline-detail-delete.png" width="400pt"/>
<br />

-->
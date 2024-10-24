---
title: Dashboards
sidebar_label: Dashboards
---

# Dashboards

Once you've added a connection and installed one or more mods into your
workspace, the [Dashboards](https://powerpipe.io/docs/run/dashboard) and
[Benchmarks](https://powerpipe.io/docs/run/benchmark) will become available for you to run in the
**Dashboards** tab. You can browse the list, or use the powerful search to
filter by name / tag etc.


Navigate to your workspace, then from the **Pipes** tab choose **Powerpipe**. 

![](/images/docs/pipes/gs_dashboard_list.png)


<br />

Click on a dashboard to run it.

![](/images/docs/pipes/dash_example_1.png)



## Saving Snapshots

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
    <td>The title of this schedule.</td>
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
schedule detail page, which shows you editable details
of the schedule, information on its next run and last run status, along with a
link out to the process logs.

When the schedule runs, Pipes will upload the snapshot to your workspace as
the `system` user, rather than attribute the activity to the user creating the
schedule. 


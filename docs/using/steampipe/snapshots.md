---
title: Snapshots
sidebar_label: Snapshots
---

# Snapshots

Turbot Pipes allows you to save and share query **snapshots** that are
dashboards containing a table generated from your query results.  You can [save](/pipes/docs/using/steampipe/query#saving-snapshots) and [schedule](/pipes/docs/using/steampipe/query#scheduling-query-snapshots) query snapshots from the **Query** tab, or [take snapshots from the Steampipe CLI](https://steampipe.io//docs/query/snapshots) and upload them to your workspace.

You can manage these snapshots from the **Snapshots** tab for the Steampipe service in your workspace.


## Browsing Snapshots

To view a list of snapshots, navigate to your workspace.  From the **Pipes** tab, select **Steampipe**, then go to the **Snapshots** tab.

The **Snapshots** tab lists all the query snapshots in the workspace, including the snapshot title, tags, and the date and time when the snapshot was taken.  

![](/images/docs/pipes/steampipe/steampipe_snapshot_list.png)

Click on a snapshot title to [view or edit it](#editing-snapshots).


## Sharing Snapshots


When taking a snapshot, you can choose the visibility of the snapshot generated. By default, visibility is restricted to only those with access to your workspace, but you can choose to share it such that anyone on the internet with the link can view it.

You can subsequently change the visibility in Pipes in multiple places:
- From the Steampipe **Snapshots** tab for your workspace, click the sharing icon for the snapshot you wish to modify. 
- From the snapshot, click the **Share** button.
- From the snapshot properties panel, click the pencil next to the **Visibility**

In all cases, a dialog will appear showing the current visibility.  

To make the snapshot available to anyone with the link, select **Anyone with Link**, then click **Share and Copy Link**.  


![](/images/docs/pipes/steampipe/steampipe_snapshot_share.png)

To restrict access to workspace members only, click **Delete Shared Link**.


![](/images/docs/pipes/steampipe/steampipe_snapshot_unshare.png)


## Editing Snapshots

You can edit a snapshots **Title**, **Tags**, and **Visibility** from the snapshot's properties panel.  To view the properties panel:
- From the Steampipe **Snapshots** tab for your workspace, click the gear icon for the snapshot you wish to modify; or
- From a snapshot, click the gear icon at the top right.


![](/images/docs/pipes/steampipe/steampipe_snapshot_property_panel.png)


The properties panel will show details about the snapshot. Editable fields will have a pencil icon next to them; click the pencil to edit the field.

You can also **download** or **delete** the snapshot from the properties panel.


## Deleting Snapshots
To delete a snapshot, click the trash can icon for the snapshot you wish to delete. 

You can also delete the snapshot directly from the snapshot itself.  Click the gear icon at the top right to show the the properties panel, then click **Delete Snapshot**.  

You will be prompted to confirm deletion.

![](/images/docs/pipes/steampipe/steampipe_snapshot_delete_confirm.png)



## Managing Snapshot Schedules

To view a list of snapshot schedules, navigate to your workspace.  From the **Pipes** tab, select **Steampipe**, then go to the **Snapshots** tab.  

Click the **Scheduled** sub-tab to view a list of all the query snapshot schedules in the workspace, including the schedule title, the next run time, last run time, and tags.

![](/images/docs/pipes/steampipe/steampipe_snapshot_schedule_list.png)


Click on a schedule title to view or manage the schedule.

![](/images/docs/pipes/steampipe/steampipe_snapshot_schedule_detail.png)
...

From this page, you can edit the schedule **Title**, **Frequency** and **Notifications**, as well as the **Title**, **Tags**, and **Visibility** for the snapshots that it will generate.  Click the pencil icon next to the relevant field to edit it.

The status of the last run appears at the top of the page, but you can link to the previous executions as well by clicking **All Runs**. This will take you to the **Activity** page, filtered to show only the process related to this query snapshot schedule.

If you want to delete the schedule, click **Delete Pipeline**.  You will be prompted to confirm deletion.  alternatively, can delete the schedule from the list on the **Scheduled** sub-tab by clicking the trashcan icon for the schedule you wish to delete.

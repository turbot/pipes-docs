---
title: Activity
sidebar_label: Activity
---

# Activity

The **Activity** tab for your workspace tab provides visibility into the all events that occur in your workspace.  

## Audit Log

The **Audit Log** provides a log of API activity associated with your workspace including _who_ did _what_ and _when_.

To view the audit log for your workspace, navigate to your workspace and then to the **Activity** tab.  From the left-hand menu, select **Audit Log**.

![](/images/docs/pipes/workspace_audit_log.png)
<br />


## Processes


Many Turbot Pipes APIs perform tasks asynchronously. These tasks include Steampipe and Powerpipe scheduled snapshots, Flowpipe trigger and pipeline executions, one-time requests (install a mod into a workspace), and recurring system tasks (update the workspace container image and plugins every week). Steampipe **Processes** provide visibility into these activities.

To view the processes for your workspace, navigate to your workspace and then to the **Activity** tab.  From the left-hand menu, select **Processes**.

You can view the status of all running and completed processes in your workspace.


![](/images/docs/pipes/workspace_process_list.png)

You can filter the list of processes using a query filter.  Click the **Query** dropdown to select a pre-defined filter, or enter your own using the [Pipes query filter syntax](/pipes/docs/reference/query-filter#syntax).


![](/images/docs/pipes/workspace_process_list_filtered.png)


Click on a process to view the detail. The process detail displays the status, which user initiated it the full detailed logs, with expandable and copyable data where available.

![](/images/docs/pipes/process_detail.png)

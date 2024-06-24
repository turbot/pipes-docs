---
title: Usage
sidebar_label: Usage
---

# Usage

Pipes provides **Usage** information to help you view and understand your workspace usage, including used storage, compute time, and the number of users in your tenant/organization/user. 

Because Pipes is billed based on your usage, understanding usage is
an essential aspect of managing and optimizing your resources effectively. By monitoring these metrics, you can ensure that your workspace operates efficiently and meets the needs of your tenant/organization/user in a cost-effective manner.

## Tenant / Organization / User Usage

To view summary usage for your tenant/organization/user, go to the **Settings** page for your tenant/organization/user and click **Usage** from the left
hand menu.

The **Stats** page provides visibility into the compute, storage, and user (if in a tenant/organization) usage for your tenant/organization/user.  At the top of the page, you can see your estimated month to date charges and a summary of your usage thresholds.

<img src="/images/docs/pipes/usage_stats_summary.png" width="400pt"/>




The **Daily Usage** provides a summary of your usage for the current day, including the current count of users, the total storage across all workspaces, and the total compute minutes for the current day.

<img src="/images/docs/pipes/usage_daily_usage.png" width="400pt"/>



Charts for the 3 usage dimension appear below.  You can select the date range for these charts.  By default, the **Current Billing Cycle** is shown, but you may instead select a different date range.  The dashed line on each chart represents the included capacity for ath metric in your plan.  Hover over any bar in a chart to see the usage breakdown for that day.

<br />

<img src="/images/docs/pipes/usage_org_compute.png" width="400pt"/>

The **Compute (mins)** chart shows you your cumulative compute usage as well as your compute usage for each day in the specified date range, broken down by type:
- **Database Compute** includes time spent running all workspace database instances.  This includes any time running queries, as well as the 5 minute idle timeout.
- **Process Compute** includes time running all pipeline processes such as scheduled snapshots and Datatank updates.


<br />

<img src="/images/docs/pipes/usage_org_storage.png" width="400pt"/>

The **Storage (GB)** chart details your total in-use storage capacity per day, broken down by type:
- **Database Storage** represents the sum of the size of all workspace database volumes.
- **Process Logs** is the sum of all process logs for all workspaces.
- **Snapshot Storage** is the sum of all snapshots for all workspaces.


<br />
<img src="/images/docs/pipes/usage_org_users.png" width="400pt"/>

The **Users** charts shows the total number of users in your tenant/organization as of each day.


## Workspace Usage
<img src="/images/docs/pipes/pipes_workspace_usage.png" width="400pt"/>
<br />

You can view your usage for a single workspace.  At the top of the page, you can see your **Daily usage**, including the current count of users, the storage for the workspace, and the compute minutes for the current day.

Charts for the workspace usage dimensions appear below.  You can select the date range for these charts.  By default, the **Current Billing Cycle** is shown, but you may instead select a different date range.  Hover over any bar in a chart to see the usage breakdown for that day.

The **Compute (mins)** chart shows you your cumulative compute usage as well as your compute usage for each day in the specified date range, broken down by type:
- **Database Compute** includes time spent running the workspace database instance.  This includes any time running queries, as well as the 5 minute idle timeout.
- **Process Compute** includes time running all pipeline processes such as scheduled snapshots and Datatank updates.

The **Storage (GB)** chart details your total in-use storage capacity per day, broken down by type:
- **Database Storage** represents the size of the workspace database volume.
- **Process Logs** is the sum of all process logs for the workspace.
- **Snapshot Storage** is the sum of all snapshots for the workspace.

For more information, please see the [Pipes pricing page](/pipes/pricing).
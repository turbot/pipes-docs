---
title: Usage
sidebar_label: Usage
---

# Workspace Usage

Pipes provides **Usage** information to help you view and understand your workspace usage, including used storage and compute time. 

Because Pipes is billed based on your usage, understanding usage is
an essential aspect of managing and optimizing your resources effectively. By monitoring these metrics, you can ensure that your workspace operates efficiently ands cost-effectively.



## Viewing Worskpace Usage

You can view your usage from the **Advanced** tab of your workspace. 

<img src="/images/docs/pipes/pipes_workspace_usage.png" width="400pt"/>
<br />

At the top of the page, you can see your **Daily usage**, including the current count of users, the storage for the workspace, and the compute minutes for the current day.

Charts for the workspace usage dimensions appear below.  You can select the date range for these charts.  By default, the **Last 30 days** is shown, but you may instead select a different date range.  Hover over any bar in a chart to see the usage breakdown for that day.

The **Compute (mins)** chart shows you your cumulative compute usage as well as your compute usage for each day in the specified date range, broken down by type:
- **Database Compute** includes time spent running the workspace database instance.  This includes any time running queries, as well as the 5 minute idle timeout.
- **Process Compute** includes time running all pipeline processes such as scheduled snapshots, Flowpipe pipelines & triggers, and Datatank updates.

The **Storage (GB)** chart details your total in-use storage capacity per day, broken down by type:
- **Database Storage** represents the size of the workspace database volume.
- **Process Logs** is the sum of all process logs for the workspace.
- **Snapshot Storage** is the sum of all snapshots for the workspace.

For more information, please see the [Pipes pricing page](/pipes/pricing).
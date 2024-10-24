---
title: Activity
sidebar_label: Activity
---

# Activity

The **Activity** tab for your tenant tab provides visibility into the events that occur in your tenant.  

## Audit Log

The **Audit Log** provides a log of API activity associated with your tenant including _who_ did _what_ and _when_.

To view the audit log for your tenant, navigate to your tenant, then click the double arrow button from the navigation at the top of the page and select **Tenant Settings** from the dropdown.  Go to the **Activity** tab for your tenant and select **Audit Log** from the left-hand menu.

![](/images/docs/pipes/tenant_audit_log.png)
<br />


## Processes


Many Turbot Pipes APIs perform tasks asynchronously. These tasks include one-time requests (install a mod into a workspace), and recurring system tasks (update the workspace container image and plugins every week). **Processes** provide visibility into these activities.

To view the audit log for your tenant, navigate to your tenant, then click the double arrow button from the navigation at the top of the page and select **Tenant Settings** from the dropdown.  Go to the **Activity** tab for your tenant and select **Processes** from the left-hand menu.

You can view the status of all running and completed processes in your tenant.


![](/images/docs/pipes/tenant_process_list.png)

You can filter the list of processes using a query filter.  Click the **Query** dropdown to select a pre-defined filter, or enter your own using the [Pipes query filter syntax](/pipes/docs/reference/query-filter#syntax).


![](/images/docs/pipes/tenant_process_list_filtered.png)


Click on a process to view the detail. The process detail displays the status, which user initiated it the full detailed logs, with expandable and copyable data where available.

<!--
![](/images/docs/pipes/process_detail.png)

-->
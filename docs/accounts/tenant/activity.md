---
title: Activity
sidebar_label: Activity
---

# Activity

The **Activity** tab for your tenant tab provides visibility into the events that occur in your tenant.  

## Audit Log

The **Audit Log** provides a log of API activity associated with your tenant, including _who_ did _what_ and _when_.

To view the audit log for your tenant, navigate to your tenant, then click the double arrow button from the navigation at the top of the page and select **Tenant Settings** from the dropdown.  Go to the **Activity** tab for your tenant and select **Audit Log** from the left-hand menu.

![](/images/docs/pipes/tenant_audit_log.png)
<br />


## Processes


Many Turbot Pipes APIs perform tasks asynchronously. These tasks include one-time requests (install a mod into a workspace) and recurring system tasks (update the workspace container image and plugins every week). **Processes** provide visibility into these activities.

To view the audit log for your tenant, navigate to your tenant, then click the double arrow button from the navigation at the top of the page and select **Tenant Settings** from the dropdown.  Go to the **Activity** tab for your tenant and select **Processes** from the left-hand menu.

You can view the status of all running and completed processes in your tenant.


![](/images/docs/pipes/tenant_process_list.png)

You can filter the list of processes using a query filter.  Click the **Query** dropdown to select a pre-defined filter, or enter your own using the [Pipes query filter syntax](/pipes/docs/reference/query-filter#syntax).


![](/images/docs/pipes/tenant_process_list_filtered.png)


Click on a process to view the process detail page. The process detail page displays the status, the user that initiated it, and the full detailed logs with expandable and copyable data where available.

<!--
![](/images/docs/pipes/process_detail.png)

-->

## Archives

The **Archives** page provides a table to list, download and delete any [log archives](/pipes/docs/accounts/tenant/log-archives) you have stored for the tenant.

To view the log archives for your tenant, navigate to your tenant, then click the double arrow button from the navigation at the top of the page and select **Tenant Settings** from the dropdown.  Go to the **Activity** tab for your tenant and select **Archives** from the left-hand menu.

![](/images/docs/pipes/tenant_activity_archives.png)

You can filter the list of archives using a query filter.  Click the **Query** dropdown to select a pre-defined filter, or enter your own using the [Pipes query filter syntax](/pipes/docs/reference/query-filter#syntax).

Click on the download icon to download an existing archive.

You can remove archives which are no longer required by selecting the **Delete** action on the options menu button ('three dots' button). You must confirm deletion via the modal dialog that appears.
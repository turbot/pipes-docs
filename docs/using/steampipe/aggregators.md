---
title:  Aggregators
sidebar_label: Aggregators
---


#  Aggregators
An **[Aggregator](https://steampipe.io/docs/managing/connections#using-aggregators)** allows you to query data from *multiple* connections as if they are a single connection. For example, using aggregators, you can query multiple AWS accounts from a single table.  Unlike connections, aggregators cannot be defined at the identity level or shared across workspaces - they can only be created at the workspace level.


Pipes will automatically create aggregators whenever you have 2 or more connections of a given plugin type.  These system-generated aggregators are configured to include all connections for the plugin, and they are placed before the connections in the default [search_path](https://steampipe.io/docs/guides/search-path).  This means that unqualified queries will use the aggregator, so your default view includes data from all connections.  The system-generated aggregators are named `all_{plugin}` (e.g. `all_aws`) and you cannot modify or delete them.

You can also create your own aggregators, with your own matching rules.


## Adding & Removing Aggregators

To manage the aggregators for your workspace, navigate to your workspace, then select Steampipe from the **Pipes** tab, then select the **Aggregators** tab.

![](/images/docs/pipes/steampipe/steampipe_aggregators_list.png)

You will see a list of aggregators for the workspace. Click on an aggregator to view it. The **Connections** tab will list the connections that are currently included in the aggregator. You can change the handle or the included connections of the aggregator from the **Settings** tab.   

<img src="/images/docs/pipes/cloud-connections-edit-aggregator.png" width="400pt"/>
<br />


To create a new aggregator, click the **New Aggregator** button. Select the **Plugin** whose connections to aggregate.  By default, only the plugins for which you currently have connection schemas will be displayed.  Select a plugin.  Next, enter a **Handle** for the aggregator.  The handle will be used as the schema name, and it must be unique in the workspace.  Next, choose the **Connections** that you want to include in the aggregator. 

<img src="/images/docs/pipes/cloud-connections-create-aggregator.png" width="400pt"/>
<br />

You can choose **All Connections** to target all existing and future Amazon Web Services connections that are in the workspace schema, but the Pipes-managed `all_{plugin}` aggregator already does this.  You can instead choose **Match Connections** to target specific connections in the workspace schema (existing and future) by name or wildcard (*). 

<img src="/images/docs/pipes/cloud-connections-match-aggregator.png" width="400pt"/>
<br />


Finally, select **Add to workspace schema automatically** to attach the aggregator schema to the workspaces.  Click **Create Aggregator**.

To delete an aggregator, find the one you wish to delete and click its handle or the cog icon to go to the aggregator detail page.  On the **Settings** tab for the aggregator, click **Delete aggregator** to permanently remove this aggregator. You will be prompted to confirm deletion. Enter the aggregator's handle and click **Delete**.  ***This action is not reversible.*** 

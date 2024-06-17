---
title:  Aggregators
sidebar_label: Aggregators
---


#  Aggregators
An **[Aggregator](https://steampipe.io/docs/managing/connections#using-aggregators)** allows you to query data from *multiple* connections as if they are a single connection. For example, using aggregators, you can query multiple AWS accounts from a single table.  Unlike connections, aggregators cannot be defined at the identity level or shared across workspaces - they can only be created at the workspace level.

When you add a connection to a workspace in Pipes, you will be prompted to create an aggregator if you have 2 or more connections of the plugin type and you don't already have an aggregator.

In the below screenshot we're adding a second `Net` connection to the workspace named `all_net`. By default Pipes will suggest creating an aggregator that targets all `Net` connections in the workspace.

This will mean that as more `Net` connections are added to the workspace, they will automatically be included in the `all_net` aggregator.

<img src="/images/docs/pipes/cloud-connections-create-aggregator.png" width="400pt"/>
<br />

If you don't want to include all connections, you can match using wildcards. In the below screenshot we've added `net*`, which will match all connections that start with `net`. We also allow you to choose from the existing connections in the workspace to target specific ones.  

<img src="/images/docs/pipes/cloud-connections-match-aggregator.png" width="400pt"/>
<br />

To access the aggregators, navigate to your workspace and go to **Settings** > **Connections**. You will see a list of connections and aggregators for the workspace. Click on an aggregator to view it. The **Connections** tab will list the connections that are currently included in the aggregator. You can change the matching rules of the aggregator by clicking **Manage connections** and entering your desired connections. We will give you an indication of how many connections have been matched by the proposed config. Once happy, click **Update**.

<img src="/images/docs/pipes/cloud-connections-edit-aggregator.png" width="400pt"/>
<br />


## Adding & Removing Aggregators


You can add and remove connections from the **Settings** tab for your workspace.
Navigate to your workspace, go to the **Settings** tab, then click
**Connections** from the menu on the left to see a list the connections that are
currently attached to the workspace. Click the **Add Connection** button to add
a connection to your workspace. To remove the connection from a workspace, click
the options menu ('three dots' button) to
the right of the connection, select **Remove** from the menu.

Alternatively, you can attach connections to your workspace from the
**Connections** tab for your developer account or organization. Navigate to your user
account or organization, and click **Connections**. You will see a list of
connections. Click on a connection in the list to view it. The **Workspaces**
tab will list the workspaces that are currently using the connection. You can
attach the connection to another workspace with the **Add to Workspace** button.
To remove the connection from a workspace, click the options menu ('three dots' button) to the right of the workspace,
select **Remove** from the menu.



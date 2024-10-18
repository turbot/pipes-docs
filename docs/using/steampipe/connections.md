---
title:  Connections
sidebar_label: Connections
---

# Connections

Before you can use Steampipe you need to add 1 or more [connections](/pipes/docs/workspaces/connections) and [add its schema](#adding-a-connection-schema) to the database.  

In Steampipe, a [connection](https://steampipe.io/docs/managing/connections) represents a set of tables for a **single data source**.  In order to query data, you'll need at least one connection, as the other schema types depend on connections to provide credentials and other configuration information. Connections may defined at the workspace level, or they may be created and shared by a [tenant](/pipes/docs/tenants/connections) or [organization](/pipes/docs/org-connections) and then attached to workspaces.



## Adding a Connection Schema
You may [create a connection](/pipes/docs/workspaces/connections) at the tenant, organization, or workspace level, but you can only add the schema to Steampipe at the **workspace level**.  

To add a schema for an existing connection, navigate to your workspace, and then to the **Connections** tab.  Find the schema that you wish to add and click **Add to Schema**.

![](/images/docs/pipes/steampipe/steampipe_schemas_add_remove.png)


To add schemas for all connections in a folder, navigate to your workspace, and then to the **Connections** tab.  Find the folder whose schemas you wish to add and click **Add to Schema**.

You can also create new connections for your workspace from the **Connections** tab.  When creating a new connection, you can choose to  **Add to Steampipe schema automatically** during creation to create the connection and add the schema in a single step


## Removing a Connection Schema

To remove a schema, navigate to your workspace, and then to the **Connections** tab.  Find the schema or folder that you wish to remove and click **Remove from Schema**.  Note that if a connection schema was added indirectly by adding the parent folder, you cannot remove the connection schema individually; you must remove the folder.


<!--


There are 3 types of schemas in Turbot Pipes.

A [Connection](connections) represents a set of tables for a **single data source**.  In order to query data, you'll need at least one connection, as the other connection types depend on connections to provide credentials and other configuration information. Connections may defined at the workspace level, or they may be created on a [tenant](/pipes/docs/tenants/connections) or [organization](/pipes/docs/org-connections) and then [attached to workspaces](/pipes/docs/connections#adding-schemas) - they can be shared by multiple workspaces within the account or organization. 

An [Aggregator](aggregators) allows you to query data from **multiple connections** as if they are a single connection. For example, using aggregators, you can query multiple AWS accounts from a single table.  Unlike connections, aggregators cannot be defined at the tenant or organization level or shared across workspaces - they can only be created at the workspace level.

A [Datatank](datatank) provides a mechanism to proactively query connections on a schedule and **store the results**. You can then query the stored results instead of the 'live' schemas, resulting in reduced query latency (at the expense of data currency). Datatank is a paid Turbot Pipes feature and is not available in the free Developer plan.  Like aggregators, datatanks cannot be defined at the tenant or organization level or shared across workspaces - they can only be created at the workspace level.


-->
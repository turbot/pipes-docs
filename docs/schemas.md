---
title: Schemas
sidebar_label: Schemas
---

# Schemas

There are 3 types of schemas in Turbot Pipes.

A [Connection](https://steampipe.io/docs/managing/connections) represents a set of tables for a **single data source**.  In order to query data, you'll need at least one connection, as the other connection types depend on connections to provide credentials and other configuration information. Connections are defined at the identity (developer account or organization) level and then attached to workspaces - they can be shared by multiple workspaces within the account or organization. 

An [Aggregator](https://steampipe.io/docs/managing/connections#using-aggregators) allows you to query data from **multiple connections** as if they are a single connection. For example, using aggregators, you can query multiple AWS accounts from a single table.  Unlike connections, aggregators cannot be defined at the identity level or shared across workspaces - they can only be created at the workspace level.

A [Datatank](datatank) provides a mechanism to proactively query connections on a schedule and **store the results**. You can then query the stored results instead of the 'live' schemas, resulting in reduced query latency (at the expense of data currency). Datatank is a paid Turbot Pipes feature and is not available in the free Developer plan.  Like aggregators, datatanks cannot be defined at the identity level or shared across workspaces - they can only be created at the workspace level.

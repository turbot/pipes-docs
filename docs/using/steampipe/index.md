---
title: Steampipe
sidebar_label: Steampipe
---

# Steampipe

Your workspace includes a hosted [Steampipe](https://steampipe.io) database.  Steampipe exposes APIs and services as a high-performance relational database, enabling you to write SQL-based queries to explore dynamic data.

Your Steampipe instance is built on PostgreSQL and it is available via a publicly available endpoint, allowing you to connect from a remote Steampipe, Powerpipe, or Flowpipe client, or from many other [third-party tools](https://turbot.com/pipes/docs/connect).

Your Steampipe database is accessible from all the pipes in your workspace. You can query your Steampipe database from the Turbot Pipes web console, share snapshots of your queries, and even run snapshots on a schedule. You can visualize your data with Powerpipe benchmarks and dashboards, and query the database in your Flowpipe pipelines.   

You can accelerate your queries with a Datatank. With Datatank, you can proactively query connections at regular intervals and store the results in a persistent schema.You can then query the stored results instead of the live schemas, resulting in reduced query latency (at the expense of data freshness).




## Steampipe Database Search Path

Your workspace includes a Steampipe database, and this database may include many [schemas](/pipes/docs/schemas).  When querying the database, any unqualified table names are resolved using the schema [search path](https://steampipe.io/docs/guides/search-path).  Mods are written using unqualified names, which allows you to target specific [datatanks](/pipes/docs/datatank), [connections](/docs/connections), and [aggregators](/pipes/docs/aggregators).  Pipes is opinionated on the search path, because *usually* you want to use a table from the datatank if it exists, otherwise an aggregator if one exists, otherwise a connection.

By default, Pipes builds the search path as follows:
1. The `public` schema
2. Datatank schemas, alphabetically
2. Aggregator schemas, alphabetically
2. Connection schemas, alphabetically

Usually, this is the desired order, however you can set a default [search path prefix](https://steampipe.io/docs/guides/search-path#search-path-prefix) if you want to customize the search path

You can set the prefix from the **Advanced** / **Workspace** page for your workspace.


![](/images/docs/pipes/pipes_workspace_search_path.png)

The active default search path is displayed.  To add or change the prefix, click **edit**, select the schemas from the list, in the order you would like them to appear, then click **Save**.

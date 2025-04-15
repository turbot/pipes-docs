---
title: Connect to Turbot pipes from pgAdmin
sidebar_label: pgAdmin
---

# Connect to Turbot pipes from pgAdmin

[pgAdmin](https://www.pgadmin.org/) is an open-source administration and development platform for PostgreSQL databases.

Steampipe provides a single interface to all your cloud, code, logs and more. Because it's built on Postgres, Steampipe provides an endpoint that any Postgres-compatible client -- including pgAdmin -- can connect to.

You can get the information needed to connect to your Turbot Pipes database instance from the **[Developers](/pipes/docs/using/steampipe/developers)** tab on the **Steampipe** page for your workspace.  

![](/images/docs/pipes/steampipe/pipes_steampipe_developer_database.png)

Once Turbot pipes is successfully connected, you can explore the tables provided by the Steampipe plugins, run queries and build reports.

Similarly, you can also connect pgAdmin to [Steampipe CLI](https://steampipe.io/downloads). To do that, run `steampipe service start --show-password` and use the displayed connection details.

```
Steampipe service is running:

Database:

  Host(s):            localhost, 127.0.0.1, 192.168.29.204
  Port:               9193
  Database:           steampipe
  User:               steampipe
  Password:           99**_****_**8c
  Connection string:  postgres://steampipe:99**_****_**8c@localhost:9193/steampipe
```

## Getting started

[pgAdmin](https://www.pgadmin.org/download/) is free and available to use on the desktop.

To create a connection choose `Register - Server` under Object. Then add the connection details and keep the SSL mode as `Preferred`.

<div style={{"marginTop":"1em", "marginBottom":"1em", "width":"90%"}}>
<img src="/images/docs/pipes/pgadmin-conection-success.png" />
</div>

Once you've connected to Turbot pipes, you can access the plugins and its tables from the object explorer.

<div style={{"marginTop":"1em", "marginBottom":"1em", "width":"90%"}}>
<img src="/images/docs/pipes/pgadmin-object-explorer.png" />
</div>

Here we select the `hackernews_top` table from the [Hacker News Plugin](https://hub.steampipe.io/plugins/turbot/hackernews). pgAdmin displays the table's schema and previews the data which can be exported into a CSV file.

<div style={{"marginTop":"1em", "marginBottom":"1em", "width":"90%"}}>
<img src="/images/docs/pipes/pgadmin-data-preview.png" />
</div>

## Create a chart with custom query

Here we will focus on creating a chart to analyze Tesla's hourly price history using the [Finance Plugin](https://hub.steampipe.io/plugins/turbot/finance). To begin, click `Query Tool`, paste this query in the command palette, then click `Execute/Refresh`.

```
select
  timestamp,
  close
from
  finance_quote_hourly
where
  symbol = 'TSLA'
order by
  timestamp desc
```

pgAdmin previews the data in the table form. Now click on the `Graph Visualiser` icon to open the visualize data form and select Type as `Stacked Bar Chart`. Update the X asxis with `close` and Y axis with `timestamp`, click `Generate` to display the chart with the data.

<div style={{"marginTop":"1em", "marginBottom":"1em", "width":"90%"}}>
<img src="/images/docs/pipes/pgadmin-graph-visualiser.png" />
</div>

## Summary

With pgAdmin and Turbot pipes you can:

- View tables in your Turbot pipes workspace

- Write custom queries to preview data from the tables in your Turbot pipes workspace

- Create charts driven by your custom queries

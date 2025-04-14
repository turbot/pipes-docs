---
title: Connect to Turbot Pipes from HeidiSQL
sidebar_label: HeidiSQL
---

# Connect to Turbot Pipes from HeidiSQL

[HeidiSQL](https://www.heidisql.com/) is a database tool to query, edit and
manage your databases.

Steampipe provides a single interface to all your cloud, code, logs and more.
Because it's built on Postgres, Steampipe provides an endpoint that any
Postgres-compatible client -- including HeidiSQL -- can connect to.

You can get the information needed to connect to your Turbot Pipes database instance from the **Developers** tab on the **Steampipe** page for your workspace.  

![](/images/docs/pipes/steampipe/pipes_steampipe_developer_database.png)

Once the connection to Turbot Pipes is established and tested, you can access
the tables provided by the Steampipe plugins, run queries and build reports.

You can also connect HeidiSQL to
[Steampipe CLI](https://steampipe.io/downloads). To do that, run
`steampipe service start --show-password` and use the displayed connection
details.

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

[HeidiSQL](https://www.heidisql.com/download.php) is a program that runs on
Windows. In this example we will create a Turbot Pipes connection with HeidiSQL
and query the top stories from Hacker News.

To establish a new connection click on `New` at the bottom left, select
PostgreSQL(TCP/IP) and enter the Turbot Pipes connection details, check the
`Use SSL` box under the SSL tab and click `Open`.

<div style={{"marginTop":"1em", "marginBottom":"1em", "width":"90%"}}>
<img src="/images/docs/pipes/heidisql-connection-success.png" />
</div>

Once you've connected to Turbot Pipes, you can access the Hacker News plugin and
its tables from the Database explorer.

<div style={{"marginTop":"1em", "marginBottom":"1em", "width":"50%"}}>
<img src="/images/docs/pipes/heidisql-database-explorer.png" />
</div>

Here we select the `hackernews_top` table. HeidiSQL displays the table's schema
and previews the returned data. You can drag the columns to rearrange the data,
then save to CSV, HTML, XML, LaTeX, Wiki markup or PHP.

<div style={{"marginTop":"1em", "marginBottom":"1em", "width":"90%"}}>
<img src="/images/docs/pipes/heidisql-hackernewstop-datapreview.png" />
</div>

## Run your first custom query

HeidiSQL provides a SQL query editor that you may use to write a custom query.
For example, we can use this query in the editor to fetch the list of top
stories with most comments.

```
select
  *
from
  hackernews_top
order by
  descendants desc
```

<div style={{"marginTop":"1em", "marginBottom":"1em", "width":"90%"}}>
<img src="/images/docs/pipes/heidisql-custom-query-response.png" />
</div>

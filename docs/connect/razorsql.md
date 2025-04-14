---
title: Connect to Turbot Pipes from RazorSQL
sidebar_label: RazorSQL
---

# Connect to Turbot Pipes from RazorSQL

[RazorSQL](https://razorsql.com/index.html) is a SQL IDE to query, edit, browse
and manage your databases.

Steampipe provides a single interface to all your cloud, code, logs and more.
Because it's built on Postgres, Steampipe provides an endpoint that any
Postgres-compatible client -- including RazorSQL -- can connect to.

You can get the information needed to connect to your Turbot Pipes database instance from the **[Developers](/pipes/docs/using/steampipe/developers)** tab on the **Steampipe** page for your workspace.  

![](/images/docs/pipes/steampipe/pipes_steampipe_developer_database.png)

Once the connection to Turbot Pipes is established and tested, you can access
the tables provided by the Steampipe plugins, run queries and build reports.

You can also connect RazorSQL to
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

[RazorSQL](https://razorsql.com/download.html) is available to use on the
desktop; there's a 30 day free trial. In this example we will create a Turbot
Pipes connection with RazorSQL and query the best stories from Hacker News.

To establish a new connection click on `Connect to a Database`, select
PostgreSQL and click `Continue`. Enter the Turbot Pipes connection details, and
click `Connect`.

<div style={{"marginTop":"1em", "marginBottom":"1em", "width":"90%"}}>
<img src="/images/docs/pipes/razorsql-connection-success.png" />
</div>

Once you've connected to Turbot Pipes, you can access the Hacker News plugin and
its tables from the database navigator.

<div style={{"marginTop":"1em", "marginBottom":"1em", "width":"50%"}}>
<img src="/images/docs/pipes/razorsql-database-navigator.png" />
</div>

Here we select the `hackernews_best` table. RazorSQL displays the table's schema
and previews the data.

<div style={{"marginTop":"1em", "marginBottom":"1em", "width":"90%"}}>
<img src="/images/docs/pipes/razorsql-hackernews-best-preview.png" />
</div>

## Run your first custom query

RazorSQL provides a SQL editor that you may use to write custom queries.
However, it requires the Schema name and the Database name to be prefixed before
the table name. Here is a query to fetch new stories by score.

```
select
  *
from
  <DatabaseName>.hackernews.hackernews_new
order by
  score desc
```

<div style={{"marginTop":"1em", "marginBottom":"1em", "width":"90%"}}>
<img src="/images/docs/pipes/razorsql-custom-query-preview.png" />
</div>

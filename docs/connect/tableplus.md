---
title: Connect to Turbot Pipes from TablePlus
sidebar_label: TablePlus
---

# Connect to Turbot Pipes from TablePlus

[TablePlus](https://tableplus.com/) is a SQL IDE to query, edit and manage your
databases.

Steampipe provides a single interface to all your cloud, code, logs and more.
Because it's built on Postgres, Steampipe provides an endpoint that any
Postgres-compatible client -- including TablePlus -- can connect to.

You can get the information needed to connect to your Turbot Pipes database instance from the **[Developers](/pipes/docs/using/steampipe/developers)** tab on the **Steampipe** page for your workspace.  

![](/images/docs/pipes/steampipe/pipes_steampipe_developer_database.png)

Once the connection to Turbot Pipes is established and tested, you can access
the tables provided by the Steampipe plugins, run queries and build reports.

You can also connect TablePlus to
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

[TablePlus](https://tableplus.com/download) is available on the desktop and the
free version can be used without any need for account creation. In this example
we will create a Turbot Pipes connection with TablePlus and query the AWS EC2
SSL policies.

To establish a new connection click on `Create a new connection`, select
PostgreSQL and click `Create`. Enter the Turbot Pipes connection details, keep
the SSL mode (`Preferred`), and click `Test` to verify the connection.

<div style={{"marginTop":"1em", "marginBottom":"1em", "width":"90%"}}>
<img src="/images/docs/pipes/tableplus-connection-success.png" />
</div>

Once you've connected to Turbot Pipes, you can access the AWS plugin and its
tables from the namespace provided at the bottom left of the window.

<div style={{"marginTop":"1em", "marginBottom":"1em", "width":"50%"}}>
<img src="/images/docs/pipes/tableplus-namespace-select.png" />
</div>

Here we select the `aws_ec2_ssl_policy` table. TablePlus displays the table's
schema and previews the data. You may also choose to export the data to CSV,
JSON or SQL.

<div style={{"marginTop":"1em", "marginBottom":"1em", "width":"90%"}}>
<img src="/images/docs/pipes/tableplus-ec2-ssl-data-preview.png" />
</div>

## Run your first custom query

TablePlus comes with a SQL query editor that you may use to write a custom
query. For example, we can use this query in the editor to fetch the S3 buckets
with default encryption disabled

```
select
  name,
  region,
  server_side_encryption_configuration
from
  aws_s3_bucket
where
  server_side_encryption_configuration is null;
```

<div style={{"marginTop":"1em", "marginBottom":"1em", "width":"90%"}}>
<img src="/images/docs/pipes/tableplus-custom-query-results.png" />
</div>

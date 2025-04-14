---
title: Connect to Turbot Pipes from DataGrip
sidebar_label: DataGrip
---

# Connect to Turbot Pipes from DataGrip

[DataGrip](https://www.jetbrains.com/datagrip/) is a cross-platform SQL IDE to
query, edit and manage your databases.

Steampipe provides a single interface to all your cloud, code, logs and more.
Because it's built on Postgres, Steampipe provides an endpoint that any
Postgres-compatible client -- including DataGrip -- can connect to.

You can get the information needed to connect to your Turbot Pipes database instance from the **[Developers](/pipes/docs/using/steampipe/developers)** tab on the **Steampipe** page for your workspace.  

![](/images/docs/pipes/steampipe/pipes_steampipe_developer_database.png)

Once the connection to Turbot Pipes is established and tested, you can explore
the tables provided by the Steampipe plugins, run queries and build reports.

You can also connect DataGrip to
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

[DataGrip](https://www.jetbrains.com/datagrip/download/#section=mac) is
available to use on the desktop; there's a 30-day trial. In this example we will
create a Turbot Pipes connection from DataGrip and query the AWS availability
zones.

To create a new connection click on `New` and add a PostgreSQL data source.
Click `Download missing driver files` at the bottom of the settings page, since
DataGrip does not include bundled drivers required to interact with the
database. Enter the Turbot Pipes connection details and click `Test Connection`
to `Verify`.

<div style={{"marginTop":"1em", "marginBottom":"1em", "width":"90%"}}>
<img src="/images/docs/pipes/datagrip-connection-success.png" />
</div>

Once you've connected to Turbot Pipes, you can access the AWS plugin and its
tables from the Database explorer.

<div style={{"marginTop":"1em", "marginBottom":"1em", "width":"50%"}}>
<img src="/images/docs/pipes/datagrip-database-explorer.png" />
</div>

Here we select the `aws_availability_zone` table. DataGrip displays the table's
schema and previews the data. You can drag the columns to organize the data and
choose to export the data to a
[variety of formats](https://steampipe.io/docs/reference/cli/check#output-formats).

<div style={{"marginTop":"1em", "marginBottom":"1em", "width":"90%"}}>
<img src="/images/docs/pipes/datagrip-availability-zone-result.png" />
</div>

## Run your first custom query

DataGrip provides an editor that you may use to write custom queries. Here is a
query to fetch the list of encrypted EBS volumes.

```
select
  volume_id,
  encrypted,
  volume_type,
  region,
  availability_zone
from
  aws_ebs_volume
where
  encrypted;
```

<div style={{"marginTop":"1em", "marginBottom":"1em", "width":"90%"}}>
<img src="/images/docs/pipes/datagrip-custom-query-result.png" />
</div>

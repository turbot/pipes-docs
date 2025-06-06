---
title: Connect to Turbot Pipes from DBeaver
sidebar_label: DBeaver
---

# Connect to Turbot Pipes from DBeaver

[DBeaver](https://dbeaver.io/) is a universal database tool to query, edit and
manage your databases.

Steampipe provides a single interface to all your cloud, code, logs and more.
Because it's built on Postgres, Steampipe provides an endpoint that any
Postgres-compatible client -- including DBeaver -- can connect to.

You can get the information needed to connect to your Turbot Pipes database instance from the **[Developers](/pipes/docs/using/steampipe/developers)** tab on the **Steampipe** page for your workspace.  

![](/images/docs/pipes/steampipe/pipes_steampipe_developer_database.png)

Once the connection to Turbot Pipes is established and tested, you can access
the tables provided by the Steampipe plugins, run queries and build reports.

You can also connect DBeaver to [Steampipe CLI](https://steampipe.io/downloads).
To do that, run `steampipe service start --show-password` and use the displayed
connection details.

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

[DBeaver](https://dbeaver.io/download/) Community is open source and free to use
on the desktop, while the pro version can be purchased. In this example we will
create a Turbot Pipes connection with DBeaver and query the AWS S3 buckets.

To establish a new connection click on `New Database Connection`, select
PostgreSQL and click `Next`. If prompted, Click `Download Drivers` to update the
missing drivers required to interact with the database. Enter the Turbot Pipes
connection details and click `Test Connection` to verify.

<div style={{"marginTop":"1em", "marginBottom":"1em", "width":"90%"}}>
<img src="/images/docs/pipes/dbeaver-connection-success.png" />
</div>

Once you've connected to Turbot Pipes, you can access the AWS plugin and its
tables from the Database navigator.

<div style={{"marginTop":"1em", "marginBottom":"1em", "width":"50%"}}>
<img src="/images/docs/pipes/dbeaver-database-navigator.png" />
</div>

Here we select the `aws_s3_bucket` table. DBeaver displays the table's schema
and previews the returned data. You can drag the columns to re-arrange the data
and also export it to a wide range of formats like CSV, JSON, SQL, TXT, XML,
etc.

<div style={{"marginTop":"1em", "marginBottom":"1em", "width":"90%"}}>
<img src="/images/docs/pipes/dbeaver-bucket-query-result.png" />
</div>

## Run your first custom query

DBeaver provides a SQL query editor that you may use to write a custom query.
For example, we can use this query in the editor to fetch the list of AWS EC2
instance types available in us-east-1 region.

```
select
  instance_type,
  location
from
  aws_ec2_instance_availability
where
  location = 'us-east-1';
```

<div style={{"marginTop":"1em", "marginBottom":"1em", "width":"90%"}}>
<img src="/images/docs/pipes/dbeaver-custom-query-result.png" />
</div>

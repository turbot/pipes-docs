---
title: Connect to Turbot Pipes with psql
sidebar_label: psql
---

# Connect to Turbot Pipes with psql

Since your Turbot Pipes workspace is just a PostgreSQL database, you can use
`psql` to query your workspace database.

You can get the information needed to connect to your Turbot Pipes database instance from the **[Developers](/pipes/docs/using/steampipe/developers)** tab on the **Steampipe** page for your workspace.  On the **Developers** tab, click **Postgres CLI** from the sidebar to show the `psql` command to connect to your workspace:

![](/images/docs/pipes/steampipe/pipes_steampipe_developer_postgres.png)

Note that the connection string includes your password. It is masked in the web
console display, but you can hover over the command and click the clipboard icon
to copy it so you can paste it into your terminal.

<div style={{"marginTop":"1em", "marginBottom":"1em", "width":"90%"}}>
<img src="/images/docs/pipes/int_psql.png"/>
</div>

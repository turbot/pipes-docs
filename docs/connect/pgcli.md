---
title: Connect to Turbot Pipes with pgcli
sidebar_label: pgcli
---

# Connect to Turbot Pipes with pgcli

Since your Turbot Pipes workspace is just a PostgreSQL database, you can use `pgcli` to query your workspace database.

You can get the information needed to connect to your Turbot Pipes database instance from the **Developers** tab on the **Steampipe** page for your workspace.  On the **Developers** tab, click **Postgres CLI** from the sidebar to show the `pgcli` command to connect to your workspace:

![](/images/docs/pipes/steampipe/pipes_steampipe_developer_postgres.png)


Note that the connection string includes your password. It is masked in the web
console display, but you can hover over the command and click the clipboard icon
to copy it so you can paste it into your terminal.

<div style={{"marginTop":"1em", "marginBottom":"1em", "width":"90%"}}>
<img src="/images/docs/pipes/int_pgcli.png"/>
</div>

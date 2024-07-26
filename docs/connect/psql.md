---
title: Connect to Turbot Pipes with psql
sidebar_label: psql
---

# Connect to Turbot Pipes with psql

Since your Turbot Pipes workspace is just a PostgreSQL database, you can use
`psql` to query your workspace database.

You can get the information needed to connect to your Turbot Pipes database instance from the **Query** tab for your workspace.  On the **Query** tab, click the **info** button at the top of the query window to show the connection information.  You can get the `psql`  command from the **Terminal** tab:

![](/images/docs/pipes/query-info-connect-terminal.png)

Note that the connection string includes your password. It is masked in the web
console display, but you can hover over the command and click the clipboard icon
to copy it so you can paste it into your terminal.

<div style={{"marginTop":"1em", "marginBottom":"1em", "width":"90%"}}>
<img src="/images/docs/pipes/int_psql.png"/>
</div>

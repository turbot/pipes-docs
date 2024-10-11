---
title: Query
sidebar_label: Query
---


# Running Queries

Once you've added a connection you will be able to run
[SQL queries](https://steampipe.io/docs/sql/steampipe-sql) to explore your data, either interactively in
the console, or [via any PostgreSQL-compatible client](/pipes/docs/connect).



## Exploring Schemas

If you navigate to your workspace, then the **Query** tab, you'll see the
interactive query console.

<img src="/images/docs/pipes/cloud-query-editor.png" width="400pt"/>
<br />

From here you can either explore your schemas on the left, or dive right in and
test out your own queries in the editor. The schema list supports flexible
searching across all the tables in your schemas. For example, if you search for
`hack new`, that will find a match for the `hackernews_show_hn` table in our
`hackernews` schema.

<img src="/images/docs/pipes/cloud-query-schema-search.png" width="200pt"/>
<br />

Clicking the search result will automatically generate a query to select all the
columns from that schema table, limited to 100 rows and will automatically run
it for you.

<img src="/images/docs/pipes/cloud-query-table-results.png" width="400pt"/>
<br />

If you click the `Edit` button you can amend the query, perhaps by selecting
just the columns you're interested in, or adding a `where` clause to filter the
results. Please note that we limit queries to 5,000 rows in the interactive
query console.

<img src="/images/docs/pipes/cloud-query-custom-query.png" width="400pt"/>
<br />

## Downloading Results

After you've run a query, you can download the results to a CSV file by clicking
the **Download** button at the bottom of the query editor.



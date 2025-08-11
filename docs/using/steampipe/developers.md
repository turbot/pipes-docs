---
title:  Developers
sidebar_label: Developers
---

# Developers


Your Pipes workspace database is accessible from anywhere, thanks to its public IP address.  The **Developers** tab provides the information needed to connect to your Turbot Pipes database instance from the [Steampipe CLI](/pipes/docs/connect/cli), Postgres CLI's like [psql](/pipes/docs/connect/psql) and [pgcli](/pipes/docs/connect/pgcli), or any other [3rd party tools and utilities](/pipes/docs/connect) that support Postgres.

Note: If you're on an [Enterprise Plan](/pipes/docs/accounts/tenant#enterprise-plan) with a custom [Tenant](/pipes/docs/accounts/tenant), these features may not be available to you if disabled by your tenant administrator.

## Database

To view the developer information for your workspace, navigate to your workspace, select **Steampipe** from the Pipes tab, then select the **Developers** tab.

The **Database** info will provide general database connection details - the **Connection String**, **Host**, **Port**, **Database**, **Username** and **Password**. 

![](/images/docs/pipes/steampipe/pipes_steampipe_developer_database.png)


 Click on any field to copy it to your clipboard.  Note that the password is masked on the screen, but clicking it will add the un-redacted text to your clipboard so that you can paste it into your tool's configuration screen.  Individual users can access the database with their credentials, and the information in this view is specific to the logged-in user, enabling secure, personalized access.

## Steampipe CLI
You can also get specific [Steampipe](https://steampipe.io/) commands by clicking the **Steampipe CLI** from the sidebar:

![](/images/docs/pipes/steampipe/pipes_steampipe_developer_steampipe.png)


## Postgres CLII

You can retrieve the [psql](/pipes/docs/connect/psql) and [pgcli](/pipes/docs/connect/pgcli) commands by clicking the **Postgres CLI**.

![](/images/docs/pipes/steampipe/pipes_steampipe_developer_postgres.png)

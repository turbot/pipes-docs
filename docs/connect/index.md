---
title:  Connect to Turbot Pipes
sidebar_label: Connect
---

# Connecting to your Turbot Pipes Workspace

Turbot Pipes offers various methods to connect and query your data. Run SQL queries and save snapshot results in the [Turbot Pipes UI](/pipes/docs/queries), use the [Query API](/pipes/docs/develop/query-api) for programmatic access, or connect via a [PostgreSQL-compatible client](/pipes/docs/integrations) for leveraging your favorite tools.

## Connecting Turbot Pipes via PostgreSQL-Compatible Clients

Your Pipes workspace database is accessible from anywhere, thanks to its public IP address. Connect using the [Steampipe CLI](/pipes/docs/connect/cli) or other standard tools and utilities that support Postgres.

You can get the Postgres connection string and other database information from the **Query** tab for your workspace.  On the **Query** tab, click the **info** button at the top of the query window to show the connection information. 

![](/images/docs/pipes/query-info-connect.png)

The **Database** tab will provide general database connection details - the **Connection String**, **Host**, **Port**, **Database**, **Username** and **Password**.  Click on any field to copy it to your clipboard.  Note that the password is masked on the screen, but clicking it will add the un-redacted text to your clipboard so that you can paste it into your tool's configuration screen.  Individual users can access the database with their credentials, and the information in this view is specific to the logged in user, enabling secure, personalized access.

You can also get specific [Steampipe](https://steampipe.io/) commands from the **Steampipe CLI** tab:

![](/images/docs/pipes/query-info-connect-steampipe.png)

Or retrieve the [psql](/pipes/docs/connect/psql) and [pgcli](/pipes/docs/connect/pgcli) commands from the **Terminal** tab.

![](/images/docs/pipes/query-info-connect-terminal.png)




## Examples of Postgres-Compatable Clients
Our community leverages a diverse range of PostgreSQL clients to connect to Turbot Pipes. This flexibility accommodates different workflows, whether you prefer traditional SQL IDEs for database management, BI tools for data analysis and visualization, or [programming languages and SDKs](https://turbot.com/pipes/blog/2024/01/turbot-pipes-as-software-component) for custom integrations.

### SQL IDEs

| Tool | Description |
|------|-------------|
| [Azure Data Studio](https://turbot.com/pipes/docs/connect/azuredatastudio) | Azure Data Studio is a cross-platform database tool for data professionals. |
| [DataGrip](https://turbot.com/pipes/docs/connect/datagrip) | DataGrip is a professional SQL IDE by JetBrains, designed for database developers. |
| [DBeaver](https://turbot.com/pipes/docs/connect/dbeaver) | DBeaver is a free, multi-platform database tool for developers and database administrators. |
| [dbt](https://turbot.com/pipes/docs/connect/dbt) | dbt is a transformation tool that enables data analysts and engineers to transform data in their warehouses. |
| [Deepnote](https://turbot.com/pipes/docs/connect/deepnote) | Deepnote is a data science notebook for collaborative projects. |
| [DuckDB](https://turbot.com/pipes/docs/connect/duckdb) | DuckDB is an in-memory SQL OLAP Database Management System. |
| [Gitpod](https://turbot.com/pipes/docs/connect/gitpod) | Gitpod streamlines developer workflows with prebuilt, collaborative development environments. |
| [HeidiSQL](https://turbot.com/pipes/docs/connect/heidisql) | HeidiSQL is a powerful and easy client for MySQL, MariaDB, Microsoft SQL Server, and PostgreSQL. |
| [Jupyter](https://turbot.com/pipes/docs/connect/jupyter) | Jupyter Notebook is an open-source web application for data science and scientific computing. |
| [Navicat](https://turbot.com/pipes/docs/connect/navicat) | Navicat offers a series of graphical database management and development software. |
| [pgAdmin](https://turbot.com/pipes/docs/connect/pgadmin) | pgAdmin is a popular open-source administration and development platform for PostgreSQL. |
| [pgcli](https://turbot.com/pipes/docs/connect/pgcli) | pgcli is a command-line interface with enhanced features for Postgres. |
| [psql](https://turbot.com/pipes/docs/connect/psql) | psql is the standard command-line tool for interacting with PostgreSQL databases. |
| [RazorSQL](https://turbot.com/pipes/docs/connect/razorsql) | RazorSQL is an SQL query tool, database browser, and SQL editor for various databases. |
| [RStudio](https://turbot.com/pipes/docs/connect/rstudio) | RStudio is an IDE that uses the R language to enable users to explore, query, and visualize data. |
| [Steampipe CLI](https://turbot.com/pipes/docs/connect/cli)| Steampipe CLI is a command-line interface for managing and interacting with Turbot Pipes. |
| [TablePlus](https://turbot.com/pipes/docs/connect/tableplus) | TablePlus is a modern, native, and friendly GUI tool for relational databases. |
| [Visual Studio Code](https://turbot.com/pipes/docs/connect/vscode) | Visual Studio Code is a streamlined code editor with support for development operations. |

### BI Tools

| Tool | Description |
|------|-------------|
| [Apache Superset](https://turbot.com/pipes/docs/connect/apachesuperset) | Apache Superset is an open-source business intelligence web application. |
| [Grafana](https://turbot.com/pipes/docs/connect/grafana) | Grafana provides open-source tools for monitoring and observability. |
| [Looker](https://turbot.com/pipes/docs/connect/looker) | Looker is a business intelligence software and big data analytics platform. |
| [Metabase](https://turbot.com/pipes/docs/connect/metabase) | Metabase is an open-source way for everyone in a company to ask questions and learn from data. |
| [PowerBI](https://turbot.com/pipes/docs/connect/powerbi) | PowerBI offers a suite of business analytics tools to analyze data and share insights. |
| [Sigma](https://turbot.com/pipes/docs/connect/sigma) | Sigma is a BI and analytics application that connects to cloud data warehouses. |
| [Tableau](https://turbot.com/pipes/docs/connect/tableau) | Tableau helps people see and understand data through interactive visual analytics. |

### SDKs

| Tool | Description |
|------|-------------|
| [Golang](https://turbot.com/pipes/docs/connect/golang) | Go is an open-source programming language for building simple, reliable, and efficient software. |
| [JavaScript](https://turbot.com/pipes/docs/connect/javascript) | JavaScript is a versatile programming language, one of the core technologies of the World Wide Web. |
| [Python](https://turbot.com/pipes/docs/connect/python) | Python is a popular programming language known for its simplicity and versatility. |
| [R](https://turbot.com/pipes/docs/connect/r) | R is a programming language and environment for statistical computing and graphics. |


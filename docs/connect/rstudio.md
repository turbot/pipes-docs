---
title: Connect to Turbot Pipes with RStudio
sidebar_label: RStudio
---

# Connect to Turbot Pipes from RStudio

[RStudio](https://posit.co/products/open-source/rstudio/) is an IDE that uses
the R language to enable users to explore, query, and visualize data.

Steampipe provides a single interface to all your cloud, code, logs and more.
Because it's built on Postgres, Steampipe provides an endpoint that any
Postgres-compatible client -- including RStudio -- can connect to.

You can get the information needed to connect to your Turbot Pipes database instance from the **[Developers](/pipes/docs/using/steampipe/developers)** tab on the **Steampipe** page for your workspace.  

![](/images/docs/pipes/steampipe/pipes_steampipe_developer_database.png)

## Connect to Steampipe CLI from RStudio

To connect RStudio to [Steampipe CLI](https://steampipe.io/downloads), run
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

[RStudio](https://posit.co/download/rstudio-desktop/) is available to use on the
desktop.

To get started, Install the
[RPostgres](https://cran.r-project.org/web/packages/RPostgres/index.html)
package, specify your connection string, create a connection, then run a query.

In this example we connect from the RStudio console, load the query results and
use the [ggplot2](https://cran.r-project.org/web/packages/ggplot2/index.html)
package to chart the versioning status of AWS S3 buckets in an account.

```r
install.packages('RPostgres')
install.packages("ggplot2")
library(DBI)
library(ggplot2)
db <- 'dea4px'
host_db <- 'rahulsrivastav14-rahulsworkspace.usea1.db.steampipe.io'
db_port <- '9193'
db_user <- 'rahulsrivastav14'
db_password <- 'f3ee-****-**2a'
con <- dbConnect(RPostgres::Postgres(), dbname=db, host=host_db, port=db_port, user=db_user, password=db_password)
tbl <- dbGetQuery(con, 'select name, region, versioning_enabled from aws_s3_bucket')
summary(tbl)
ggplot(tbl, aes(versioning_enabled)) + geom_bar(stat = 'count') + labs(x = 'Versioning')
```

<img src="/images/docs/pipes/rstudio-versioning-graph.png" style={{ boxShadow: 'none' }} />

## Call the Turbot Pipes API from RStudio

You can also use the
[Turbot Pipes query API](/pipes/docs/develop/query-api).
Grab your [token](/pipes/docs/profile#tokens), put it an
environment variable like `PIPES_TOKEN`, and use this pattern.

```r
install.packages("httr")
library(httr)
response <- POST( url="https://pipes.turbot.com/api/latest/user/rahulsrivastav14/workspace/rahulsworkspace/query",
add_headers(.headers = c(
'Authorization'='Bearer {PIPES_TOKEN}',
'Content-Type' = 'application/json',
'Encoding' = "UTF-8")),
body = '{"sql":"select name, region from aws_s3_bucket limit 2"}')
content(response, "text")
```

```json
{
  "items": [
    {
      "name": "amplify-authcra-devc-deployment",
      "region": "us-east-2"
    },
    {
      "name": "appstream-app-settings-us-east-1-v01a5",
      "region": "us-east-1"
    }
  ]
}
```

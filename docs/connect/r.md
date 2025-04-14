---
title: Connect to Turbot Pipes with R
sidebar_label: R
---

# Connect to Turbot Pipes from R

Since your Turbot Pipes workspace is just a Postgres database, you can use the
standard `RPostgres` adapter to query your workspace database from R.

You can get the information needed to connect to your Turbot Pipes database instance from the **Developers** tab on the **Steampipe** page for your workspace.  

![](/images/docs/pipes/steampipe/pipes_steampipe_developer_database.png)

To get started, Install the
[RPostgres](https://cran.r-project.org/web/packages/RPostgres/index.html)
package, specify your connection string, create a connection, then run a query.

In this example we connect from the R console, load the query results, then use
its
[summary](https://www.rdocumentation.org/packages/base/versions/3.6.2/topics/summary)
function to summarize the data.

```r
install.packages('RPostgres')
library(DBI)
db <- 'dea4px'
host_db <- 'rahulsrivastav14-rahulsworkspace.usea1.db.steampipe.io'
db_port <- '9193'
db_user <- 'rahulsrivastav14'
db_password <- 'f4**-****-**2s'
con <- dbConnect(RPostgres::Postgres(), dbname=db, host=host_db, port=db_port, user=db_user, password=db_password)
tbl <- dbGetQuery(con, 'select name, region, versioning_enabled from aws_s3_bucket')
summary(tbl)
```

<img src="/images/docs/pipes/r-data-summary.png" style={{ boxShadow: 'none' }} />

## Connect to Steampipe CLI from R

To connect R to [Steampipe CLI](https://steampipe.io/downloads), run
`steampipe service start --show-password` and use the displayed connection
details.

```
Steampipe service is running:

Database:

  Host(s):            localhost, 127.0.0.1, 172.28.158.171
  Port:               9193
  Database:           steampipe
  User:               steampipe
  Password:           9a**-****-**7e
  Connection string:  postgres://steampipe:9a49-42e2-a57e@localhost:9193/steampipe
```

## Call the Turbot Pipes API from R

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

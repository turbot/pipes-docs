---
title: Connect to Turbot Pipes with JavaScript
sidebar_label: JavaScript
---

# Connect to Turbot Pipes from JavaScript

The Turbot Pipes workspace is a Postgres database, with the use of the `pg`
client you can connect and query your workspace database with JavaScript.

You can get the information needed to connect to your Turbot Pipes database instance from the **[Developers](/pipes/docs/using/steampipe/developers)** tab on the **Steampipe** page for your workspace.  

![](/images/docs/pipes/steampipe/pipes_steampipe_developer_database.png)

You'll need the Postgres client for JavaScript, which you can install using
`npm i pg` or `yarn add pg`. Then you specify the connection string, create a
connection, run a query, and fetch results. In this example, we query the state
and the region of `aws_vpc`.

```javascript
const postgres = require("pg");

const conn = {
  connectionString:
    "postgresql://rahulsrivastav14:f3**-****-**2c@rahulsrivastav14-rahulsworkspace.usea1.db.steampipe.io:9193/dea4px",
  ssl: {},
};

const pgClient = new postgres.Client(conn);
pgClient.connect();

pgClient.query("select vpc_id, region, state from aws_vpc", (err, res) => {
  if (err) console.error(err);
  console.log(res.rows);
  pgClient.end();
});
```

```json
[
  {
    "vpc_id": "vpc-0142da3508c247062e",
    "region": "us-east-1",
    "state": "available"
  },
  {
    "vpc_id": "vpc-12199f7a",
    "region": "ca-central-1",
    "state": "available"
  }
]
```

## Connect to Steampipe CLI from JavaScript

To connect JavaScript to [Steampipe CLI](https://steampipe.io/downloads), run
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

## Call the Turbot Pipes API from JavaScript

You can also use the
[Turbot Pipes query API](/pipes/docs/develop/query-api) with
the JavaScript `request` client. Grab your
[token](/pipes/docs/profile#tokens), put it an
environment variable like `PIPES_TOKEN`, and use this pattern.

```javascript
const request = require("request");
let hostname =
  "https://pipes.turbot.com/api/latest/user/rahulsrivastav14/workspace/rahulsworkspace/query";
const data = { sql: "Select is_default, region, state from aws_vpc limit 2" };
const headers = {
  Authorization: `Bearer ${process.env.PIPES_TOKEN}`,
};
request.post(
  {
    url: hostname,
    headers: headers,
    json: true,
    body: data,
  },
  function (error, response, body) {
    console.log(JSON.stringify(body));
  }
);
```

```json
{
  "items": [
    {
      "is_default": true,
      "region": "ca-central-1",
      "state": "available"
    },
    {
      "is_default": true,
      "region": "us-east-1",
      "state": "available"
    }
  ]
}
```

---
title: Connect to Turbot Pipes with Python
sidebar_label: Python
---

# Connect to Turbot Pipes from Python

Since your Turbot Pipes workspace is just a Postgres database, you can use the
standard `psycopg2` adapter to query your workspace database from Python.

You can get the information needed to connect to your Turbot Pipes database instance from the **Query** tab for your workspace.  On the **Query** tab, click the **info** button at the top of the query window to show the connection information. 

![](/images/docs/pipes/query-info-connect.png)

It's the usual drill: import
[psycopg2](https://wiki.postgresql.org/wiki/Psycopg2_Tutorial), specify your
connection string, create a connection, run a query, fetch results.

```python
import json, psycopg2
conn_str = "host='acme-jon.usea1.db.steampipe.io' dbname='o6u91f' user='judell' \
  port='9193' password='df**-****-**ee'"
conn = psycopg2.connect(conn_str)
cur = conn.cursor()
cur.execute('select name, region, account_id from aws_s3_bucket limit 2')
r = cur.fetchall()
print(json.dumps(r,indent=4))
```

```json
[
  ["10k-with-standard-kms", "us-east-2", "899206412154"],
  ["10k-with-bucket-kms", "us-east-2", "899206412154"]
]
```

If you prefer to receive a list of dictionaries, instead of tuples, use
`RealDictCursor`.

```python
import json, psycopg2, psycopg2.extras
conn_str = "host='acme-jon.usea1.db.steampipe.io' dbname='o6u91f' user='judell' \
  port='9193' password='df**-****-**ee'"
conn = psycopg2.connect(conn_str)
cur = conn.cursor(cursor_factory=psycopg2.extras.RealDictCursor)
cur.execute('select name, region, account_id from aws_s3_bucket limit 2')
r = cur.fetchall()
print(json.dumps(r,indent=4))
```

```json
[
  {
    "name": "10k-with-standard-kms",
    "region": "us-east-2",
    "account_id": "899206412154"
  },
  {
    "name": "10k-with-bucket-kms",
    "region": "us-east-2",
    "account_id": "899206412154"
  }
]
```

## Connect to Steampipe CLI from Python

To connect Python to [Steampipe CLI](https://steampipe.io/downloads), run
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

## Call the Turbot Pipes API from Python

You can also use the
[Turbot Pipes query API](/pipes/docs/develop/query-api).
Grab your [token](/pipes/docs/profile#tokens), put it an
environment variable like `PIPES_TOKEN`, and use this pattern.

```python
import json, os, requests
url = 'https://pipes.turbot.com/api/latest/org/acme/workspace/jon/query'
data = {'sql':'select name, region from aws_s3_bucket limit 2'}
token = os.environ['PIPES_TOKEN']
headers = {"Authorization": "Bearer " + token}
r = requests.post(url, headers=headers, data=data)
print(json.dumps(r.json(),indent=4))
```

```json
{
  "items": [
    {
      "name": "10k-with-bucket-kms",
      "region": "us-east-2"
    },
    {
      "name": "10k-with-standard-kms",
      "region": "us-east-2"
    }
  ]
}
```

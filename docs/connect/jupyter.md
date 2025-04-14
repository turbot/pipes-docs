---
title: Connect to Turbot Pipes with a Jupyter Notebook
sidebar_label: Jupyter Notebook
---

# Connect to Turbot Pipes from Jupyter Notebook

Since your Turbot Pipes workspace is just a Postgres database, you can use the
standard `psycopg2` adapter to query your workspace database from Python.

You can get the information needed to connect to your Turbot Pipes database instance from the **[Developers](/pipes/docs/using/steampipe/developers)** tab on the **Steampipe** page for your workspace.  

![](/images/docs/pipes/steampipe/pipes_steampipe_developer_database.png)

It's the usual drill: import
[psycopg2](https://wiki.postgresql.org/wiki/Psycopg2_Tutorial), specify your
connection string, create a connection, then run a query. (See also:
[Connect to Turbot Pipes from Python](/docs/connect/python).)

In this example we connect from an instance of Jupyter Notebook running in
VSCode, load the query results into a
<a href="https://pandas.pydata.org/docs/reference/api/pandas.DataFrame.html">pandas.DataFrame</a>,
then use its
<a href="https://pandas.pydata.org/docs/reference/api/pandas.DataFrame.describe.html">describe</a>
method to summarize the data.

<img src="/images/docs/pipes/jupyter.png" style={{ boxShadow: 'none' }} />

## Connect to Steampipe CLI from Jupyter Notebook

To connect Jupyter Notebook to [Steampipe CLI](https://steampipe.io/downloads),
run `steampipe service start --show-password` and use the displayed connection
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

## Call the Turbot Pipes API from Jupyter Notebook

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

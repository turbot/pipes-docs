---
title: Using the Turbot Pipes Query API
sidebar_label: Query API
---

# Using the Turbot Pipes Query API

## Authentication

To use the [Turbot Pipes API](/pipes/docs/reference/api), you must connect with an
[API token](/pipes/docs/accounts/developer/advanced#tokens). The examples in this section assume
that you have set the
[`PIPES_TOKEN`](https://steampipe.io/docs/reference/env-vars/PIPES_TOKEN) to a valid
API token:

```bash
export PIPES_TOKEN=tpt_c6rnjt8afakemj4gha10_svpnmxqfaketokenad431k
```

## Query Your Data

The Turbot Pipes API makes it easy query your data and integrate it into your
scripts and applications!

You can issue a simple query with a GET request:

```bash
curl -H "Authorization: Bearer ${PIPES_TOKEN}" \
  https://pipes.turbot.com/api/latest/user/foo/workspace/bar/query?sql=select+*+from+aws_s3_bucket
```

If you POST you can avoid encoding the SQL:

```bash
curl -H "Authorization: Bearer ${PIPES_TOKEN}" \
  -d 'sql=select name,arn from aws_s3_bucket' \
  https://pipes.turbot.com/api/latest/user/foo/workspace/bar/query
```

By default, the results are in JSON. You can get the results in other formats by
adding a file name with the appropriate extension to the path. You can get your
results in CSV:

```bash
curl -H "Authorization: Bearer ${PIPES_TOKEN}" \
  -d sql'=select name,arn from aws_s3_bucket' \
  https://pipes.turbot.com/api/latest/user/foo/workspace/bar/query/my-file.csv
```

Or markdown:

```bash
curl -H "Authorization: Bearer ${PIPES_TOKEN}" \
  -d sql'=select name,arn from aws_s3_bucket' \
  https://pipes.turbot.com/api/latest/user/foo/workspace/bar/query/my-file.md
```

Alternatively, you can set the content type in the `content_type` query
parameter:

```bash
curl -H "Authorization: Bearer ${PIPES_TOKEN}" \
  -d sql'=select name,arn from aws_s3_bucket' \
  https://pipes.turbot.com/api/latest/user/foo/workspace/bar/query?content_type=csv
```

Or via HTTP headers:

```bash
curl -H "Authorization: Bearer ${PIPES_TOKEN}" \
  -H "Accept: text/csv" \
  -X POST -d sql='select name,arn from aws_s3_bucket' \
  https://pipes.turbot.com/api/latest/user/foo/workspace/bar/query
```

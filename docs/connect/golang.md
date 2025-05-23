---
title: Connect to Turbot Pipes with Golang
sidebar_label: Golang
---

# Connect to Turbot Pipes from Golang

Since your Turbot Pipes workspace is a Postgres database, you can connect and
query using Go's database client.

You can get the information needed to connect to your Turbot Pipes database instance from the **[Developers](/pipes/docs/using/steampipe/developers)** tab on the **Steampipe** page for your workspace.  

![](/images/docs/pipes/steampipe/pipes_steampipe_developer_database.png)

You'll need the Postgres driver for Go's `database/sql` package, which you can
install using `go get github.com/lib/pq`. Then you specify the connection
string, create a connection, run a query, and fetch results. In this example, we
query the name, region and the versioning state of `aws_s3_bucket`.

```go
package main

import (
	"database/sql"
	"fmt"
	_ "github.com/lib/pq"
)

var db *sql.DB

func main() {
	var err error

	connStr := "postgresql://rahulsrivastav14:f3**-****-**2c@rahulsrivastav14-rahulsworkspace.usea1.db.steampipe.io:9193/dea4px"
	db, err = sql.Open("postgres", connStr)
	if err != nil {
		panic(err)
	}
	if err = db.Ping(); err != nil {
		panic(err)
	}
	rows, err := db.Query(`select name, region, versioning_enabled from aws_s3_bucket`)
	defer rows.Close()

	var name string
	var region string
	var versioning_enabled string

	for rows.Next() {
		switch err := rows.Scan(&name, &region, &versioning_enabled); err {
		case sql.ErrNoRows:
			fmt.Println("No matching rows")
		case nil:
			fmt.Println(name, region, versioning_enabled, "\n")
		default:
			panic(err)
		}
	}
}
```

```
aws-glue-temporary-986325076436-us-east-1 us-east-1 false

aws-logs-986325076436-us-east-1 us-east-1 true

turbot-986325076436-us-east-1 us-east-1 true

appstream2-36fb080bb8-us-east-1-986325076436 us-east-1 true

integratedtagsbucket2022 us-east-1 false

```

## Connect to Steampipe CLI from Golang

To connect to [Steampipe CLI](https://steampipe.io/downloads), run
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

## Call the Turbot Pipes API from Golang

You can also use the
[Turbot Pipes query API](/pipes/docs/develop/query-api) with
Go's `net/http`. Grab your
[token](/pipes/docs/profile#tokens), put it an
environment variable like `PIPES_TOKEN`, and make an HTTP request.

```go
package main

import (
	"fmt"
	"io/ioutil"
	"log"
	"net/http"
	"net/url"
	"os"
	"strings"
)

func main() {
	reqURL, _ := url.Parse("https://pipes.turbot.com/api/latest/user/rahulsrivastav14/workspace/rahulsworkspace/query")
	reqBody := ioutil.NopCloser(strings.NewReader(`{"sql": "select state, volume_id, region from aws_ebs_volume limit 2"}`))
	req := &http.Request{
		Method: "POST",
		URL: reqURL,
		Header: map[string] []string{
			"Content-Type": {"application/json"},
			"Authorization": {fmt.Sprintf("Bearer %s", os.Getenv("PIPES_TOKEN"))},
		},
		Body: reqBody,
	}
	res, err := http.DefaultClient.Do(req)
	if err != nil{
		log.Fatal("Error:", err)
	}
	defer res.Body.Close()
	body, err := ioutil.ReadAll(res.Body)
	fmt.Println(string(body))
}

```

```json
{
  "items": [
    {
      "region": "us-east-1",
      "state": "available",
      "volume_id": "vol-0e60f81e436b9bf5e"
    },
    {
      "region": "us-west-1",
      "state": "in-use",
      "volume_id": "vol-08648a6af363ccc92"
    }
  ]
}
```

---
title: Using the Turbot Pipes Go SDK
sidebar_label: Go SDK
---

# Using the Turbot Pipes Go SDK

The Go SDK for Turbot Pipes provides an interface to the Pipes API for Go
programmers.

**[GoDoc reference for github.com/turbot/pipes-sdk-go →](https://pkg.go.dev/github.com/turbot/pipes-sdk-go)**

**[View the source on Github →](https://github.com/turbot/pipes-sdk-go)**

```go
package main

import (
    "context"
    "fmt"
    "os"

    pipes "github.com/turbot/pipes-sdk-go"
)

func main() {
    // Create a default configuration
    configuration := pipes.NewConfiguration()

    // Add your Turbot Pipes user token as an auth header
    configuration.AddDefaultHeader("Authorization", fmt.Sprintf("Bearer %s", os.Getenv("PIPES_TOKEN")))

    // Create a client
    client := pipes.NewAPIClient(configuration)

    // Find your authenticated user info
    actor, _, err := client.Actors.Get(context.Background()).Execute()

    if err != nil {
      // Do something with the error
      return
    }

    // List your workspaces
    workspaces, _, err := client.UserWorkspaces.List(context.Background(), actor.Handle).Execute()

    if err != nil {
      // Do something with the error
      return
    }
}
```

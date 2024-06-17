---
title: Using the Turbot Pipes plugin for Steampipe
sidebar_label: Turbot Pipes Plugin
---

# Query Turbot Pipes API with the Pipes Plugin

The Turbot Pipes plugin makes it easy to query your Workspaces, Connections, and
other Turbot Pipes assets using Steampipe!

**[View the docs on the Hub →](https://hub.steampipe.io/plugins/turbot/pipes)**

```sql
select
  user_handle,
  org_handle,
  status
from
  pipes_organization_member
```

---
title: Connect to Turbot Pipes from the Steampipe CLI
sidebar_label: Steampipe CLI
---

# Connect to Turbot Pipes from the Steampipe CLI

You can use the [Steampipe CLI](https://steampipe.io/downloads) to query your workspace database or to run benchmarks and controls against your workspace.
You will need to create an [API token](profile#tokens), and then set the `PIPES_TOKEN` [environment variable](https://steampipe.io/docs/reference/env-vars/overview)
to authenticate:

```bash
export PIPES_TOKEN=tpt_c6f5tmpe4mv9appio5rg_3jz0a8fakekeyf8ng72qr646
```

You can get the information needed to connect to your Turbot Pipes database instance from the **[Developers](/pipes/docs/using/steampipe/developers)** tab on the **Steampipe** page for your workspace.  On the **Developers** tab, click **Steampipe CLI** from the sidebar to show the `steampipe` commands to query your workspace:

![](/images/docs/pipes/steampipe/pipes_steampipe_developer_steampipe.png)

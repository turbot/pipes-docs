---
title: Connect to Turbot Pipes from the Steampipe CLI
sidebar_label: Steampipe CLI
---

# Connect to Turbot Pipes from the Steampipe CLI

You can use the [Steampipe CLI](https://steampipe.io/downloads) to query your
workspace database, or to run benchmarks and controls against your workspace.
You will need to create an [API token](profile#tokens), and then set
the `PIPES_TOKEN` [environment variable](https://steampipe.io/docs/reference/env-vars/overview)
to authenticate:

```bash
export PIPES_TOKEN=tpt_c6f5tmpe4mv9appio5rg_3jz0a8fakekeyf8ng72qr646
```

The **Connect** tab for your workspace provides examples that you can copy,
paste and run to run an interactive query, run an interactive dashboard, or run
a benchmark against your cloud workspace!

<div style={{"marginTop":"1em", "marginBottom":"1em", "width":"90%"}}>
<img src="/images/docs/pipes/int_cli.png"/>
</div>

---
title: Instance Types
sidebar_label: Instance Types
---

# Instance Types

Pipes offers flexible compute resources through different instance types designed to match your workload requirements and budget. Each instance type is optimized for specific use cases, with compute instances handling pipeline execution and database instances running Steampipe databases. The pricing model scales with resource consumption, using cost multipliers to ensure you pay proportionally for the compute power you use.

| Instance Type   | CPU | Memory  | Persistent? | Cost Multiplier
|-----------------|-----|---------|-------------|-----------------
| c1.shared       |   2 |     4GB | No          | 1x
| db1.shared      |   2 |     4GB | No          | 1x
| db1.small       |   4 |     4GB | Yes         | 2x
| db1.medium      |   8 |     4GB | Yes         | 4x


## Instance Classes

Pipes supports two instance classes:
- `c1.*`: Ephemeral compute instances used to run pipelines
- `db1.*`: Instances used to run Steampipe databases

## Persistence

Shared instances only include ephemeral storage.  Small and medium instances include persistent storage, suitable for Datatank instances.

## Cost Multiplier

Pipes has a pay-for-what-you-use serverless model. Each plan comes with an included allowance of Compute minutes (metered in seconds). You will be charged at the end of the billing for any usage that exceeds the included allowance for your plan.

The Compute charge for a billing cycle is calculated based on database and pipeline compute seconds utilized. Larger instances use a multiplier to consume Compute usage at a higher rate.


### Example 1 - Developer workspace running jobs for 1 month

| Description | Usage
|-|--
| Database usage | 180 mins of `db1.shared`
| Pipeline usage | 300 mins of `c1.shared`
| Included mins  | 400 mins
| **Cost**       |  **`(180 mins + 300 mins - 400 mins) * 60 secs * $0.0001 = $0.48`** |



### Example 2 - Team workspace running jobs for 1 month

| Description | Usage
|-|--
| Database usage | 1,830 mins of `db1.small` (2x multiple)
| Pipeline usage | 635 mins of `c1.shared`
| Included mins  | 2,000 mins
| **Cost**       |  **`((1,830 x 2) mins + 635 mins - 2,000 mins) * 60 secs * $0.0001 = $13.77`** |


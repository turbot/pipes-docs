---
title: Log Archives
sidebar_label: Log Archives
---

# Log Archives

The **Log Archives** page allows you to control which log types (if any) are archived to storage on a daily basis.

- **Audit Logs** pertain to administrative actions undertaken within the Tenant, such as role assignments and resource creation.
- **Database Logs** are logs of queries performed against a workspaces Steampipe database within the tenant.

> [!IMPORTANT] Log archives will be metered towards your Tenants storage allowance and any overages will be billed as per our [pricing](https://turbot.com/pipes/pricing#how-are-storage-costs-calculated).

![](/images/docs/pipes/tenant_log_archive_config.png)
<br />

Enabling a log archive will initiate a daily background job that will archive the **previous** days logs of that type to a file.

> [!NOTE]
> Disabling a log archive will prevent future generations of archives but will not remove existing archives from storage, these must be manually removed from the [archives](/pipes/docs/accounts/tenant/advanced#archives).

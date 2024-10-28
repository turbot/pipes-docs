---
title: Integrations
sidebar_label: Integrations
---

# Integrations


[Integrations](/pipes/docs/integrations/) are used to interface with external systems.

When you create an integration for a tenant, you may use it in any workspace in the tenant.  Some integrations, such as the [AWS](/pipes/docs/integrations/aws), [Azure](/pipes/docs/integrations/azure), and [GCP](/pipes/docs/integrations/gcp) integrations, automatically create and manage [connections and folders](/pipes/docs/workspaces/connections).  You can share these connections with any organization or workspace in your tenant.

You must be assigned the tenant **Owner** role to create, modify, or delete tenant integrations.


## Managing Integrations

You can manage integrations from the **Integrations** tab for your tenant.

![](/images/docs/pipes/tenant_integrations.png)


To create a new integration, click the **New Integration** button.  You will be prompted to select the integration and then fill in the required information for that specific [integration](/pipes/docs/integrations/).

To edit an integration, you can click the handle or the gear icon that corresponds to the integration you want to modify.  Each integration type will have its own settings.

To delete an integration,  click the handle or the gear icon that corresponds to the integration you want to modify.  Go to the **Advanced** page and click the **Delete Integration** button. 

You will be asked to enter the handle to confirm deletion. If you wish to ***permanently delete the integration and all of its resources***, click **Delete**.

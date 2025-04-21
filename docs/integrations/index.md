---
title: Integrations
sidebar_label: Integrations
---

# Integrations

Like [connections](/pipes/docs/workspaces/connections), **Integrations** are used to interface with external systems, but they differ from connections in a few ways:

- Integrations may require bidirectional communication with the external system, often needing a public HTTP endpoint in Pipes for asynchronous communication flow.
- Integrations often manage other Pipes resources, such as mods and connections.
- Where a single connection only represents a single security principal, integrations may provide credentials for multiple purposes, requesting different scopes in different situations or impersonating other principals / assuming multiple roles.

Integrations may be defined at the tenant (Enterprise plan only) or identity levels in the hierarchy and then used by workspaces in the same tenant or identity.

You must be assigned the tenant or organization **Owner** role to create, modify, or delete integrations.

## Related links:
|        |               |               |
| ------ | ------------- | ------------- |
| AWS organizations | [Docs](/pipes/docs/integrations/aws) | [Announcement & demo](https://turbot.com/pipes/blog/2024/07/aws-org-sync) |
| Azure tenants | [Docs](/pipes/docs/integrations/azure) | [Announcement & demo](https://turbot.com/pipes/blog/2024/07/azure-tenant-sync) |
| GCP organizations | [Docs](/pipes/docs/integrations/gcp) | [Announcement & demo](https://turbot.com/pipes/blog/2024/07/gcp-org-sync) |
| GitHub organizations | [Docs](/pipes/docs/integrations/github) | [Announcement & demo](https://turbot.com/pipes/blog/2024/05/github-custom-mods) |
| GitLab organizations | [Docs](/pipes/docs/integrations/gitlab) | [Announcement & demo](https://turbot.com/pipes/blog/2025/04/gitlab-custom-mods) |
| Slack | [Docs](/pipes/docs/integrations/slack) |  |

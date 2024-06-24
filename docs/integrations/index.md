---
title: Integrations
sidebar_label: Integrations
---

# Integrations

Like [connections](/pipes/docs/connections), **Integrations** are used to interface with external systems, but they differ from connections in a few ways:

- Integrations may require bidirectional communication with the external system, often needing a public HTTP endpoint in Pipes for asynchronous communication flow.
- Integrations often manage other Pipes resources, such as mods and connections.
- Where a single connection only represents a single security principal, integrations may provide credentials for multiple purposes, requesting different scopes in different situations or impersonating other principals / assuming multiple roles.

Integrations may be defined at the tenant or identity levels in the hierarchy and then used by workspaces in the same tenant or identity.

You must be assigned the organization **Owner** role to create, modify, or delete integrations.  


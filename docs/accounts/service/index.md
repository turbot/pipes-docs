---
title: Service Accounts
sidebar_label: Service Accounts
---

# Service Accounts

Service Accounts are a specialized type of user designed for programmatic access to Turbot Pipes.

The primary use case for service accounts is to enable automation and integration scenarios, where a non-human user needs to interact with the Pipes platform. 
Service accounts can be used in CI/CD pipelines, automated scripts, or other systems that require access to Pipes resources without human intervention.

Service accounts are managed within Turbot Pipes and as such do not require a provisioned user from your user directory (SAML, Google, GitHub, etc).

## Limitations

Service accounts have the following limitations:
- Cannot log in via the Console (web interface).
- Cannot create/manage personal resources i.e. workspaces.
- Cannot modify themselves or other service accounts.
- Can only be created and managed from either the organization or tenant level, depending on your plan.
  - **[Team Plan](/pipes/docs/accounts/org#team-plan)**: Service accounts can be [created at the organization](/pipes/docs/accounts/org/members#service-accounts) level.
  - **[Enterprise Plan](/pipes/docs/accounts/tenant#enterprise-plan)**: Service accounts can be [created at the tenant](/pipes/docs/accounts/tenant/members#service-accounts) level.

## Billing Considerations

From a billing standpoint each service account is classified as a user in your [Team](/pipes/docs/accounts/org#team-plan) or [Enterprise](/pipes/docs/accounts/tenant#enterprise-plan) plan. 

Service accounts are billed like a normal user. They will count against the included users in your plan. If exceeding your included users will be billed at the same rate as an individual user.

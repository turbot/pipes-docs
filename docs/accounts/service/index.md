---
title: Service Account
sidebar_label: Service Account
---

# Service Account

Service Accounts are a specialized account type designed for non-human users that need programmatic access to Turbot Pipes.

## Creating Service Accounts

Service accounts can be created from either the organization or tenant level, depending on your plan.

- **Team Plan** [Team Plan](/pipes/docs/accounts/org#team-plan): Service accounts can be [created at the organization](/pipes/docs/accounts/org/people#manage-service-accounts) level.
- **Enterprise Plan** [Enterprise Plan](/pipes/docs/accounts/tenant#enterprise-plan): Service accounts can be [created at the tenant](/pipes/docs/accounts/tenant/people#manage-service-accounts) level.

## Limitations

Service accounts have the following limitations:
- Cannot log in via the Console (web interface).
- Cannot own personal resources i.e. workspaces.
- Are bound to the billing entity in which they are created.
  - If created in an organization, they can only be assigned permissions to this org and any workspaces within the org.
  - If created in a tenant, they can be assigned permissions across all organizations and workspaces within the tenant.
- Cannot modify themselves or other service accounts.

## Billing Considerations

Each Service Account contributes to your user count on your [Team](/pipes/docs/accounts/org#team-plan) or [Enterprise](/pipes/docs/accounts/tenant#enterprise-plan) plan, as such you should consider service account usage when planning your subscription capacity.

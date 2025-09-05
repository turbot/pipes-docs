---
title: Service Account
sidebar_label: Service Account
---

# Service Account

Service Accounts are a specialized type of user designed for programmatic access to Turbot Pipes.

The primary use case for service accounts is to enable automation and integration scenarios, where a non-human user needs to interact with the Pipes platform. 
Service accounts can be used in CI/CD pipelines, automated scripts, or other systems that require access to Pipes resources without human intervention.

## Limitations

Service accounts have the following limitations:
- Cannot log in via the Console (web interface).
- Cannot own personal resources i.e. workspaces.
- Are bound to the billing entity in which they are created.
    - If created in an organization, they can only be assigned permissions to this organization and workspaces contained within the organization.
    - If created in a tenant, they can be assigned permissions across all organizations and workspaces within the tenant.
- Cannot modify themselves or other service accounts.

## Creating Service Accounts

Service accounts can be created from either the organization or tenant level, depending on your plan.

- **[Team Plan](/pipes/docs/accounts/org#team-plan)**: Service accounts can be [created at the organization](/pipes/docs/accounts/org/members#service-accounts) level.
- **[Enterprise Plan](/pipes/docs/accounts/tenant#enterprise-plan)**: Service accounts can be [created at the tenant](/pipes/docs/accounts/tenant/members#service-accounts) level.

## Billing Considerations

Each service account contributes to your user count on your [Team](/pipes/docs/accounts/org#team-plan) or [Enterprise](/pipes/docs/accounts/tenant#enterprise-plan) plan, as such you should consider service account usage when planning your subscription capacity.

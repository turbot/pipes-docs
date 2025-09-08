---
title: Tenants
sidebar_label: Tenants
---

# Tenants

With [Pipes Enterprise](/pipes/docs/accounts/tenant#enterprise-plan), you can create your own isolated **Tenant** with a custom domain for your environment (e.g. `acme.pipes.turbot.com`).  Your tenant has its own discrete set of user accounts, organizations, and workspaces, giving you centralized visibility and control.  You can choose which [authentication methods](/pipes/docs/accounts/tenant/advanced#authentication-methods) are allowed, configure which [domains to trust](/pipes/docs/accounts/tenant/advanced#trusted-login-domains), and set up [SAML](/pipes/docs/accounts/tenant/advanced#saml) to integrate your Pipes tenant with your single-sign-on solution.  

Tenants are only available in the [Enterprise plan](#enterprise-plan).


## Enterprise Plan

The **Enterprise Plan** provides organization-wide security, compliance, and scalability.

The enterprise plan provides the ability to create a single tenant.  The base price includes 3 users, 10,000 compute minutes, and 100GB storage capacity, but you can [purchase additional capacity](/pipes/pricing) in a monthly pay-as-you-go model.



## Creating Tenants

To create a tenant, first ensure you are on the main [Pipes tenant](https://pipes.turbot.com). Select your profile picture at the top right of the Pipes console, and select **Create Tenant** from the menu. Review the Enterprise plan offering details
and select **Create Tenant**. Enter a name for your tenant. This name must be unique across all tenants in Pipes, and the console will let you know if it's available or not.
Optionally, expand the **Profile** and set
a **Logo URL** (publicly accessible URL for the organization's logo) and **URL**
(publicly accessible URL for the organization). Click **Create Tenant**.

The creation process can vary in time and may take up to 5 minutes. You don't have to wait, though - once the tenant is created, you will be sent a welcome email with a login link.

## Initial login

The initial login to a new tenant can only be performed via email. The Pipes user that created the tenant will be added as a [tenant owner](/pipes/docs/accounts/tenant/members#tenant-roles) in the new tenant and will have full control of the tenant after they log in.

Once you have logged in, you can set up other [authentication methods](/pipes/docs/accounts/tenant/advanced#authentication-methods), or you can invite other users to the tenant.

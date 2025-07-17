---
title: Authentication
sidebar_label: Authentication
---

# Authentication

The **Authentication** page allows you to control which [domains are trusted](#trusted-login-domains), as well as to enable, disable, and configure [authentication methods](#authentication-methods) like Email, [SAML](#saml), [GitHub](#github), and [Google](#google).

To manage the authentication settings for your tenant, navigate to your tenant, then click the double arrow button from the navigation at the top of the page and select **Tenant Settings** from the dropdown. 
This option will only be visible in a custom tenant for which you are a [tenant owner](/pipes/docs/accounts/tenant/people#tenant-roles). 


## Trusted Login Domains

Trusted domains allow you to specify a list of email domains from which users can log in and be invited. The restrictions are applied regardless of the [authentication method](#authentication-methods) used.

By default, this is set to an empty list, which means there are no domain restrictions in place. If you wish to restrict access to a specific domain(s), you can add that domain to the list.

Enter the domain(s) you wish to add and click **Save**.

<img src="/images/docs/pipes/pipes-enterprise-settings-auth-trust-domains.png" width="400pt"/>

## Authentication Methods

You can enable multiple methods of authentication for your tenant - users logging in across multiple methods will be treated as the same user in Pipes if their logins resolve to a user with the same email address.


The methods available for authentication are:

| Methods     | Description
|-------------|------------------------------------------------------
| `Email` |  The default method for a new tenant. Login is available via magic links sent to the requesting user.
| `SAML` |  [SSO via SAML 2.0](#saml). 
| `GitHub` |  OAuth via [GitHub](#github). **Please note** the user's *primary* GitHub email address is presented and therefore used when evaluating [trusted login domain](#trusted-login-domains) restrictions.
| `Google` |  OAuth via [Google](#google).


<!--

| `Microsoft` |  OAuth via Microsoft.

-->

To enable or disable an authentication method, toggle the radio button for that method.



### SAML

SAML, which stands for Security Assertion Markup Language, is an XML-based open standard for exchanging authentication and authorization data between parties. The primary use case for SAML is in single sign-on (SSO) scenarios, where a user can log in once and gain access to multiple systems or applications without the need to log in again for each one.  The SAML standard is widely used in enterprise environments and web-based applications to enable secure and seamless single sign-on experiences. 

If you wish to enable SSO via SAML for your tenant, please follow the steps below:

- Navigate to **SAML** from the **Authentication methods** section.
- In your Identity Provider (IdP), create a new SAML 2.0 application for Pipes. The details you will need are:
  - **Service Provider ACS URL**: _Pre-populated for you in the Pipes console. Click to copy it._
  - **Service Provider Entity ID**: _Pre-populated for you in the Pipes console. Click to copy it_
  - **Name ID Format**: EmailAddress
  - **Attribute Mappings**: Map the following attributes to the corresponding user attributes in your IdP: 
    - `email`: the email address of the user
    - `firstName`: the given / first name of the user
    - `lastName`: the family/surname of the user
    - `login`: _optional_ unique user login identifier
- Once you have created the application, you will need to gather and enter the following information from your IdP: 
  - **Identity Provider Issuer ID**: e.g. https://okta.com/eyldobv30u6ndacE15e7
  - **Identity Provider SSO URL**: e.g. https://dev-1234567.okta.com/app/dev-1234567_turbotpipes/eyldobv30u6ndacE15e7/sso/saml
  - **Identity Provider Public Signing Certificate**: Download the X.509 PEM-format certification from your IdP

Once you have entered the required information from the SAML IdP configuration, click **Save**. You can then enable the SAML authentication method by toggling the radio button.


### GitHub

You can enable GitHub authentication by toggling the radio button.  When GitHub authentication is enabled, any user that has been authenticated by GitHub whose primary email address is from a [trusted login domain](#trusted-login-domains) will be able to log in to your tenant - they do not need to be invited.  A user will be created the first time they log in to Pipes, and they will be assigned the [Member role](/pipes/docs/accounts/tenant/people#tenant-roles) in the tenant. 

**Please note** the user's *primary GitHub email address* is presented and therefore used when evaluating [trusted login domain](#trusted-login-domains) restrictions.


### Google
You can enable Google authentication by toggling the radio button.  When Google authentication is enabled, any user who has been authenticated by Google whose email address is from a [trusted login domain](#trusted-login-domains) will be able to log in to your tenant - they do not need to be invited.  A user will be created the first time they log in to Pipes, and they will be assigned the [Member role](/pipes/docs/accounts/tenant/people#tenant-roles) in the tenant. 

## User Session Timeout

You can configure the maximum duration of a user session in your tenant, after which the user will be required to log in again. 

To set the user session timeout, select the desired duration or select custom (hours) for the **User Session Timeout** field and click **Save**. The default value is `30 Days`.

<img src="/images/docs/pipes/cloud-tenant-user-session-timeout.png" width="400pt"/>
<br />

> Note: This setting will only apply to new user sessions. Existing user sessions will not be affected until they expire, the user logs out or [authentication is reset](#reset-authentication).

## Reset Authentication

Once users have been added to your tenant, they will be able to authenticate against it according to the permissions they were granted.
They can authenticate using either temporary tokens issued via console or [CLI login](https://steampipe.io/docs/reference/cli/login#steampipe-login), or with [tokens](/pipes/docs/accounts/developer/advanced#tokens) managed via their user profile settings.

If you wish to reset authentication in your organization for any currently issued tokens, you can do so by going to the **Advanced** page for your tenant and then clicking **Authentication** from the left-hand menu.  Click the
`Reset authentication` button to reset authentication for all existing temporary and user tokens.

This will immediately remove console access to the tenant for all users, prompting them to log in again. Any users who wish to access your tenant via the API will also be required to generate a new user [token](/pipes/docs/accounts/developer/advanced#tokens).

<img src="/images/docs/pipes/cloud-tenant-reset-authentication.png" width="400pt"/>
<br />
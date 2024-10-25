---
title: Billing
sidebar_label: Billing
---

# Billing

The **Billing** page provides visibility into the current state of billing for your tenant. 

You can view and manage billing from the **Advanced** page for your tenant. Navigate to your tenant, then click the double arrow button from the navigation at the top of the page and select **Tenant Settings** from the dropdown. Go to the **advanced** tab, and select **Billing** from the lef-hand menu.  The billing page will only available if you are a Tenant Owner for the tenant.


<img src="/images/docs/pipes/pipes_billing.png" width="400pt"/>
 

## Free Trial

When you first enroll in the [Enterprise Plan](/pipes/docs/accounts/tenant#enterprise-plan) and create a tenant, you will be signed up to a 14-day free trial. 

During this period, you will have access to all the features of the plan, with 1/2 of the normal included monthly compute minutes.

After or during the trial period, you will need to upgrade to a paid plan to continue using the service. Failure to do so will result in your workspaces being suspended.

After you have added a card, you will automatically be converted to a paid subscription at the end of the trial.

## Debit / Credit Card Payment

If you wish to pay for Pipes using a debit or credit card, you must first enter your card details. To do so, click the **Add Card** button.

<img src="/images/docs/pipes/pipes_billing_add_card.png" width="400pt"/>

This will create a secure connection between your browser and our payment provider. **Please note**: We *never* store your card details on our servers.

At the top of the page you will see a summary of your billing information:

- The billing [plan](/pipes/pricing) for this account.
- The dates of the current billing cycle.  Billing cycles vary by tenant, and may not coincide with a calendar month.
- The amount of the last invoice, along with its payment status
- The amount of the next invoice

### Invoices

The invoices table provides a list of previous invoices, including the invoice date, the amount, and the payment status. You can download any of these invoices by clicking the options menu (three vertical dots) at the end of the line and selection **Download** from the popup menu.

### Cards

The cards section lists your active debit/credit cards. One of these cards must be selected as the **default**. The default card is the card that will be billed when subscribed via debit/credit card. Only a non-default card can be removed.

### Manage Subscription

You can cancel the subscription by clicking the **Cancel Subscription** button. The cancellation will occur at the end of the free trial, or the current billing period. Once cancelled this will result in the suspension of all your workspaces.

## AWS Marketplace Subscription

As an alternative to direct card payment, you can choose to pay for your tenant subscription via [AWS Marketplace](https://aws.amazon.com/marketplace).

### Setup

To do so:

- Ensure you are logged into the AWS account that you wish to use to pay for your subscription.
- Navigate to either the [Turbot Pipes - Enterprise Plan](https://aws.amazon.com/marketplace/pp/prodview-oysayoazz5dds) or [Turbot Pipes - Team Plan](https://aws.amazon.com/marketplace/pp/prodview-b3dfz5hxhcn3a) product page.
- Review the pricing and terms, then click **View purchase options**.
- Click the **Subscribe** button.
- Click the **Set up your account** button.
- You will be taken to a Turbot Pipes landing page - you may be asked to sign-in again.
- From there, you will be presented with a list of tenants or organizations that you are an [owner](/pipes/docs/people) of.
- Select the tenant or organization that you wish to subscribe to via AWS Marketplace.
- Click **Set up**.

This will close out any existing debit/credit card subscription you have and generate a final invoice based on additional usage in the current billing cycle.

Once complete you will be taken back to your dashboard. If you were previously in a tenant or organization trial, the monthly subscription fee will be added to your AWS Marketplace subscription after a short while. If you were already on a paid plan you will not be metered for the AWS Marketplace subscription until the date at which your existing debit/credit card plan would have rolled to the next billing cycle.

All additional usage will be metered to AWS Marketplace on a daily basis and added to your monthly AWS bill.

When subscribed via AWS Marketplace, Pipes has no access to the invoices or payment cards associated with your subscription, as these are managed within your subscribing AWS account. 

### Cancellation

If you wish to cancel your subscription: you can do so at any time by clicking the **Manage Subscription** button on the **Billing** page.

This will take you to your AWS Marketplace subscriptions page. From there:

- Find the `Turbot Pipes - Team Plan` subscription.
- Click **Manage**
- Under `Actions`, select **Cancel Subscription**.

This will initiate the cancellation flow and close out the subscription in Pipes. Once that has completed your workspaces will be suspended.

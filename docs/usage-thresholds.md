---
title: Usage Thresholds
sidebar_label: Usage Thresholds
---

# Usage Thresholds

Pipes **Usage Thresholds** enable you to set usage limits and control what happens when those limits are reached.

To view and set usage thresholds, go to the **Settings** page for your organization or developer account and click **Usage** from the left
hand menu. At the top of the page, click **Thresholds** to switch the the Thresholds tab.

<img src="/images/docs/pipes/pipes_identity_usage_thresholds.png" width="400pt"/>
<br />


For each usage dimension (Storage, Compute, Users), you can set the threshold value as well as the behavior:
- **Warn**:  Send notifications when the threshold limit is reached.
- **Cap and warn** - Cap usage and send notifications when the threshold limit is reached.

Notifications are sent to the Organization owners via email. You will receive a warning when you reach 75%, 100%, 125%, 200%, 300%, 500%, and 1000% of the specified value.


The **Cap and warn** behavior varies by dimension:
- When **Cap and warn** is set and the compute limit is reached, all workspaces will sleep and pipelines will be be suspended.
- When **Cap and warn** is set and the storage limit is reached, snapshots will no longer be written, and you will not be able to spin up any new workspaces.
- When **Cap and warn** is set and the user limit is reached, you will not be able to invite any more users to the Organization.




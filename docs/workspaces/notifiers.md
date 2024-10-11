---
title: Notifiers
sidebar_label: Notifiers
---

# Notifiers


Sending notifications is a common pattern, and often users will want to route a request to more than one user, group, or channel, and via more than one delivery mechanism. For instance, you may want to request approval via slack AND email. The Flowpipe `notifier` resource allows you to define a list notification [integrations](/pipes/docs/integrations/) to send notifications to.

Each notifier contains a list of integrations and related settings used to send and receive data to one or more integration when an input step executes.


## Default Notifier



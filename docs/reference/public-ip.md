---
title: Public IP Addresses
sidebar_label: Public IP Addresses
---

# Public IP Addresses

This document lists the public IPs used by Pipes for inbound and outbound requests. You can use these IPs to configure firewall rules, set up access controls, and integrate with external services.

## Inbound to Pipes
Turbot Pipes accepts traffic on the following ports:

| **Name**                                                   | **Static IP Address**     | **Ports**
|------------------------------------------------------------|---------------------------|-----------
| Turbot Pipes UI/API (pipes.turbot.com, *.pipes.turbot.com) | 34.86.218.179/32          | 80, 443
| Workspace Steampipe DB Endpoint                            | 34.145.175.31/32          | 9193
| Workspace Powerpipe WebSocket Server                       | 34.85.232.246/32          | 80, 443


## Outbound from Pipes

Turbot Pipes will use the following IP addresses for outbound traffic to external services:

| **Static IP Address** |
|-----------------------|
| 35.194.64.40/32       |
| 34.150.247.248/32     |
| 34.150.238.109/32     |

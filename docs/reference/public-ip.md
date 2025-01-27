# Public IP Addresses

## Overview
This document provides a list of public IPs used by Pipes for inbound and outbound requests. These IPs are intended for end users to configure whitelisting, firewall rules, and integrations with external services.

## Public IPs
### 1. Inbound to Pipes
The following IPs are inbound to Pipes to accept traffic. Please ensure these are whitelisted for access to our services:

| **Name**                                                           | **Static IP Address**     | **Ports**     |
|--------------------------------------------------------------------|---------------------------|---------------|
| Turbot Pipes UI (pipes.turbot.com, *.pipes.turbot.com)             | 34.86.218.179/32          | 80, 443       |
| Postgres Endpoint                                                  | 34.145.175.31/32          | 9193          |
| WebSocket Server                                                   | 34.85.232.246/32          | 80, 443       |

These IPs are static and will not change.

### 2. Outbound from Pipes
The following IPs are used for outbound traffic from Pipes to external services:

| **Static IP Address**     |
|---------------------------|
| 35.194.64.40/32           |
| 34.150.247.248/32         |
| 34.150.238.109/32         |
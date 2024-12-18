# Pipes' Public IP Addresses

## **Overview**
This document provides a list of public IPs used by Pipes for outbound requests. These IPs are intended for end-users to configure whitelisting, firewall rules, and integrations with external services.

## **Public IPs**
#### **1. Load Balancer IPs**
The following IPs are used by Pipes' load balancers. Please ensure these are whitelisted for access to our services:

| **Load Balancer Name**       | **Static IP Address**     | **Ports**     |
|------------------------------|---------------------------|---------------|
| Main Service           | 34.86.218.179            | 80, 443       |
| Database Proxy                    | 34.145.175.31            | 9193          |
| Dashboard                    | 34.85.232.246            | 80, 443       |

These IPs are static and will not change.

#### **2. NAT Gateway IPs**
The following IPs are used for outbound traffic from Pipes to external services:

| **Static IP Address**     |
|---------------------------|
| 35.194.64.40              |
| 34.150.247.248            |
| 34.150.238.109            |
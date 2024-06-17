---
title: Using the Turbot Pipes Terraform Provider
sidebar_label: Terraform
---

# Manage Turbot Pipes with Terraform

The Turbot Pipes Terraform provider makes it easy to manage your Turbot Pipes
infrastructure as code!

**[Turbot Pipes Terraform Provider reference docs →](https://registry.terraform.io/providers/turbot/pipes/latest/docs)**

```hcl
terraform {
  required_providers {
    pipes = {
      source = "turbot/pipes"
    }
  }
}

# Configure the Turbot Pipes provider
provider "pipes" {
  token = "tpt_q9boaa6gutha5g3rgexample"
}

# Create an org
resource "pipes_organization" "myorg" {
  handle       = "myorg"
  display_name = "Test Org"
}

# Add an org member
resource "pipes_organization_member" "example" {
  organization = pipes_organization.myorg.handle
  user_handle  = "someuser"
  role         = "member"
}
```

# Terraform Modules

[![GitHub license](https://img.shields.io/github/license/Alexander77063/terraform-modules)](https://github.com/Alexander77063/terraform-modules/blob/main/LICENSE)
[![Terraform](https://img.shields.io/badge/terraform-%235835CC.svg?style=flat&logo=terraform&logoColor=white)](https://www.terraform.io/)
[![AWS](https://img.shields.io/badge/AWS-%23FF9900.svg?style=flat&logo=amazon-aws&logoColor=white)](https://aws.amazon.com/)

A collection of reusable Terraform modules for AWS cloud infrastructure provisioning and management. These modules implement infrastructure as code best practices, enabling consistent, repeatable, and version-controlled deployments.

## Table of Contents

- [Overview](#overview)
- [Modules](#modules)
- [Requirements](#requirements)
- [Usage](#usage)
- [Examples](#examples)
- [Contributing](#contributing)
- [License](#license)

## Overview

This repository contains modular, composable Terraform configurations encapsulating common infrastructure patterns used across AWS deployments. Each module is designed to be independent, reusable, and configurable using variables to accommodate different use cases and environments.

The primary goals of these modules are:

- **Standardization** - Enforce best practices and security standards across infrastructure
- **Reusability** - Build once, use many times across projects
- **Maintainability** - Centralized changes and updates to infrastructure patterns
- **Simplification** - Abstract complex infrastructure into easy-to-use modules

## Modules

| Module Name | Description | Documentation |
|-------------|-------------|---------------|
| `networking` | Creates VPC, subnets, route tables, NACLs, and other networking components | [Documentation](./networking/README.md) |
| `compute` | Provisions EC2 instances with standardized configurations | [Documentation](./compute/README.md) |
| `security` | Manages security groups, IAM policies and roles | [Documentation](./security/README.md) |
| `storage` | Creates and configures S3 buckets with proper encryption and access policies | [Documentation](./storage/README.md) |
| `database` | Sets up RDS instances with proper configuration and backup policies | [Documentation](./database/README.md) |
| `lambda` | Deploys Lambda functions with proper IAM permissions | [Documentation](./lambda/README.md) |
| `monitoring` | Configures CloudWatch alarms, dashboards, and logging | [Documentation](./monitoring/README.md) |

## Requirements

- Terraform >= 1.0.0
- AWS Provider >= 4.0
- AWS CLI configured with appropriate credentials
- Git for version control

## Usage

To use these modules in your Terraform configurations, reference them using the GitHub source:

```hcl
module "vpc" {
  source = "github.com/Alexander77063/terraform-modules//networking/vpc?ref=v1.0.0"
  
  # Module specific variables
  vpc_name        = "production-vpc"
  vpc_cidr        = "10.0.0.0/16"
  azs             = ["eu-west-2a", "eu-west-2b", "eu-west-2c"]
  private_subnets = ["10.0.1.0/24", "10.0.2.0/24", "10.0.3.0/24"]
  public_subnets  = ["10.0.101.0/24", "10.0.102.0/24", "10.0.103.0/24"]
  
  # Additional parameters as needed
  enable_nat_gateway = true
  single_nat_gateway = false
  
  tags = {
    Environment = "production"
    Terraform   = "true"
  }
}
```

Always pin to a specific version using the `?ref=VERSION` parameter to ensure your infrastructure remains stable.

## Examples

The `examples` directory contains complete, working examples demonstrating how to use these modules in different scenarios:

- [Basic VPC Setup](./examples/basic-vpc/README.md)
- [Three-Tier Web Application](./examples/three-tier-app/README.md)
- [Serverless Application](./examples/serverless-app/README.md)
- [Multi-Account Infrastructure](./examples/multi-account/README.md)

Each example includes:
- Ready-to-use Terraform configurations
- A README with detailed explanations
- Variables file templates

To run an example:

```bash
cd examples/basic-vpc
terraform init
terraform plan
terraform apply
```

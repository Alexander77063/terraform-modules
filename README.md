
# Terraform Modules Repository

A collection of reusable Terraform modules for provisioning cloud infrastructure.

## Modules Overview

### Available Modules

| Module Name | Description | Documentation Link |
|-------------|-------------|---------------------|
| `vpc`       | Creates a VPC with subnets, NAT Gateway, and route tables | [VPC Module Docs](./modules/vpc/README.md) |
| `ec2`       | Provisions EC2 instances with customizable configurations | [EC2 Module Docs](./modules/ec2/README.md) |
| `rds`       | Sets up RDS instances with security best practices | [RDS Module Docs](./modules/rds/README.md) |
| `security-group` | Configures security groups with common rule sets | [Security Group Docs](./modules/security-group/README.md) |
| `s3`        | Creates S3 buckets with versioning and access controls | [S3 Module Docs](./modules/s3/README.md) |

*(Replace the above module names and descriptions with your actual modules)*

## Usage

### Prerequisites
- Terraform v1.0+
- AWS CLI configured with proper credentials
- Git for version control

### How to Use These Modules

1. Clone the repository:
   ```bash
   git clone https://github.com/Alexander77063/terraform-modules.git
   ```

2. In your Terraform configuration:
   ```hcl
   module "example_vpc" {
     source = "./modules/vpc"
     
     vpc_cidr = "10.0.0.0/16"
     public_subnets = ["10.0.1.0/24", "10.0.2.0/24"]
     private_subnets = ["10.0.3.0/24", "10.0.4.0/24"]
   }
   ```

## Module Documentation Details

Each module contains detailed documentation in its respective README file:

### VPC Module
- [Input Variables](./modules/vpc/variables.tf)
- [Output Values](./modules/vpc/outputs.tf)
- [Resource Definitions](./modules/vpc/main.tf)

### EC2 Module
- [Input Variables](./modules/ec2/variables.tf)
- [Output Values](./modules/ec2/outputs.tf)
- [Resource Definitions](./modules/ec2/main.tf)

### RDS Module
- [Input Variables](./modules/rds/variables.tf)
- [Output Values](./modules/rds/outputs.tf)
- [Resource Definitions](./modules/rds/main.tf)

*(Repeat this pattern for all your modules)*

## Example Implementations

See complete usage examples in the [examples](./examples/) directory:
- [Basic Web Application](./examples/web-app/)
- [Multi-tier Architecture](./examples/multi-tier/)
- [Serverless Setup](./examples/serverless/)
## License

[Apache License 2.0](./LICENSE)

To customize this template:
1. Update the module names and descriptions to match your actual modules
2. Verify the file paths match your repository structure
3. Add/remove modules as needed
4. Update the example implementations section with your actual examples
5. Add any module-specific requirements or notes
6. Include any important security considerations
7. Add CI/CD badges if applicable
8. Include Terraform registry information if published

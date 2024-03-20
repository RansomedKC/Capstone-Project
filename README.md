# Capstone-Project
This repo contains My Alt School final Capstone Project


```markdown
# Terraform Configuration for AWS EKS Deployment

This Terraform configuration automates the deployment of an Amazon Elastic Kubernetes Service (EKS) cluster along with associated networking resources using Infrastructure as Code (IaC) principles.

## Prerequisites

- [Terraform](https://www.terraform.io/downloads.html) installed on your local machine.
- AWS credentials configured on your system.

## Usage

1. Cloned this repository to my local machine:

   ```bash
   git clone https://github.com/RansomedKC/eks-cluster-deployment.git
   ```

2. Navigated to the cloned repository directory:

   ```bash
   cd eks-cluster-deployment
   ```

3. Updated the `variables.tf` file with your AWS credentials and desired configurations.

4. Initialized Terraform and applied the configurations:

   ```bash
   terraform init
   terraform apply
   ```

5. Follow edthe prompts to confirm the changes and deploy the infrastructure.

## Components

### AWS Provider Configuration

The AWS provider block configures the AWS region based on the value specified in the `var.region` variable.

```hcl
provider "aws" {
  region = var.region
}
```

### Availability Zones Data Source

The data source `aws_availability_zones` filters out local zones, which are not currently supported with managed node groups.

```hcl
data "aws_availability_zones" "available" {
  filter {
    name   = "opt-in-status"
    values = ["opt-in-not-required"]
  }
}
```

### Virtual Private Cloud (VPC) Module

The `terraform-aws-modules/vpc/aws` module is used to create a VPC with public and private subnets.

```hcl
module "vpc" {
  source  = "terraform-aws-modules/vpc/aws"
  version = "5.0.0"
  ...
}
```

### Amazon EKS Module

The `terraform-aws-modules/eks/aws` module is used to create an EKS cluster with managed node groups.

```hcl
module "eks" {
  source  = "terraform-aws-modules/eks/aws"
  version = "19.15.3"
  ...
}
```

## Additional Notes

- Ensure that your IAM user or role has the necessary permissions to create EKS clusters and associated resources.
- Review the Terraform plan carefully before applying it to your AWS account to avoid unexpected changes.
- Consider enabling logging and monitoring for the EKS cluster to ensure visibility into its performance and health.

For more details and customization options, refer to the Terraform documentation and the respective module documentation on the Terraform Registry.
```
This README provides a comprehensive guide for users to understand the Terraform configurations and deploy an AWS EKS cluster with associated networking resources. It includes usage instructions, component descriptions, and additional notes for customization and best practices.

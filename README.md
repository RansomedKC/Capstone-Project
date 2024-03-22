# Capstone-Project
This repo contains My Alt School final Capstone Project

Certainly! Here's a breakdown of the provided Terraform solution for deploying the Socks Shop microservices application on Kubernetes, structured as a README file:

---

# Socks Shop Microservices Application Deployment

This repository contains Terraform configurations to automate the deployment of the Socks Shop microservices application on Amazon Elastic Kubernetes Service (EKS).

## Objective

The main goal of this project is to deploy the Socks Shop application, a demonstration of a microservices architecture, using modern DevOps practices and Infrastructure as Code (IaC) principles. The deployment process should be automated, ensuring quick, reliable, and secure deployment on Kubernetes.

## Setup Details

### What I did

I set up the Socks Shop application using Terraform configurations, automating the deployment process on Amazon EKS.

### Resources

- [Socks Shop Microservices Demo](https://github.com/microservices-demo/microservices-demo): GitHub Repository containing the Socks Shop application.
- [Detailed Implementation Guide](https://github.com/microservices-demo/microservices-demo): GitHub Repository providing detailed instructions for setting up the Socks Shop application.

## Key Components

### Terraform Configuration

The Terraform configurations in this repository automated the setup of the following components:

- Amazon EKS Cluster
- Virtual Private Cloud (VPC)
- Subnets, Security Groups, and other networking resources
- Managed Node Groups for EKS worker nodes

### File Structure

The repository follows the following file structure:

```
.
├── main.tf                # Main Terraform configuration defining resources
├── variables.tf           # Variables used in the Terraform configuration
├── outputs.tf             # Output values from the Terraform configuration
└── README.md              # README file providing an overview of the project
```

## Usage

1. I Cloned this repository to my local machine:

   ```bash
   git clone https://github.com/RansomedKC/socks-shop-deployment.git
   ```

2. I Navigated to the cloned repository directory:

   ```bash
   cd socks-shop-deployment
   ```

3. I Updated the `variables.tf` file with my AWS credentials and desired configurations.

4. I then Initialized Terraform and applied the configurations:

   ```bash
   terraform init
   terraform apply
   ```

5. I Followed the prompts to confirm the changes and deploy the infrastructure.

## Additional Considerations

- **Monitoring and Alerts**: Implement Prometheus for monitoring and set up Alertmanager for alerts.
- **Logging**: Ensure the application's operations can be tracked and analyzed through logs.
- **Security and HTTPS**: Make sure the application is accessible over HTTPS by using Let’s Encrypt for certificates. Implement network security measures and handle sensitive information securely using Ansible Vault.

## Contributing

Contributions to improve this project are welcome! Feel free to open issues or pull requests with suggestions, enhancements, or bug fixes.

---

This README provides an overview of the project, explaining its purpose, components, usage instructions, and additional considerations for further enhancements. It serves as a guide for users to understand and utilize the Terraform configurations effectively for deploying the Socks Shop microservices application on Amazon EKS.


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

5. Followed the prompts to confirm the changes and deploy the infrastructure.

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

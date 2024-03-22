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


 

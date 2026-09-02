# AWS Secure Web Server Deployment using Terraform

## Overview
This project demonstrates Infrastructure as Code (IaC) by using Terraform to
automatically provision a secure AWS environment and deploy a live web server —
without manually clicking through the AWS Console.

## Architecture
- Custom VPC (10.0.0.0/16) with a public subnet
- Internet Gateway for internet connectivity
- Route Table routing external traffic through the Internet Gateway
- Security Group:
  - Port 22 (SSH) restricted to a single trusted IP
  - Port 80 (HTTP) open to the public for web access
- EC2 instance (t3.micro, free-tier eligible) running Amazon Linux 2023
- Apache web server automatically installed and started via `user_data`

## Why This Project
Manually creating and configuring cloud resources through the console is slow,
inconsistent, and hard to reproduce. This project uses Terraform to define the
entire infrastructure as version-controlled code — the same approach used in
real-world DevOps and Cloud Engineering environments — enabling repeatable,
auditable, and disposable infrastructure.

## Tools & Technologies
- Terraform
- AWS CLI
- AWS Services: VPC, EC2, Security Groups, Internet Gateway, Route Tables, IAM

## How It Works
1. `terraform init` — initializes the working directory and downloads the AWS provider
2. `terraform plan` — previews the resources that will be created
3. `terraform apply` — provisions the VPC, subnet, security group, and EC2 instance
4. The EC2 instance's `user_data` script installs and starts an Apache web server on boot
5. `terraform destroy` — tears down all resources cleanly, avoiding unnecessary cost

## Key Takeaways
- Hands-on experience provisioning cloud infrastructure using Infrastructure as Code
- Practical understanding of AWS networking (VPC, subnets, routing, security groups)
- Applied least-privilege principles by restricting SSH access to a single IP
- End-to-end automation from infrastructure provisioning to application deployment

## Author
Avnish Mishra
[LinkedIn](https://linkedin.com/in/avnishmishra154) | [GitHub](https://github.com/AvnishMishra154)

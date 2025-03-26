# terroform-_task

# AWS VPC with EC2 using Terraform

This repository contains a Terraform configuration to provision an AWS infrastructure with the following resources:
- AWS VPC
- Public and Private Subnets
- Internet Gateway for public access
- NAT Gateway for private subnet internet access
- Route Tables
- EC2 Instance in the Public Subnet

## Prerequisites
- AWS Account
- AWS CLI installed ([Installation Guide](https://docs.aws.amazon.com/cli/latest/userguide/install-cliv2.html))
- Terraform installed ([Download Terraform](https://developer.hashicorp.com/terraform/downloads))

## AWS Configuration
Ensure your AWS CLI is configured using the following command:
```bash
aws configure
```
You will be prompted to enter:
- **AWS Access Key ID**
- **AWS Secret Access Key**
- **Default Region Name** (e.g., `us-east-1`)
- **Output Format** (e.g., `json`)

Verify your AWS configuration:
```bash
aws sts get-caller-identity
```

## Project Setup
1. Clone this repository:
```bash
git clone <repository-url>
cd <repository-folder>
```

2. Initialize Terraform:
```bash
terraform init
```

3. Review the Terraform plan:
```bash
terraform plan
```

4. Apply the Terraform configuration:
```bash
terraform apply
```
Confirm with `yes` when prompted.

## Outputs
After the deployment is successful, Terraform will display the public IP of the EC2 instance:
```bash
Outputs:
public_ip = <EC2 Public IP>
```
You can use this IP to access your instance using SSH:
```bash
ssh ec2-user@<EC2 Public IP> -i <path-to-your-private-key>
```

## Cleanup
To destroy the provisioned resources:
```bash
terraform destroy
```

## Troubleshooting
- Ensure your AWS CLI is correctly authenticated using `aws sts get-caller-identity`.
- Check for any missing permissions in AWS IAM.
- Review error logs using `terraform plan` or `terraform apply`.


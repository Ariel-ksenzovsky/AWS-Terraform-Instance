# AWS Terraform Instance

This repository contains a simple Terraform configuration for deploying an EC2 instance on AWS. The configuration defines the necessary resources to create and manage the EC2 instance, including networking and security settings.

## Prerequisites

Before using this repository, ensure you have the following installed:

- [Terraform](https://www.terraform.io/downloads.html)
- [AWS CLI](https://aws.amazon.com/cli/) (with configured credentials)
- A valid AWS account and necessary permissions to create EC2 instances.

## Setup

1. Clone the repository:

   ```bash
   git clone https://github.com/Ariel-ksenzovsky/AWS-Terraform-Instance.git
   cd AWS-Terraform-Instance
   ```

2. Initialize Terraform:

   ```bash
   terraform init
   ```

3. Review the configuration files to ensure they meet your requirements, such as instance type, region, and security group settings.

4. Plan the Terraform execution to see what changes will be made:

   ```bash
   terraform plan
   ```

5. Apply the Terraform configuration to create the EC2 instance:

   ```bash
   terraform apply
   ```

   You will be prompted to confirm the action by typing `yes`.

6. After the EC2 instance is created, you can view it in the [AWS Management Console](https://aws.amazon.com/console/).

## Resources Managed

- EC2 instance (with a configurable AMI, instance type, and security group)
- Security group with open ports (configurable)

## Clean Up

To delete the resources created by Terraform, run:

```bash
terraform destroy
```

Confirm the action by typing `yes` when prompted.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
```

Feel free to adjust any settings or add more details specific to your use case!
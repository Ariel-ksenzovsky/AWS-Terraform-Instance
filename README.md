# AWS Terraform Instance

This repository contains a simple Terraform configuration for deploying an EC2 instance on AWS. The configuration defines the necessary resources to create and manage the EC2 instance, including networking and security settings. Additionally, CI and CD workflows are implemented to automate the process.

## Prerequisites

Before using this repository, ensure you have the following installed:

- [Terraform](https://www.terraform.io/downloads.html)
- [AWS CLI](https://aws.amazon.com/cli/) (with configured credentials)
- [Ansible](https://www.ansible.com/) for running playbooks
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

7. **Apply Ansible Playbook**: After the EC2 instance is created, the Ansible playbook is executed to configure the instance. This can include installing necessary software, copying files, or applying configuration changes to the instance.

## CI Workflow

The CI (Continuous Integration) workflow automates the process of building and testing the Docker image:

- **Build Docker Image**: On each push to the repository, a new Docker image is built using the latest code. This ensures that the application is always packaged with the latest changes.
- **Test Docker Image**: After building the Docker image, automated tests are run to ensure the image works as expected. This could include unit tests, integration tests, or any other validation needed before deploying the image.

## CD Workflow

The CD (Continuous Deployment) workflow automates the process of deploying the infrastructure and configuring the application after the code has passed tests:

- **Apply Terraform Configuration**: Once the CI pipeline successfully builds and tests the Docker image, the CD pipeline applies the Terraform configuration to create or update the EC2 instance on AWS. This ensures the latest infrastructure changes are applied automatically.
  
- **Run Ansible Playbook**: After the EC2 instance is provisioned, an Ansible playbook is executed to configure the instance. This can include installing necessary software, copying files, or applying configuration changes to the instance.

## Project Structure

The project is organized as follows:

```
AWS-Terraform-Instance/
│
├── ansible/
│   ├── playbook.yml           # Ansible playbook to configure the EC2 instance
│   ├── inventory.ini          # Ansible inventory file for EC2 instances
│
├── terraform/
│   ├── main.tf                # Main Terraform configuration file for EC2 instance
│   ├── variables.tf           # Variables for Terraform configuration
│   ├── outputs.tf             # Output values for the Terraform configuration
│
├── .github/
│   └── workflows/             # GitHub Actions workflows (CI and CD)
│       ├── ci.yml             # CI workflow to build and test Docker image
│       └── cd.yml             # CD workflow to apply Terraform and run Ansible
│
├── README.md                  # Project documentation
├── LICENSE                    # Project license file
```

- `ansible/`: Contains the Ansible playbook and inventory file for configuring the EC2 instance after it is provisioned.
- `terraform/`: Contains the Terraform configuration files to create the EC2 instance and define its resources.
- `.github/`: Contains the GitHub Actions workflows for the CI and CD processes.
- `README.md`: This file that explains the project, setup, and workflows.
- `LICENSE`: License file for the project.

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

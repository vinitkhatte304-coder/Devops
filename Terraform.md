# 🌍 Terraform Notes

## What is Terraform?

**Terraform** is an **Infrastructure as Code (IaC)** tool developed by **HashiCorp**. It allows you to define, provision, update, and manage infrastructure using code instead of manually creating resources.

Using Terraform, you can:

- Create infrastructure
- Update infrastructure
- Delete infrastructure
- Automate cloud resource provisioning

Terraform supports multiple cloud providers, including:

- AWS
- Microsoft Azure
- Google Cloud Platform (GCP)
- Oracle Cloud
- DigitalOcean
- VMware
- Kubernetes

---

# Why Use Terraform?

- Infrastructure as Code (IaC)
- Automates infrastructure provisioning
- Supports multiple cloud providers
- Reusable and modular code
- Version-controlled infrastructure
- Easy collaboration among teams
- Consistent infrastructure deployment

---

# What is Infrastructure as Code (IaC)?

**Infrastructure as Code (IaC)** is the practice of managing and provisioning infrastructure using code instead of manually configuring servers and cloud resources.

### Benefits

- Automation
- Consistency
- Faster deployments
- Reduced human errors
- Easy rollback using version control

---

# What is a Terraform Plugin?

A **Terraform Plugin** is an external component that enables Terraform to communicate with cloud providers, platforms, or services.

Examples:

- AWS Provider
- Azure Provider
- Google Provider
- Kubernetes Provider

Without plugins (providers), Terraform cannot create or manage infrastructure.

---

# Terraform vs HCL

| Terraform | HCL (HashiCorp Configuration Language) |
|-----------|-----------------------------------------|
| Infrastructure as Code (IaC) tool | Configuration language used by Terraform |
| Executes infrastructure changes | Defines infrastructure resources |
| Developed by HashiCorp | Developed by HashiCorp |
| Runs commands like `plan` and `apply` | Human-readable declarative language |
| Creates and manages resources | Describes desired infrastructure |

### Example HCL

```hcl
resource "aws_instance" "web" {
  ami           = "ami-xxxxxxxx"
  instance_type = "t3.micro"
}
```

---

# Terraform vs AWS CloudFormation

| Terraform | CloudFormation |
|------------|----------------|
| Multi-cloud support | AWS only |
| Open Source | AWS Managed Service |
| Uses HCL | Uses YAML or JSON |
| Supports AWS, Azure, GCP, etc. | Supports only AWS |
| State file (`terraform.tfstate`) | AWS Stack Management |
| Vendor-independent | AWS-specific |

---

# Terraform Architecture

```text
Terraform Code (HCL)
          │
          ▼
Terraform CLI
          │
          ▼
Terraform Provider (Plugin)
          │
          ▼
Cloud Provider API
          │
          ▼
Cloud Resources
```

---

# Terraform File Structure

```text
Terraform-Project/
│
├── main.tf
├── variables.tf
├── outputs.tf
├── terraform.tfvars
├── provider.tf
└── terraform.tfstate
```

---

# Important Terraform Files

| File | Purpose |
|------|----------|
| `main.tf` | Main Terraform configuration |
| `provider.tf` | Provider configuration |
| `variables.tf` | Input variables |
| `terraform.tfvars` | Variable values |
| `outputs.tf` | Output values |
| `terraform.tfstate` | Stores infrastructure state |

---

# What is a Terraform Provider?

A **Provider** is a plugin that allows Terraform to interact with a specific cloud platform or service.

### Example

```hcl
provider "aws" {
  region = "us-east-1"
}
```

---

# What is a Terraform Resource?

A **Resource** is any infrastructure object that Terraform manages.

Examples:

- EC2 Instance
- S3 Bucket
- VPC
- Security Group
- IAM User
- RDS Database

### Example

```hcl
resource "aws_instance" "myserver" {
  ami           = "ami-12345678"
  instance_type = "t3.micro"
}
```

This resource creates an **AWS EC2 instance**.

---

# Creating an EC2 Instance Using Terraform

## Step 1 – Install Terraform

Open **PowerShell**.

Install Terraform:

```powershell
winget install Hashicorp.Terraform
```

Verify installation:

```powershell
terraform version
```

Install:

- Visual Studio Code
- AWS CLI (optional but recommended)

Create a new project folder and add:

```text
main.tf
```

---

## Step 2 – Configure AWS Provider

Copy the AWS provider configuration into `main.tf`.

```hcl
provider "aws" {
  region     = "us-east-1"
  access_key = "YOUR_ACCESS_KEY"
  secret_key = "YOUR_SECRET_KEY"
}
```

> **Note:** For production environments, avoid hardcoding credentials. Use the AWS CLI (`aws configure`) or IAM Roles instead.

---

## Step 3 – Create an EC2 Resource

```hcl
resource "aws_instance" "example" {
  ami           = "ami-xxxxxxxxxxxxxxxxx"
  instance_type = "t3.micro"

  tags = {
    Name = "New-Terraform-Instance"
  }
}
```

Replace:

- `ami-xxxxxxxxxxxxxxxxx` with a valid AMI ID for your chosen AWS region.

---

# Terraform Commands

## Initialize Terraform

Downloads the required provider plugins.

```bash
terraform init
```

---

## Validate Configuration

Checks the syntax of your Terraform files.

```bash
terraform validate
```

---

## Format Code

Automatically formats Terraform code.

```bash
terraform fmt
```

---

## Create an Execution Plan

Shows what Terraform will create, update, or destroy.

```bash
terraform plan
```

---

## Apply Changes

Creates or updates infrastructure.

```bash
terraform apply
```

When prompted, type:

```text
yes
```

to confirm.

---

## Destroy Infrastructure

Deletes all resources managed by Terraform.

```bash
terraform destroy
```

or

```bash
terraform destroy -auto-approve
```

> **Note:** The correct flag is `-auto-approve` (not `-auto approved`).

---

# Step 4 – Verify Resources

After running:

```bash
terraform apply
```

Go to:

```text
AWS Console
        │
        ▼
EC2 Dashboard
        │
        ▼
Instances
```

Verify that your EC2 instance has been created successfully.

---

# Common Terraform Commands

| Command | Description |
|----------|-------------|
| `terraform init` | Initialize Terraform project |
| `terraform validate` | Validate configuration files |
| `terraform fmt` | Format Terraform code |
| `terraform plan` | Preview changes |
| `terraform apply` | Apply infrastructure changes |
| `terraform destroy` | Delete infrastructure |
| `terraform show` | Display current state |
| `terraform output` | Show output values |
| `terraform state list` | List managed resources |
| `terraform version` | Display installed Terraform version |

---

# Terraform Workflow

```text
Write Configuration
        │
        ▼
terraform init
        │
        ▼
terraform validate
        │
        ▼
terraform fmt
        │
        ▼
terraform plan
        │
        ▼
terraform apply
        │
        ▼
Infrastructure Created
```

---

# Advantages of Terraform

- Infrastructure as Code (IaC)
- Multi-cloud support
- Open Source
- Reusable modules
- Easy automation
- Version control integration
- Consistent deployments
- Declarative configuration

---

# Interview Questions

### What is Terraform?

Terraform is an **Infrastructure as Code (IaC)** tool developed by HashiCorp that automates the provisioning and management of infrastructure using code.

---

### What is HCL?

HCL (HashiCorp Configuration Language) is the declarative language used to write Terraform configuration files.

---

### What is a Provider?

A Provider is a plugin that allows Terraform to communicate with cloud platforms such as AWS, Azure, and GCP.

---

### What is a Resource?

A Resource is an infrastructure object managed by Terraform, such as an EC2 instance, S3 bucket, or VPC.

---

### What does `terraform init` do?

It initializes the Terraform working directory and downloads the required provider plugins.

---

### What does `terraform plan` do?

It previews the changes Terraform will make before applying them.

---

### What does `terraform apply` do?

It creates or updates infrastructure based on the Terraform configuration.

---

### What does `terraform destroy` do?

It deletes all infrastructure managed by the Terraform configuration.

---

# Quick Interview Revision

## Terraform

- Infrastructure as Code (IaC)
- Developed by HashiCorp
- Multi-cloud support

## HCL

- Human-readable configuration language
- Used to define infrastructure

## Provider

- Connects Terraform to cloud platforms

## Resource

- Infrastructure object managed by Terraform

## State File

- Stores the current state of infrastructure

## Important Commands

```bash
terraform init
terraform validate
terraform fmt
terraform plan
terraform apply
terraform destroy
terraform output
terraform show
terraform version
```

---

# Author

**Prepared by:** Vinit Khatte  
**Purpose:** AWS • DevOps • Terraform Interview Revision Notes

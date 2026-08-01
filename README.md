# SME Website Migration to AWS Cloud: Capstone Project

Migration of a Small and Medium Enterprise (SME) website to AWS Cloud, using
WordPress on Amazon EC2, deployed both manually and via Terraform
(Infrastructure as Code).

Author: Dimmalove
**Programme:** 3MTT Cloud Computing Training 

## Repository contents

| File / Folder | Description |
|---|---|
| `SME_AWS_Migration_Capstone_Report.docx` | Full capstone report: introduction, architecture, AWS setup, WordPress installation, Terraform deployment, testing, troubleshooting, cost estimation, security, deliverables, and learning outcomes, with APA references. |
| `SME_AWS_Migration_Capstone_Presentation.pptx` | 17-slide presentation summarising the project for a demonstration or oral defence. |
| `terraform-project/` | Standalone Terraform configuration (`provider.tf`, `variables.tf`, `main.tf`, `outputs.tf`, `terraform.tfvars`, `wordpress_setup.sh.tpl`) that provisions the full architecture and auto-installs WordPress on first boot. |
| `screenshots/` | Evidence captures from the live deployment (EC2 console, SSH session, WordPress site) — to be added after deployment. |

## Architecture summary

```
Internet → Internet Gateway → VPC → Public Subnet → Route Table
         → Security Group (22/80/443) → EC2 (Apache, PHP, WordPress, MySQL)
         → Amazon EBS
```

See the full report for the detailed diagram, component explanations, and
rationale for each technology choice.

## Quick start (automated deployment)

```bash
cd terraform-project
terraform init
terraform apply     # type "yes" to confirm
```

Terraform prints the site's public URL when it finishes. Allow 1–2 minutes
for the boot script to install the LAMP stack and WordPress, then open the
URL in a browser to complete the WordPress setup wizard.

To remove all AWS resources and stop billing:

```bash
terraform destroy
```

Full step-by-step instructions (including the manual, console-based
deployment path) are in the project report.

## Cost

Designed to run within the AWS Free Tier (12 months) at no cost. After the
Free Tier expires, estimated baseline cost is approximately US$9–12/month.
See the report's Cost Estimation section for the full breakdown.

## Skills demonstrated

AWS Cloud Computing · EC2 Administration · Linux Server Administration ·
Networking (VPC/subnets/routing) · WordPress Deployment ·
Infrastructure as Code (Terraform) · Cloud Security · DevOps & Automation ·
Cloud Migration Planning

## License

This project is for educational purposes as part of the 3MTT Cloud
Computing Training programme.

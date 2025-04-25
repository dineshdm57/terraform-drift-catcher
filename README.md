# Terraform Drift Cost Catcher

Detects AWS EC2 resources running outside of Terraform state.

## What It Does

This OpenOps workflow:

- Gets all running EC2 instances from AWS
- Gets Terraform-managed resources (from your Terraform outputs or state)
- Compares both lists
- Alerts in Slack if any EC2 instance is not managed via Terraform

## Why It Matters

Cloud drift = cost waste.  
This tool flags orphaned resources you forgot to clean up.  
Helps FinOps, DevOps, and Security teams stay in control.

## How to Use

1. Import the `.json` file in OpenOps
2. Connect your AWS and Slack accounts
3. Update:
   - AWS Region in Step 2
   - Terraform API/source in Step 3
   - Slack Channel in Step 5
4. Run the workflow

## Requirements

- AWS access with `ec2:DescribeInstances`
- Terraform state accessible via API or endpoint
- Slack connection

## Editable

You can extend this for:
- Azure/GCP resources
- Other IaC tools (Pulumi, CDK)
- Email/Teams instead of Slack

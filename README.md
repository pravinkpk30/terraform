# terraform

# Steps to follow

# terraform init
Run terraform init to initialize the working directory. This step downloads the necessary provider plugins (like AWS, Azure, Google Cloud, etc.) that Terraform needs to interact with the respective cloud platform or service.

## Purpose
This ensures Terraform has the required tools to communicate with the platforms defined in the configuration.

# terraform plan
Run terraform plan to preview the changes that will be made to the infrastructure. Terraform compares the desired state defined in the configuration files with the current state stored in its state file or remote state storage.

## Purpose
The plan command produces an execution plan, showing exactly what changes (additions, modifications, or deletions) Terraform will make when you apply the changes. No actual changes are made during this step.

# terraform apply
After reviewing the plan, run terraform apply to actually provision or modify the infrastructure. Terraform reads the configuration files, computes the changes necessary, and applies them.

## Purpose
During this step, Terraform interacts with APIs of the providers (e.g., AWS, Azure) to create, update, or destroy resources to match the configuration.

# State Management
Terraform maintains a state file (usually named terraform.tfstate), which keeps track of the current state of your infrastructure. This file helps Terraform understand what resources exist, their configurations, and any changes made.
<b>Remote State:</b> For collaboration or large-scale environments, this state file can be stored remotely (e.g., in S3, Google Cloud Storage, etc.) to ensure consistency and avoid conflicts.
Importance: Terraform's state file is critical for determining how the real-world infrastructure compares to the desired configuration.

# Modifications
## When changes are made to the configuration, Terraform will:
Re-run terraform plan to detect differences between the configuration and the current infrastructure.
Execute terraform apply to bring the infrastructure in sync with the updated configuration.

# terraform destroy
Terraform can also tear down infrastructure with the terraform destroy command. This removes all the resources that were defined in the configuration and cleans up any state files.

## Purpose
Useful when you want to decommission infrastructure or remove resources that are no longer needed.

# Summary of Terraform Flow:
Define: Write the desired infrastructure as code in .tf files.
Initialize: Use terraform init to set up the environment and download necessary providers.
Plan: Run terraform plan to preview the changes.
Apply: Use terraform apply to implement the changes.
State: Track the infrastructure using the state file.
Modify: Re-apply changes by modifying configuration and using terraform plan and apply.
Destroy: Clean up infrastructure with terraform destroy.
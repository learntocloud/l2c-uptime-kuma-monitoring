# L2C Uptime Kuma Monitoring

## Overview

This Terraform project deploys and configures Uptime Kuma for L2C monitoring on Azure. You can see the deployed version - [status.learntocloud.guide](https://status.learntocloud.guide/). The infrastructure includes an Azure Resource Group, a Storage Account with a file share, an App Service Plan, and a Linux Web App configured to run the Uptime Kuma Docker container.

## Prerequisites

- [Terraform](https://www.terraform.io/downloads.html) installed (v1.0+ recommended)
- An active Azure subscription
- [Azure CLI](https://learn.microsoft.com/en-us/cli/azure/install-azure-cli) for authentication (optional but recommended)

## Installation

1. **Clone the repository**  

   ```sh
   git clone <repository_url>
   cd ltc-uptime-kuma-monitoring
   ```


2. **Initialize Terraform**

    `terraform init`
    This will download required providers and initialize the backend.

3. **Configure Variables**

    Modify the variables in variables.tf or create a `terraform.tfvars` file to provide values for:

    - `resource_group_name`
    - `storage_account_name`
    - `web_app_name`
    - `(Other variables as needed)`

## Deployment

1. Plan the deployment
    Use Terraform to review the changes:
    `terraform plan`

2. Apply the configuration
    Deploy the resources with:
    `terraform apply`

3. Verify the deployment
    Confirm that the Web App is running the Uptime Kuma container and that all resources are set up correctly.

## Architecture

The key resources defined in main.tf include:

- Azure Resource Group: Groups all the Azure resources.
- Azure Storage Account and Share: Provides persistent storage for Uptime Kuma data.
- Azure App Service Plan and Linux Web App: Hosts the Uptime Kuma container.

For more details, review the specific resource configurations in `main.tf` and variable definitions in `variables.tf`.

## Usage

Use the deployed Uptime Kuma Web App to monitor L2C status, view performance metrics, and receive alerts.


## Troubleshooting

Check the `terraform.tfstate` file to verify resource changes.

If errors occur, review the output logs for any Terraform apply errors.
Ensure that all environment variables and Terraform variable values are correctly set.

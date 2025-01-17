<!-- gen-readme start - generated by https://github.com/jetify-com/devbox/ -->

## Getting Started

This project uses [devbox](https://github.com/jetify-com/devbox) to manage its development environment.

Install devbox:

```sh
curl -fsSL https://get.jetpack.io/devbox | bash
```

Start the devbox shell:

```sh
devbox shell
```

Run a script in the devbox environment:

```sh
devbox run <script>
```

## Purpose

This project is used to deploy and configure an Azure hosted Azure DevOps Agent using Ubuntu Server 22.04.

Default parameters are defined in the ./roles/[Role Name]/defaults/main.yml. To override defaults, add variables to the project root variables.yml.

Ensure you update variables.yml with your ADO Organisation URL, PAT Token & Agent Pool. Please Note, the Agent Pool must already exist!

To tear down the Azure Resources deployed, set the variable "azure_vm_state" to Absent.

Automatic removal of the agent from the pool is not currently supported. Please remove the agent manually before redeploying with the same name.

## Notice

This will deploy an Azure VM, and all surrounding resources required (e.g. RG, vNet, PIP)

This deploys an NSG that only allows SSH inbound, and uses SSH Keys to secure this.

## Authentication

To authenticate to Azure, use the AZ CLI. This is installed via DevBox.

`az login --use-device-code`

## Packages

- [python312Packages.ansible-core@2.18.1](https://www.nixhub.io/packages/python312Packages.ansible-core)
- [python312Packages.ansible@11.1.0](https://www.nixhub.io/packages/python312Packages.ansible)
- [azure-cli@2.67.0](https://www.nixhub.io/packages/azure-cli)
- [python312Packages.azure-storage-blob@12.23.1](https://www.nixhub.io/packages/python312Packages.azure-storage-blob)
- [python312Packages.azure-mgmt-network@latest](https://www.nixhub.io/packages/python312Packages.azure-mgmt-network)
- [python312Packages.azure-mgmt-automation@latest](https://www.nixhub.io/packages/python312Packages.azure-mgmt-automation)
- [python312Packages.azure-mgmt-notificationhubs@8.0.0](https://www.nixhub.io/packages/python312Packages.azure-mgmt-notificationhubs)
- [python312Packages.azure-mgmt-datafactory@9.0.0](https://www.nixhub.io/packages/python312Packages.azure-mgmt-datafactory)
- [python312Packages.azure-identity@1.18.0](https://www.nixhub.io/packages/python312Packages.azure-identity)
- [python312Packages.msgraph-sdk@1.15.0](https://www.nixhub.io/packages/python312Packages.msgraph-sdk)

## To Do

- Creation of Agent Pool if it does not exist
- Automated removal of the agent if the VM is being torn down.
- Support for other operating systems.
- Option to remove PIP after building.

[![Built with Devbox](https://www.jetify.com/img/devbox/shield_galaxy.svg)](https://www.jetify.com/devbox/docs/contributor-quickstart/)

<!-- gen-readme end -->

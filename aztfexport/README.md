## Prerequisites

Azure CLI has to be installed on your system

## Installation

```sh
brew install aztfexport
```

## Usage

Login with Azure CLI to your requested account:

```sh
az login
```

Set subscription

```sh
az account set --subscription "<id>"
```

In an empty folder use the following command:

```sh
aztfexport resource-group --backend-type=azurerm --backend-config="resource_group_name=<rg_to_store_state>" --backend-config="storage_account_name=<storage_account_to_store_state>" --backend-config="container_name=<container_name>" --backend-config="key=<file_name>" <rg_to_export>
```

Example:

```sh
aztfexport resource-group --backend-type=azurerm --backend-config="resource_group_name=gep-p-common-rg" --backend-config="storage_account_name=geppcommonsa" --backend-config="container_name=tf-state-prod" --backend-config="key=terraform.tfstate" gep-p-rg
```

## Links

- https://github.com/Azure/aztfexport#install
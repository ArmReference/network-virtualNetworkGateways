[![Deploy to Azure](https://aka.ms/deploytoazurebutton)](https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2FArmReference%2Fnetwork-virtualNetworkGateways%2F1.0.0.0%2Fazuredeploy.json)
# Create Virtual Network Gateway

This template creates an Virtual Network Gateway in Azure

A VPN gateway is a specific type of virtual network gateway that is used to send encrypted traffic between an Azure virtual network and an on-premises location over the public Internet. You can also use a VPN gateway to send encrypted traffic between Azure virtual networks over the Microsoft network. Each virtual network can have only one VPN gateway. However, you can create multiple connections to the same VPN gateway. When you create multiple connections to the same VPN gateway, all VPN tunnels share the available gateway bandwidth.

## Parameters

Parameter name | Required | Description
-------------- | -------- | -----------
StorageAccountName | Yes      | The name of the Azure Storage Account where the templates are stored.
ContainerName  | Yes      | The Container inside the Storage Account.
SasToken       | Yes      | The Shared Access Signature for the Storage Account.

### StorageAccountName

![Parameter Setting](https://img.shields.io/badge/parameter-required-orange?style=flat-square)

The name of the Azure Storage Account where the templates are stored.

### ContainerName

![Parameter Setting](https://img.shields.io/badge/parameter-required-orange?style=flat-square)

The Container inside the Storage Account.

### SasToken

![Parameter Setting](https://img.shields.io/badge/parameter-required-orange?style=flat-square)

The Shared Access Signature for the Storage Account.

## Outputs

Name | Type | Description
---- | ---- | -----------
armTemplate | object | Fully populated template

## Snippets

### Parameter file

```json
{
    "$schema": "https://schema.management.azure.com/schemas/2015-01-01/deploymentParameters.json#",
    "contentVersion": "1.0.0.1",
    "metadata": {
        "template": "azuredeploy.json"
    },
    "parameters": {
        "StorageAccountName": {
            "value": ""
        },
        "ContainerName": {
            "value": ""
        },
        "SasToken": {
            "value": ""
        }
    }
}
```

### Command line

#### PowerShell

```powershell
New-AzResourceGroupDeployment -Name <deployment-name> -ResourceGroupName <resource-group-name> -TemplateFile <path-to-template> -TemplateParameterFile <path-to-templateparameter>
```

#### Azure CLI

```text
az group deployment create --name <deployment-name> --resource-group <resource-group-name> --template-file <path-to-template> --parameters @<path-to-templateparameterfile>
```

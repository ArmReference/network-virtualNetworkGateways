# Azure template

## Parameters

Parameter name | Required | Description
-------------- | -------- | -----------
customBgpIpAddresses | No       | The list of custom BGP peering addresses which belong to IP configuration.
defaultBgpIpAddresses | No       | The list of default BGP peering addresses which belong to IP configuration.
ipconfigurationId | No       | The ID of IP configuration which belongs to gateway.
tunnelIpAddresses | No       | The list of tunnel public IP addresses which belong to IP configuration.

### customBgpIpAddresses

![Parameter Setting](https://img.shields.io/badge/parameter-optional-green?style=flat-square)

The list of custom BGP peering addresses which belong to IP configuration.

### defaultBgpIpAddresses

![Parameter Setting](https://img.shields.io/badge/parameter-optional-green?style=flat-square)

The list of default BGP peering addresses which belong to IP configuration.

### ipconfigurationId

![Parameter Setting](https://img.shields.io/badge/parameter-optional-green?style=flat-square)

The ID of IP configuration which belongs to gateway.

### tunnelIpAddresses

![Parameter Setting](https://img.shields.io/badge/parameter-optional-green?style=flat-square)

The list of tunnel public IP addresses which belong to IP configuration.

## Outputs

Name | Type | Description
---- | ---- | -----------
IPConfigurationBgpPeeringAddress | object | BGP peering address with IP configuration ID for virtual network gateway.

## Snippets

### Parameter file

```json
{
    "$schema": "https://schema.management.azure.com/schemas/2015-01-01/deploymentParameters.json#",
    "contentVersion": "1.0.0.0",
    "metadata": {
        "template": "reference/ipconfigurationbgppeeringaddress.json"
    },
    "parameters": {
        "customBgpIpAddresses": {
            "value": []
        },
        "defaultBgpIpAddresses": {
            "value": []
        },
        "ipconfigurationId": {
            "value": ""
        },
        "tunnelIpAddresses": {
            "value": []
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

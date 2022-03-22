# Azure template

## Parameters

Parameter name | Required | Description
-------------- | -------- | -----------
name           | Yes      | Resource name.
location       | No       | Resource location.
properties     | No       | Virtual network Gateway Properties
tags           | No       | Resource tags.
DependsOn      | No       | Pass dependencies

### name

![Parameter Setting](https://img.shields.io/badge/parameter-required-orange?style=flat-square)

Resource name.

### location

![Parameter Setting](https://img.shields.io/badge/parameter-optional-green?style=flat-square)

Resource location.

- Default value: `[resourceGroup().location]`

### properties

![Parameter Setting](https://img.shields.io/badge/parameter-optional-green?style=flat-square)

Virtual network Gateway Properties

### tags

![Parameter Setting](https://img.shields.io/badge/parameter-optional-green?style=flat-square)

Resource tags.

### DependsOn

![Parameter Setting](https://img.shields.io/badge/parameter-optional-green?style=flat-square)

Pass dependencies

## Outputs

Name | Type | Description
---- | ---- | -----------
virtualNetworkGateway | object |

## Snippets

### Parameter file

```json
{
    "$schema": "https://schema.management.azure.com/schemas/2015-01-01/deploymentParameters.json#",
    "contentVersion": "1.0.0.0",
    "metadata": {
        "template": "reference/virtualNetworkGateways.json"
    },
    "parameters": {
        "name": {
            "value": ""
        },
        "location": {
            "value": "[resourceGroup().location]"
        },
        "properties": {
            "value": {}
        },
        "tags": {
            "value": {}
        },
        "DependsOn": {
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

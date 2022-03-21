# Azure template

## Parameters

Parameter name | Required | Description
-------------- | -------- | -----------
addressPrefixes | No       | A list of address blocks reserved for this virtual network in CIDR notation.

### addressPrefixes

![Parameter Setting](https://img.shields.io/badge/parameter-optional-green?style=flat-square)

A list of address blocks reserved for this virtual network in CIDR notation.

## Outputs

Name | Type | Description
---- | ---- | -----------
AddressSpace | object | AddressSpace contains an array of IP address ranges that can be used by subnets of the virtual network.

## Snippets

### Parameter file

```json
{
    "$schema": "https://schema.management.azure.com/schemas/2015-01-01/deploymentParameters.json#",
    "contentVersion": "1.0.0.0",
    "metadata": {
        "template": "reference/addressspace.json"
    },
    "parameters": {
        "addressPrefixes": {
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

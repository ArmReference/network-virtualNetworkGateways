# Azure template

## Parameters

Parameter name | Required | Description
-------------- | -------- | -----------
name           | Yes      | The name of the resource that is unique within a resource group. This name can be used to access the resource.
privateIPAddress | No       | Private IP Address for this gateway.
privateIPAllocationMethod | Yes      | The private IP allocation method. Possible values are: 'Static' and 'Dynamic'.
publicIPAddress | No       | The reference of the public IP resource.
subnet         | No       | The reference of the subnet resource.

### name

![Parameter Setting](https://img.shields.io/badge/parameter-required-orange?style=flat-square)

The name of the resource that is unique within a resource group. This name can be used to access the resource.

### privateIPAddress

![Parameter Setting](https://img.shields.io/badge/parameter-optional-green?style=flat-square)

Private IP Address for this gateway.

### privateIPAllocationMethod

![Parameter Setting](https://img.shields.io/badge/parameter-required-orange?style=flat-square)

The private IP allocation method. Possible values are: 'Static' and 'Dynamic'.

- Allowed values: `Dynamic`, `Static`

### publicIPAddress

![Parameter Setting](https://img.shields.io/badge/parameter-optional-green?style=flat-square)

The reference of the public IP resource.

### subnet

![Parameter Setting](https://img.shields.io/badge/parameter-optional-green?style=flat-square)

The reference of the subnet resource.

## Outputs

Name | Type | Description
---- | ---- | -----------
VirtualNetworkGatewayIPConfiguration | object | IP configuration for virtual network gateway.

## Snippets

### Parameter file

```json
{
    "$schema": "https://schema.management.azure.com/schemas/2015-01-01/deploymentParameters.json#",
    "contentVersion": "1.0.0.0",
    "metadata": {
        "template": "reference/virtualnetworkgatewayipconfiguration.json"
    },
    "parameters": {
        "name": {
            "value": ""
        },
        "privateIPAddress": {
            "value": ""
        },
        "privateIPAllocationMethod": {
            "value": ""
        },
        "publicIPAddress": {
            "value": {}
        },
        "subnet": {
            "value": {}
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

# Azure template

## Parameters

Parameter name | Required | Description
-------------- | -------- | -----------
name           | Yes      | The name of the resource that is unique within a resource group. This name can be used to access the resource.
externalMappings | No       | The private IP address external mapping for NAT.
internalMappings | No       | The private IP address internal mapping for NAT.
ipConfigurationId | No       | The IP Configuration ID this NAT rule applies to.
mode           | Yes      | The private IP allocation method. Possible values are: 'Static' and 'Dynamic'.
type           | Yes      | The private IP allocation method. Possible values are: 'Static' and 'Dynamic'.

### name

![Parameter Setting](https://img.shields.io/badge/parameter-required-orange?style=flat-square)

The name of the resource that is unique within a resource group. This name can be used to access the resource.

### externalMappings

![Parameter Setting](https://img.shields.io/badge/parameter-optional-green?style=flat-square)

The private IP address external mapping for NAT.

### internalMappings

![Parameter Setting](https://img.shields.io/badge/parameter-optional-green?style=flat-square)

The private IP address internal mapping for NAT.

### ipConfigurationId

![Parameter Setting](https://img.shields.io/badge/parameter-optional-green?style=flat-square)

The IP Configuration ID this NAT rule applies to.

### mode

![Parameter Setting](https://img.shields.io/badge/parameter-required-orange?style=flat-square)

The private IP allocation method. Possible values are: 'Static' and 'Dynamic'.

- Allowed values: `EgressSnat`, `IngressSnat`

### type

![Parameter Setting](https://img.shields.io/badge/parameter-required-orange?style=flat-square)

The private IP allocation method. Possible values are: 'Static' and 'Dynamic'.

- Allowed values: `Dynamic`, `Static`

## Outputs

Name | Type | Description
---- | ---- | -----------
VirtualNetworkGatewayNatRule | object | IP configuration for virtual network gateway.

## Snippets

### Parameter file

```json
{
    "$schema": "https://schema.management.azure.com/schemas/2015-01-01/deploymentParameters.json#",
    "contentVersion": "1.0.0.1",
    "metadata": {
        "template": "reference/virtualnetworkgatewaynatrule.json"
    },
    "parameters": {
        "name": {
            "value": ""
        },
        "externalMappings": {
            "value": []
        },
        "internalMappings": {
            "value": []
        },
        "ipConfigurationId": {
            "value": ""
        },
        "mode": {
            "value": ""
        },
        "type": {
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

# Azure template

## Parameters

Parameter name | Required | Description
-------------- | -------- | -----------
name           | Yes      | Resource name.
activeActive   | No       | ActiveActive flag.
bgpSettings    | No       | Virtual network gateway's BGP speaker settings.
enableBgp      | No       | Whether BGP is enabled for this virtual network gateway or not.
gatewayType    | Yes      | The type of this virtual network gateway. Possible values are: 'Vpn' and 'ExpressRoute'.
ipConfigurations | Yes      | IP configurations for virtual network gateway.
vpnType        | No       | The type of this virtual network gateway. Possible values are: 'PolicyBased' and 'RouteBased'.
sku            | Yes      | The reference of the VirtualNetworkGatewaySku resource which represents the SKU selected for Virtual network gateway.
DependsOn      | No       | Pass dependencies

### name

![Parameter Setting](https://img.shields.io/badge/parameter-required-orange?style=flat-square)

Resource name.

### activeActive

![Parameter Setting](https://img.shields.io/badge/parameter-optional-green?style=flat-square)

ActiveActive flag.

- Default value: `False`

### bgpSettings

![Parameter Setting](https://img.shields.io/badge/parameter-optional-green?style=flat-square)

Virtual network gateway's BGP speaker settings.

### enableBgp

![Parameter Setting](https://img.shields.io/badge/parameter-optional-green?style=flat-square)

Whether BGP is enabled for this virtual network gateway or not.

- Default value: `False`

### gatewayType

![Parameter Setting](https://img.shields.io/badge/parameter-required-orange?style=flat-square)

The type of this virtual network gateway. Possible values are: 'Vpn' and 'ExpressRoute'.

- Allowed values: `ExpressRoute`, `Vpn`

### ipConfigurations

![Parameter Setting](https://img.shields.io/badge/parameter-required-orange?style=flat-square)

IP configurations for virtual network gateway.

### vpnType

![Parameter Setting](https://img.shields.io/badge/parameter-optional-green?style=flat-square)

The type of this virtual network gateway. Possible values are: 'PolicyBased' and 'RouteBased'.

- Allowed values: ``, `PolicyBased`, `RouteBased`

### sku

![Parameter Setting](https://img.shields.io/badge/parameter-required-orange?style=flat-square)

The reference of the VirtualNetworkGatewaySku resource which represents the SKU selected for Virtual network gateway.

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
        "activeActive": {
            "value": false
        },
        "bgpSettings": {
            "value": {}
        },
        "enableBgp": {
            "value": false
        },
        "gatewayType": {
            "value": ""
        },
        "ipConfigurations": {
            "value": []
        },
        "vpnType": {
            "value": ""
        },
        "sku": {
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

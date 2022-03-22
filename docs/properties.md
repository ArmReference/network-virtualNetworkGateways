# Azure template

## Parameters

Parameter name | Required | Description
-------------- | -------- | -----------
activeActive   | No       | ActiveActive flag.
bgpSettings    | No       | Virtual network gateway's BGP speaker settings.
customRoutes   | No       | The reference to the address space resource which represents the custom routes address space specified by the customer for virtual network gateway and VpnClient.
disableIPSecReplayProtection | No       | disableIPSecReplayProtection flag.
enableBgp      | No       | Whether BGP is enabled for this virtual network gateway or not.
enableBgpRouteTranslationForNat | No       | EnableBgpRouteTranslationForNat flag
enableDnsForwarding | No       | Whether dns forwarding is enabled or not.
enablePrivateIpAddress | No       | Whether private IP needs to be enabled on this gateway for connections or not.
gatewayDefaultSite | No       | The reference to the LocalNetworkGateway resource which represents local network site having default routes. Assign Null value in case of removing existing default site setting.
gatewayType    | Yes      | The type of this virtual network gateway.
ipConfigurations | No       | IP configurations for virtual network gateway.
natRules       | No       | NatRules for virtual network gateway.
sku            | Yes      | The reference to the VirtualNetworkGatewaySku resource which represents the SKU selected for Virtual network gateway.
vpnClientConfiguration | No       | The reference to the VpnClientConfiguration resource which represents the P2S VpnClient configurations.
vpnGatewayGeneration | No       | The generation for this VirtualNetworkGateway. Must be None if gatewayType is not VPN.
vpnType        | Yes      | The type of this virtual network gateway.

### activeActive

![Parameter Setting](https://img.shields.io/badge/parameter-optional-green?style=flat-square)

ActiveActive flag.

- Default value: `False`

### bgpSettings

![Parameter Setting](https://img.shields.io/badge/parameter-optional-green?style=flat-square)

Virtual network gateway's BGP speaker settings.

### customRoutes

![Parameter Setting](https://img.shields.io/badge/parameter-optional-green?style=flat-square)

The reference to the address space resource which represents the custom routes address space specified by the customer for virtual network gateway and VpnClient.

### disableIPSecReplayProtection

![Parameter Setting](https://img.shields.io/badge/parameter-optional-green?style=flat-square)

disableIPSecReplayProtection flag.

- Default value: `True`

### enableBgp

![Parameter Setting](https://img.shields.io/badge/parameter-optional-green?style=flat-square)

Whether BGP is enabled for this virtual network gateway or not.

- Default value: `False`

### enableBgpRouteTranslationForNat

![Parameter Setting](https://img.shields.io/badge/parameter-optional-green?style=flat-square)

EnableBgpRouteTranslationForNat flag

- Default value: `False`

### enableDnsForwarding

![Parameter Setting](https://img.shields.io/badge/parameter-optional-green?style=flat-square)

Whether dns forwarding is enabled or not.

- Default value: `True`

### enablePrivateIpAddress

![Parameter Setting](https://img.shields.io/badge/parameter-optional-green?style=flat-square)

Whether private IP needs to be enabled on this gateway for connections or not.

- Default value: `False`

### gatewayDefaultSite

![Parameter Setting](https://img.shields.io/badge/parameter-optional-green?style=flat-square)

The reference to the LocalNetworkGateway resource which represents local network site having default routes. Assign Null value in case of removing existing default site setting.

### gatewayType

![Parameter Setting](https://img.shields.io/badge/parameter-required-orange?style=flat-square)

The type of this virtual network gateway.

- Allowed values: `ExpressRoute`, `LocalGateway`, `Vpn`

### ipConfigurations

![Parameter Setting](https://img.shields.io/badge/parameter-optional-green?style=flat-square)

IP configurations for virtual network gateway.

### natRules

![Parameter Setting](https://img.shields.io/badge/parameter-optional-green?style=flat-square)

NatRules for virtual network gateway.

### sku

![Parameter Setting](https://img.shields.io/badge/parameter-required-orange?style=flat-square)

The reference to the VirtualNetworkGatewaySku resource which represents the SKU selected for Virtual network gateway.

### vpnClientConfiguration

![Parameter Setting](https://img.shields.io/badge/parameter-optional-green?style=flat-square)

The reference to the VpnClientConfiguration resource which represents the P2S VpnClient configurations.

### vpnGatewayGeneration

![Parameter Setting](https://img.shields.io/badge/parameter-optional-green?style=flat-square)

The generation for this VirtualNetworkGateway. Must be None if gatewayType is not VPN.

- Default value: `Generation1`

- Allowed values: `Generation1`, `Generation2`, `None`

### vpnType

![Parameter Setting](https://img.shields.io/badge/parameter-required-orange?style=flat-square)

The type of this virtual network gateway.

- Allowed values: `PolicyBased`, `RouteBased`

## Outputs

Name | Type | Description
---- | ---- | -----------
Properties | object | Virtual Network Gateway Properties

## Snippets

### Parameter file

```json
{
    "$schema": "https://schema.management.azure.com/schemas/2015-01-01/deploymentParameters.json#",
    "contentVersion": "1.0.0.0",
    "metadata": {
        "template": "reference/properties.json"
    },
    "parameters": {
        "activeActive": {
            "value": false
        },
        "bgpSettings": {
            "value": {}
        },
        "customRoutes": {
            "value": {}
        },
        "disableIPSecReplayProtection": {
            "value": true
        },
        "enableBgp": {
            "value": false
        },
        "enableBgpRouteTranslationForNat": {
            "value": false
        },
        "enableDnsForwarding": {
            "value": true
        },
        "enablePrivateIpAddress": {
            "value": false
        },
        "gatewayDefaultSite": {
            "value": {}
        },
        "gatewayType": {
            "value": ""
        },
        "ipConfigurations": {
            "value": []
        },
        "natRules": {
            "value": []
        },
        "sku": {
            "value": {}
        },
        "vpnClientConfiguration": {
            "value": {}
        },
        "vpnGatewayGeneration": {
            "value": "Generation1"
        },
        "vpnType": {
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

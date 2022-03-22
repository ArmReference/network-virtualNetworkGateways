# Azure template

## Parameters

Parameter name | Required | Description
-------------- | -------- | -----------
aadAudience    | Yes      | The AADAudience property of the VirtualNetworkGateway resource for vpn client connection used for AAD authentication.
aadIssuer      | Yes      | The AADIssuer property of the VirtualNetworkGateway resource for vpn client connection used for AAD authentication.
aadTenant      | Yes      | The AADTenant property of the VirtualNetworkGateway resource for vpn client connection used for AAD authentication.
radiusServerAddress | Yes      | The radius server address property of the VirtualNetworkGateway resource for vpn client connection.
radiusServerSecret | Yes      | The radius secret property of the VirtualNetworkGateway resource for vpn client connection.
radiusServers  | No       | The radiusServers property for multiple radius server configuration.
vpnAuthenticationTypes | No       | VPN authentication types for the virtual network gateway. String array containing any of:'AAD','Certificate','Radius'
vpnClientAddressPool | No       | The reference to the address space resource which represents Address space for P2S VpnClient.
vpnClientIpsecPolicies | No       | VpnClientIpsecPolicies for virtual network gateway P2S client.
vpnClientProtocols | No       | VpnClientProtocols for Virtual network gateway. String array containing any of: 'IkeV2','OpenVPN','SSTP'
vpnClientRevokedCertificates | No       | VpnClientRevokedCertificate for Virtual network gateway.
vpnClientRootCertificates | No       | VpnClientRootCertificate for virtual network gateway.

### aadAudience

![Parameter Setting](https://img.shields.io/badge/parameter-required-orange?style=flat-square)

The AADAudience property of the VirtualNetworkGateway resource for vpn client connection used for AAD authentication.

### aadIssuer

![Parameter Setting](https://img.shields.io/badge/parameter-required-orange?style=flat-square)

The AADIssuer property of the VirtualNetworkGateway resource for vpn client connection used for AAD authentication.

### aadTenant

![Parameter Setting](https://img.shields.io/badge/parameter-required-orange?style=flat-square)

The AADTenant property of the VirtualNetworkGateway resource for vpn client connection used for AAD authentication.

### radiusServerAddress

![Parameter Setting](https://img.shields.io/badge/parameter-required-orange?style=flat-square)

The radius server address property of the VirtualNetworkGateway resource for vpn client connection.

### radiusServerSecret

![Parameter Setting](https://img.shields.io/badge/parameter-required-orange?style=flat-square)

The radius secret property of the VirtualNetworkGateway resource for vpn client connection.

### radiusServers

![Parameter Setting](https://img.shields.io/badge/parameter-optional-green?style=flat-square)

The radiusServers property for multiple radius server configuration.

### vpnAuthenticationTypes

![Parameter Setting](https://img.shields.io/badge/parameter-optional-green?style=flat-square)

VPN authentication types for the virtual network gateway. String array containing any of:'AAD','Certificate','Radius'

### vpnClientAddressPool

![Parameter Setting](https://img.shields.io/badge/parameter-optional-green?style=flat-square)

The reference to the address space resource which represents Address space for P2S VpnClient.

### vpnClientIpsecPolicies

![Parameter Setting](https://img.shields.io/badge/parameter-optional-green?style=flat-square)

VpnClientIpsecPolicies for virtual network gateway P2S client.

### vpnClientProtocols

![Parameter Setting](https://img.shields.io/badge/parameter-optional-green?style=flat-square)

VpnClientProtocols for Virtual network gateway. String array containing any of: 'IkeV2','OpenVPN','SSTP'

### vpnClientRevokedCertificates

![Parameter Setting](https://img.shields.io/badge/parameter-optional-green?style=flat-square)

VpnClientRevokedCertificate for Virtual network gateway.

### vpnClientRootCertificates

![Parameter Setting](https://img.shields.io/badge/parameter-optional-green?style=flat-square)

VpnClientRootCertificate for virtual network gateway.

## Outputs

Name | Type | Description
---- | ---- | -----------
VpnClientConfiguration | object | VpnClientConfiguration for P2S client.

## Snippets

### Parameter file

```json
{
    "$schema": "https://schema.management.azure.com/schemas/2015-01-01/deploymentParameters.json#",
    "contentVersion": "1.0.0.0",
    "metadata": {
        "template": "reference/vpnclientconfiguration.json"
    },
    "parameters": {
        "aadAudience": {
            "value": ""
        },
        "aadIssuer": {
            "value": ""
        },
        "aadTenant": {
            "value": ""
        },
        "radiusServerAddress": {
            "value": ""
        },
        "radiusServerSecret": {
            "value": ""
        },
        "radiusServers": {
            "value": []
        },
        "vpnAuthenticationTypes": {
            "value": []
        },
        "vpnClientAddressPool": {
            "value": {}
        },
        "vpnClientIpsecPolicies": {
            "value": []
        },
        "vpnClientProtocols": {
            "value": []
        },
        "vpnClientRevokedCertificates": {
            "value": []
        },
        "vpnClientRootCertificates": {
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

# Azure template

## Parameters

Parameter name | Required | Description
-------------- | -------- | -----------
name           | Yes      | The name of the resource that is unique within a resource group. This name can be used to access the resource.
thumbprint     | Yes      | The revoked VPN client certificate thumbprint.

### name

![Parameter Setting](https://img.shields.io/badge/parameter-required-orange?style=flat-square)

The name of the resource that is unique within a resource group. This name can be used to access the resource.

### thumbprint

![Parameter Setting](https://img.shields.io/badge/parameter-required-orange?style=flat-square)

The revoked VPN client certificate thumbprint.

## Outputs

Name | Type | Description
---- | ---- | -----------
VpnClientRevokedCertificate | object | VPN client revoked certificate of virtual network gateway.

## Snippets

### Parameter file

```json
{
    "$schema": "https://schema.management.azure.com/schemas/2015-01-01/deploymentParameters.json#",
    "contentVersion": "1.0.0.0",
    "metadata": {
        "template": "reference/vpnclientrevokedcertificate.json"
    },
    "parameters": {
        "name": {
            "value": ""
        },
        "thumbprint": {
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

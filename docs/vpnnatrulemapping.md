# Azure template

## Parameters

Parameter name | Required | Description
-------------- | -------- | -----------
addressSpace   | Yes      | Address space for Vpn NatRule mapping.
portRange      | Yes      | Port range for Vpn NatRule mapping.

### addressSpace

![Parameter Setting](https://img.shields.io/badge/parameter-required-orange?style=flat-square)

Address space for Vpn NatRule mapping.

### portRange

![Parameter Setting](https://img.shields.io/badge/parameter-required-orange?style=flat-square)

Port range for Vpn NatRule mapping.

## Outputs

Name | Type | Description
---- | ---- | -----------
VpnNatRuleMapping | object | Vpn NatRule mapping.

## Snippets

### Parameter file

```json
{
    "$schema": "https://schema.management.azure.com/schemas/2015-01-01/deploymentParameters.json#",
    "contentVersion": "1.0.0.1",
    "metadata": {
        "template": "reference/vpnnatrulemapping.json"
    },
    "parameters": {
        "addressSpace": {
            "value": ""
        },
        "portRange": {
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

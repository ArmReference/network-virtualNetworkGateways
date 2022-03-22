# Azure template

## Parameters

Parameter name | Required | Description
-------------- | -------- | -----------
name           | Yes      | Gateway SKU name.
tier           | Yes      | Gateway SKU tier.
capactiy       | No       | The capacity.

### name

![Parameter Setting](https://img.shields.io/badge/parameter-required-orange?style=flat-square)

Gateway SKU name.

- Allowed values: `Basic`, `ErGw1AZ`, `ErGw2AZ`, `ErGw3AZ`, `HighPerformance`, `Standard`, `UltraPerformance`, `VpnGw1`, `VpnGw1AZ`, `VpnGw2`, `VpnGw2AZ`, `VpnGw3`, `VpnGw3AZ`, `VpnGw4`, `VpnGw4AZ`, `VpnGw5`, `VpnGw5AZ`

### tier

![Parameter Setting](https://img.shields.io/badge/parameter-required-orange?style=flat-square)

Gateway SKU tier.

- Allowed values: `Basic`, `ErGw1AZ`, `ErGw2AZ`, `ErGw3AZ`, `HighPerformance`, `Standard`, `UltraPerformance`, `VpnGw1`, `VpnGw1AZ`, `VpnGw2`, `VpnGw2AZ`, `VpnGw3`, `VpnGw3AZ`, `VpnGw4`, `VpnGw4AZ`, `VpnGw5`, `VpnGw5AZ`

### capactiy

![Parameter Setting](https://img.shields.io/badge/parameter-optional-green?style=flat-square)

The capacity.

- Default value: `0`

## Outputs

Name | Type | Description
---- | ---- | -----------
virtualNetworkGatewaySku | object | VirtualNetworkGatewaySku details.

## Snippets

### Parameter file

```json
{
    "$schema": "https://schema.management.azure.com/schemas/2015-01-01/deploymentParameters.json#",
    "contentVersion": "1.0.0.0",
    "metadata": {
        "template": "reference/virtualNetworkGatewaySku.json"
    },
    "parameters": {
        "name": {
            "value": ""
        },
        "tier": {
            "value": ""
        },
        "capactiy": {
            "value": 0
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

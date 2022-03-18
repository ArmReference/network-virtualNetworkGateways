# Azure template

## Parameters

Parameter name | Required | Description
-------------- | -------- | -----------
asn            | No       | The BGP speaker's ASN.
peerWeight     | No       | The weight added to routes learned from this BGP speaker.

### asn

![Parameter Setting](https://img.shields.io/badge/parameter-optional-green?style=flat-square)

The BGP speaker's ASN.

- Default value: `0`

### peerWeight

![Parameter Setting](https://img.shields.io/badge/parameter-optional-green?style=flat-square)

The weight added to routes learned from this BGP speaker.

- Default value: `0`

## Outputs

Name | Type | Description
---- | ---- | -----------
bgpSettings | object |

## Snippets

### Parameter file

```json
{
    "$schema": "https://schema.management.azure.com/schemas/2015-01-01/deploymentParameters.json#",
    "contentVersion": "1.0.0.0",
    "metadata": {
        "template": "reference/bgpSettings.json"
    },
    "parameters": {
        "asn": {
            "value": 0
        },
        "peerWeight": {
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

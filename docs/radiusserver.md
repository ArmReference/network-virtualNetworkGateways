# Azure template

## Parameters

Parameter name | Required | Description
-------------- | -------- | -----------
radiusServerAddress | No       | The address of this radius server.
radiusServerScore | No       | The initial score assigned to this radius server.
radiusServerSecret | No       | The secret used for this radius server.

### radiusServerAddress

![Parameter Setting](https://img.shields.io/badge/parameter-optional-green?style=flat-square)

The address of this radius server.

### radiusServerScore

![Parameter Setting](https://img.shields.io/badge/parameter-optional-green?style=flat-square)

The initial score assigned to this radius server.

- Default value: `0`

### radiusServerSecret

![Parameter Setting](https://img.shields.io/badge/parameter-optional-green?style=flat-square)

The secret used for this radius server.

## Outputs

Name | Type | Description
---- | ---- | -----------
RadiusServer | object | Radius Server Settings.

## Snippets

### Parameter file

```json
{
    "$schema": "https://schema.management.azure.com/schemas/2015-01-01/deploymentParameters.json#",
    "contentVersion": "1.0.0.0",
    "metadata": {
        "template": "reference/radiusserver.json"
    },
    "parameters": {
        "radiusServerAddress": {
            "value": ""
        },
        "radiusServerScore": {
            "value": 0
        },
        "radiusServerSecret": {
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

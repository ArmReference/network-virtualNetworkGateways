# Azure template

## Parameters

Parameter name | Required | Description
-------------- | -------- | -----------
dhGroup        | Yes      | The DH Group used in IKE Phase 1 for initial SA.
ikeEncryption  | Yes      | The IKE encryption algorithm (IKE phase 2).
ikeIntegrity   | Yes      | The IKE integrity algorithm (IKE phase 2).
ipsecEncryption | Yes      | The IPSec encryption algorithm (IKE phase 1).
ipsecIntegrity | Yes      | The IPSec integrity algorithm (IKE phase 1).
pfsGroup       | Yes      | The Pfs Group used in IKE Phase 2 for new child SA.
saDataSizeKilobytes | Yes      | The IPSec Security Association (also called Quick Mode or Phase 2 SA) payload size in KB for a site to site VPN tunnel.
saLifeTimeSeconds | Yes      | The IPSec Security Association (also called Quick Mode or Phase 2 SA) lifetime in seconds for a site to site VPN tunnel.

### dhGroup

![Parameter Setting](https://img.shields.io/badge/parameter-required-orange?style=flat-square)

The DH Group used in IKE Phase 1 for initial SA.

- Allowed values: `DHGroup1`, `DHGroup14`, `DHGroup2`, `DHGroup2048`, `DHGroup24`, `ECP256`, `ECP384`, `None`

### ikeEncryption

![Parameter Setting](https://img.shields.io/badge/parameter-required-orange?style=flat-square)

The IKE encryption algorithm (IKE phase 2).

- Allowed values: `AES128`, `AES192`, `AES256`, `DES`, `DES3`, `GCMAES128`, `GCMAES256`

### ikeIntegrity

![Parameter Setting](https://img.shields.io/badge/parameter-required-orange?style=flat-square)

The IKE integrity algorithm (IKE phase 2).

- Allowed values: `GCMAES128`, `GCMAES256`, `MD5`, `SHA1`, `SHA256`, `SHA384`

### ipsecEncryption

![Parameter Setting](https://img.shields.io/badge/parameter-required-orange?style=flat-square)

The IPSec encryption algorithm (IKE phase 1).

- Allowed values: `AES128`, `AES192`, `AES256`, `DES`, `DES3`, `GCMAES128`, `GCMAES256`, `None`

### ipsecIntegrity

![Parameter Setting](https://img.shields.io/badge/parameter-required-orange?style=flat-square)

The IPSec integrity algorithm (IKE phase 1).

- Allowed values: `AES128`, `AES192`, `AES256`, `MD5`, `SHA1`, `SHA256`

### pfsGroup

![Parameter Setting](https://img.shields.io/badge/parameter-required-orange?style=flat-square)

The Pfs Group used in IKE Phase 2 for new child SA.

- Allowed values: `ECP256`, `ECP384`, `None`, `PFS1`, `PFS14`, `PFS2`, `PFS2048`, `PFS24`, `PFSMM`

### saDataSizeKilobytes

![Parameter Setting](https://img.shields.io/badge/parameter-required-orange?style=flat-square)

The IPSec Security Association (also called Quick Mode or Phase 2 SA) payload size in KB for a site to site VPN tunnel.

### saLifeTimeSeconds

![Parameter Setting](https://img.shields.io/badge/parameter-required-orange?style=flat-square)

The IPSec Security Association (also called Quick Mode or Phase 2 SA) lifetime in seconds for a site to site VPN tunnel.

## Outputs

Name | Type | Description
---- | ---- | -----------
IpsecPolicy | object | An IPSec Policy configuration for a virtual network gateway connection.

## Snippets

### Parameter file

```json
{
    "$schema": "https://schema.management.azure.com/schemas/2015-01-01/deploymentParameters.json#",
    "contentVersion": "1.0.0.1",
    "metadata": {
        "template": "reference/ipsecpolicy.json.json"
    },
    "parameters": {
        "dhGroup": {
            "value": ""
        },
        "ikeEncryption": {
            "value": ""
        },
        "ikeIntegrity": {
            "value": ""
        },
        "ipsecEncryption": {
            "value": ""
        },
        "ipsecIntegrity": {
            "value": ""
        },
        "pfsGroup": {
            "value": ""
        },
        "saDataSizeKilobytes": {
            "value": 0
        },
        "saLifeTimeSeconds": {
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

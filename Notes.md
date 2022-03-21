# Resource Notes

## Microsoft.Network/virtualNetworkGateways

## APIVersion 2021-05-01

This template defines the properties required to deploy a VirtualNetwork Gateway in Azure.

### Schema

It appeares that the ApiVersion above can't actually be found the [Microsoft.Network.json](https://github.com/Azure/azure-resource-manager-schemas/tree/main/schemas/2021-05-01) appears to be missing from the folder. I've created an issue for this [here](https://github.com/Azure/azure-resource-manager-schemas/issues/2264).

### Properties

This resource doesn't have a defined properties object, everything is referenced as properties.bgpsettings, this is not an issue just odd, considering the last few I've worked through had a properties object of some sort.

### VirtualNetworkGatewayNatRule

It seems we have a stray type, this is outside of the properties and I don't see it referenced in the examples or the schema

### vpnAuthenticationTypes

The property values for this property are not documented outside of the [schema](https://github.com/Azure/azure-resource-manager-schemas/blob/main/schemas/2020-11-01/Microsoft.Network.json#L18315). They are documented in the arm template [documentation](https://docs.microsoft.com/en-us/azure/templates/microsoft.network/2021-05-01/virtualnetworkgateways?tabs=bicep#vpnclientconfiguration).


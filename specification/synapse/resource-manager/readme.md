# Azure Synapse Analytics

> see https://aka.ms/autorest

This is the AutoRest configuration file for Azure Synapse Analytics.



---
## Getting Started
To build the SDK for Azure Synapse Analytics, [Install AutoRest](https://aka.ms/autorest/install) and in this folder, run:

> `autorest`

To see additional help and options, run:

> `autorest --help`
---

## Configuration


### Basic Information
These are the global settings for the Azure Synapse Analytics API.

``` yaml
title: SynapseManagementClient
description: Azure Synapse Analytics Management Client
openapi-type: arm
azure-arm: true
tag: package-2019-06-01-preview
```

### Tag: package-2019-06-01-preview

These settings apply only when `--tag=package-2019-06-01-preview` is specified on the command line.

``` yaml $(tag) == 'package-2019-06-01-preview'
input-file:
- Microsoft.Synapse/preview/2019-06-01-preview/bigDataPool.json
- Microsoft.Synapse/preview/2019-06-01-preview/checkNameAvailability.json
- Microsoft.Synapse/preview/2019-06-01-preview/firewallRule.json
- Microsoft.Synapse/preview/2019-06-01-preview/operations.json
- Microsoft.Synapse/preview/2019-06-01-preview/sqlPool.json
- Microsoft.Synapse/preview/2019-06-01-preview/workspace.json
- Microsoft.Synapse/preview/2019-06-01-preview/integrationRuntime.json
- Microsoft.Synapse/preview/2019-06-01-preview/privateLinkResources.json
- Microsoft.Synapse/preview/2019-06-01-preview/privateEndpointConnections.json
```

## Suppressions

``` yaml
directive:
  - suppress: EnumInsteadOfBoolean
    reason: This boolean values are actually boolean in the model.
  - suppress: TrackedResourceListByImmediateParent
    reason: Does not apply to workspace/operationStatus and workspace/operationResults .
  - suppress: PostOperationIdContainsUrlVerb
    reason: ReplaceAllIpFirewallRules has a nonstandard verb ReplaceAll.
  - suppress: TrackedResourceListByResourceGroup
    reason: Does not apply to sqlPool and bigDataPool as they are nested tracked resources
  - suppress: TrackedResourceListBySubscription
    reason: Does not apply to sqlPool and bigDataPool as they are nested tracked resources
```

---
# Code Generation


## Swagger to SDK

This section describes what SDK should be generated by the automatic system.
This is not used by Autorest itself.

``` yaml $(swagger-to-sdk)
swagger-to-sdk:
  - repo: azure-sdk-for-net
  - repo: azure-sdk-for-js
  - repo: azure-sdk-for-java
  - repo: azure-sdk-for-python
  - repo: azure-sdk-for-go
```

## Python

See configuration in [readme.python.md](./readme.python.md)

## Java

See configuration in [readme.java.md](./readme.java.md)

## C#

These settings apply only when `--csharp` is specified on the command line.
Please also specify `--csharp-sdks-folder=<path to "SDKs" directory of your azure-sdk-for-net clone>`.

``` yaml $(csharp)
csharp:
  license-header: MICROSOFT_MIT_NO_VERSION
  namespace: Microsoft.Azure.Management.Synapse
  output-folder: $(csharp-sdks-folder)/synapse/Microsoft.Azure.Management.Synapse/src/Generated
  clear-output-folder: true
```

## Go

See configuration in [readme.go.md](./readme.go.md)

## Multi-API/Profile support for AutoRest v3 generators 

AutoRest V3 generators require the use of `--tag=all-api-versions` to select api files.

This block is updated by an automatic script. Edits may be lost!

``` yaml $(tag) == 'all-api-versions' /* autogenerated */
# include the azure profile definitions from the standard location
require: $(this-folder)/../../../profiles/readme.md

# all the input files across all versions
input-file:
  - $(this-folder)/Microsoft.Synapse/preview/2019-06-01-preview/bigDataPool.json
  - $(this-folder)/Microsoft.Synapse/preview/2019-06-01-preview/checkNameAvailability.json
  - $(this-folder)/Microsoft.Synapse/preview/2019-06-01-preview/firewallRule.json
  - $(this-folder)/Microsoft.Synapse/preview/2019-06-01-preview/operations.json
  - $(this-folder)/Microsoft.Synapse/preview/2019-06-01-preview/sqlPool.json
  - $(this-folder)/Microsoft.Synapse/preview/2019-06-01-preview/workspace.json
  - $(this-folder)/Microsoft.Synapse/preview/2019-06-01-preview/integrationRuntime.json
  - $(this-folder)/Microsoft.Synapse/preview/2019-06-01-preview/privateLinkResources.json
  - $(this-folder)/Microsoft.Synapse/preview/2019-06-01-preview/privateEndpointConnections.json

```

If there are files that should not be in the `all-api-versions` set, 
uncomment the  `exclude-file` section below and add the file paths.

``` yaml $(tag) == 'all-api-versions'
#exclude-file: 
#  - $(this-folder)/Microsoft.Example/stable/2010-01-01/somefile.json
```

---
type: docs
title: "Reference: applications.datastores/mongodatabases@2023-10-01-preview"
linkTitle: "mongodatabases"
description: "Detailed reference documentation for applications.datastores/mongodatabases@2023-10-01-preview"
---

{{< schemaExample >}}

## Schema

### Top-Level Resource

#### Properties

| Property | Type | Description |
|----------|------|-------------|
| **apiVersion** | '2023-10-01-preview' | The resource api version <br />_(read-only, deploy-time constant)_ |
| **id** | string | The resource id <br />_(read-only, deploy-time constant)_ |
| **location** | string | The geo-location where the resource lives <br />_(required)_ |
| **name** | string | The resource name <br />_(required, deploy-time constant)_ |
| **properties** | [MongoDatabaseProperties](#mongodatabaseproperties) | MongoDatabase portable resource properties |
| **systemData** | [SystemData](#systemdata) | Metadata pertaining to creation and last modification of the resource. <br />_(read-only)_ |
| **tags** | [TrackedResourceTags](#trackedresourcetags) | Resource tags. |
| **type** | 'Applications.Datastores/mongoDatabases' | The resource type <br />_(read-only, deploy-time constant)_ |

### Function listSecrets (Applications.Datastores/mongoDatabases@2023-10-01-preview)

* **Resource**: Applications.Datastores/mongoDatabases
* **ApiVersion**: 2023-10-01-preview
* **Input**: any
* **Output**: [MongoDatabaseListSecretsResult](#mongodatabaselistsecretsresult)

### MongoDatabaseProperties

#### Properties

| Property | Type | Description |
|----------|------|-------------|
| **application** | string | Fully qualified resource ID for the application that the portable resource is consumed by (if applicable) |
| **database** | string | Database name of the target Mongo database |
| **environment** | string | Fully qualified resource ID for the environment that the portable resource is linked to <br />_(required)_ |
| **host** | string | Host name of the target Mongo database |
| **port** | int | Port value of the target Mongo database |
| **provisioningState** | 'Accepted' | 'Canceled' | 'Deleting' | 'Failed' | 'Provisioning' | 'Succeeded' | 'Updating' | Provisioning state of the resource at the time the operation was called <br />_(read-only)_ |
| **recipe** | [Recipe](#recipe) | The recipe used to automatically deploy underlying infrastructure for a portable resource |
| **resourceProvisioning** | 'manual' | 'recipe' | Specifies how the underlying service/resource is provisioned and managed. Available values are 'recipe', where Radius manages the lifecycle of the resource through a Recipe, and 'manual', where a user manages the resource and provides the values. |
| **resources** | [ResourceReference](#resourcereference)[] | List of the resource IDs that support the MongoDB resource |
| **secrets** | [MongoDatabaseSecrets](#mongodatabasesecrets) | The secret values for the given MongoDatabase resource |
| **status** | [ResourceStatus](#resourcestatus) | Status of a resource. <br />_(read-only)_ |
| **username** | string | Username to use when connecting to the target Mongo database |

### Recipe

#### Properties

| Property | Type | Description |
|----------|------|-------------|
| **name** | string | The name of the recipe within the environment to use <br />_(required)_ |
| **parameters** | any | Any object |

### ResourceReference

#### Properties

| Property | Type | Description |
|----------|------|-------------|
| **id** | string | Resource id of an existing resource <br />_(required)_ |

### MongoDatabaseSecrets

#### Properties

| Property | Type | Description |
|----------|------|-------------|
| **connectionString** | string | Connection string used to connect to the target Mongo database |
| **password** | string | Password to use when connecting to the target Mongo database |

### ResourceStatus

#### Properties

| Property | Type | Description |
|----------|------|-------------|
| **compute** | [EnvironmentCompute](#environmentcompute) | Represents backing compute resource |
| **outputResources** | [OutputResource](#outputresource)[] | Properties of an output resource |
| **recipe** | [RecipeStatus](#recipestatus) | Recipe status at deployment time for a resource. <br />_(read-only)_ |

### EnvironmentCompute

* **Discriminator**: kind

#### Base Properties

| Property | Type | Description |
|----------|------|-------------|
| **identity** | [IdentitySettings](#identitysettings) | IdentitySettings is the external identity setting. |
| **resourceId** | string | The resource id of the compute resource for application environment. |

#### KubernetesCompute

##### Properties

| Property | Type | Description |
|----------|------|-------------|
| **kind** | 'kubernetes' | Discriminator property for EnvironmentCompute. <br />_(required)_ |
| **namespace** | string | The namespace to use for the environment. <br />_(required)_ |


### IdentitySettings

#### Properties

| Property | Type | Description |
|----------|------|-------------|
| **kind** | 'azure.com.workload' | 'undefined' | IdentitySettingKind is the kind of supported external identity setting <br />_(required)_ |
| **oidcIssuer** | string | The URI for your compute platform's OIDC issuer |
| **resource** | string | The resource ID of the provisioned identity |

### OutputResource

#### Properties

| Property | Type | Description |
|----------|------|-------------|
| **id** | string | The UCP resource ID of the underlying resource. |
| **localId** | string | The logical identifier scoped to the owning Radius resource. This is only needed or used when a resource has a dependency relationship. LocalIDs do not have any particular format or meaning beyond being compared to determine dependency relationships. |
| **radiusManaged** | bool | Determines whether Radius manages the lifecycle of the underlying resource. |

### RecipeStatus

#### Properties

| Property | Type | Description |
|----------|------|-------------|
| **templateKind** | string | TemplateKind is the kind of the recipe template used by the portable resource upon deployment. <br />_(required)_ |
| **templatePath** | string | TemplatePath is the path of the recipe consumed by the portable resource upon deployment. <br />_(required)_ |
| **templateVersion** | string | TemplateVersion is the version number of the template. |

### SystemData

#### Properties

| Property | Type | Description |
|----------|------|-------------|
| **createdAt** | string | The timestamp of resource creation (UTC). |
| **createdBy** | string | The identity that created the resource. |
| **createdByType** | 'Application' | 'Key' | 'ManagedIdentity' | 'User' | The type of identity that created the resource. |
| **lastModifiedAt** | string | The timestamp of resource last modification (UTC) |
| **lastModifiedBy** | string | The identity that last modified the resource. |
| **lastModifiedByType** | 'Application' | 'Key' | 'ManagedIdentity' | 'User' | The type of identity that created the resource. |

### TrackedResourceTags

#### Properties

* **none**

#### Additional Properties

* **Additional Properties Type**: string

### MongoDatabaseListSecretsResult

#### Properties

| Property | Type | Description |
|----------|------|-------------|
| **connectionString** | string | Connection string used to connect to the target Mongo database <br />_(read-only)_ |
| **password** | string | Password to use when connecting to the target Mongo database <br />_(read-only)_ |


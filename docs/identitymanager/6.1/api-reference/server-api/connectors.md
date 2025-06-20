# Connectors

### /api/Connectors/Agent

#### Get

##### Summary:

Returns all the agents according to the provided query.

##### Parameters:

| Name                | Description                                          | Required | Type | Reference |
| ------------------- | ---------------------------------------------------- | -------- | ---- | --------- |
| squery              | Query compliant to the API query grammar.            | False    |      |           |
| Path                | Represents the permission path.                      | False    |      |           |
| QueryRootEntityType | Defines the query root entity type.                  | False    |      |           |
| QueryBinding        | Defines the query binding.                           | False    |      |           |
| PageSize            | Page size.                                           | False    |      |           |
| ContinuationToken   | ContinuationToken returned by previous page request. | False    |      |           |
| api-version         | The requested API version                            | True     |      |           |

##### Responses:

| Code | Description     | Reference |
| ---- | --------------- | --------- |
| 200  | The agent list. |           |

#### Post

##### Summary:

Creates a agent.

##### Parameters:

| Name        | Description               | Required | Type | Reference |
| ----------- | ------------------------- | -------- | ---- | --------- |
| api-version | The requested API version | True     |      |           |

##### Responses:

| Code | Description                       | Reference |
| ---- | --------------------------------- | --------- |
| 200  | The result of the agent creation. |           |

### /api/Connectors/Agent/`{id}`

#### Get

##### Summary:

Returns a agent corresponding to the provided identifier and its information according to the
provided query.

##### Parameters:

| Name                | Description                               | Required | Type | Reference |
| ------------------- | ----------------------------------------- | -------- | ---- | --------- |
| id                  | Identifier of the agent.                  | True     |      |           |
| squery              | Query compliant to the API query grammar. | False    |      |           |
| Path                | Represents the permission path.           | False    |      |           |
| QueryRootEntityType | Defines the query root entity type.       | False    |      |           |
| QueryBinding        | Defines the query binding.                | False    |      |           |
| api-version         | The requested API version                 | True     |      |           |

##### Responses:

| Code | Description | Reference |
| ---- | ----------- | --------- |
| 200  | The agent.  |           |

#### Put

##### Summary:

Updates a agent.

##### Parameters:

| Name        | Description                        | Required | Type | Reference |
| ----------- | ---------------------------------- | -------- | ---- | --------- |
| id          | Identifier of the agent to update. | True     |      |           |
| api-version | The requested API version          | True     |      |           |

##### Responses:

| Code | Description                     | Reference |
| ---- | ------------------------------- | --------- |
| 200  | The result of the agent update. |           |

#### Delete

##### Summary:

Deletes a agent.

##### Parameters:

| Name        | Description                        | Required | Type | Reference |
| ----------- | ---------------------------------- | -------- | ---- | --------- |
| id          | Identifier of the agent to delete. | True     |      |           |
| api-version | The requested API version          | True     |      |           |

##### Responses:

| Code | Description                     | Reference |
| ---- | ------------------------------- | --------- |
| 200  | The result of the agent delete. |           |

### /api/Connectors/Connection

#### Get

##### Summary:

Returns all the connection packages according to the provided query.

##### Parameters:

| Name                | Description                                          | Required | Type | Reference |
| ------------------- | ---------------------------------------------------- | -------- | ---- | --------- |
| squery              | Query compliant to the API query grammar.            | False    |      |           |
| Path                | Represents the permission path.                      | False    |      |           |
| QueryRootEntityType | Defines the query root entity type.                  | False    |      |           |
| QueryBinding        | Defines the query binding.                           | False    |      |           |
| PageSize            | Page size.                                           | False    |      |           |
| ContinuationToken   | ContinuationToken returned by previous page request. | False    |      |           |
| api-version         | The requested API version                            | True     |      |           |

##### Responses:

| Code | Description         | Reference |
| ---- | ------------------- | --------- |
| 200  | The connector list. |           |

#### Post

##### Summary:

Creates a connection.

##### Parameters:

| Name        | Description               | Required | Type | Reference |
| ----------- | ------------------------- | -------- | ---- | --------- |
| api-version | The requested API version | True     |      |           |

##### Responses:

| Code | Description                           | Reference |
| ---- | ------------------------------------- | --------- |
| 200  | The result of the connector creation. |           |

### /api/Connectors/Connection/`{id}`

#### Get

##### Summary:

Returns a connection package corresponding to the provided identifier and its information according
to the provided query.

##### Parameters:

| Name                | Description                               | Required | Type | Reference |
| ------------------- | ----------------------------------------- | -------- | ---- | --------- |
| id                  | Identifier of the connector.              | True     |      |           |
| squery              | Query compliant to the API query grammar. | False    |      |           |
| Path                | Represents the permission path.           | False    |      |           |
| QueryRootEntityType | Defines the query root entity type.       | False    |      |           |
| QueryBinding        | Defines the query binding.                | False    |      |           |
| api-version         | The requested API version                 | True     |      |           |

##### Responses:

| Code | Description    | Reference |
| ---- | -------------- | --------- |
| 200  | The connector. |           |

#### Put

##### Summary:

Updates a connector.

##### Parameters:

| Name        | Description                            | Required | Type | Reference |
| ----------- | -------------------------------------- | -------- | ---- | --------- |
| id          | Identifier of the connector to update. | True     |      |           |
| api-version | The requested API version              | True     |      |           |

##### Responses:

| Code | Description                         | Reference |
| ---- | ----------------------------------- | --------- |
| 200  | The result of the connector update. |           |

#### Delete

##### Summary:

Deletes a connector.

##### Parameters:

| Name        | Description                            | Required | Type | Reference |
| ----------- | -------------------------------------- | -------- | ---- | --------- |
| id          | Identifier of the connector to delete. | True     |      |           |
| api-version | The requested API version              | True     |      |           |

##### Responses:

| Code | Description                         | Reference |
| ---- | ----------------------------------- | --------- |
| 200  | The result of the connector delete. |           |

### /api/Connectors/ConnectionPackage

#### Get

##### Summary:

Returns all the connection packages according to the provided query.

##### Parameters:

| Name                | Description                                          | Required | Type | Reference |
| ------------------- | ---------------------------------------------------- | -------- | ---- | --------- |
| squery              | Query compliant to the API query grammar.            | False    |      |           |
| Path                | Represents the permission path.                      | False    |      |           |
| QueryRootEntityType | Defines the query root entity type.                  | False    |      |           |
| QueryBinding        | Defines the query binding.                           | False    |      |           |
| PageSize            | Page size.                                           | False    |      |           |
| ContinuationToken   | ContinuationToken returned by previous page request. | False    |      |           |
| api-version         | The requested API version                            | True     |      |           |

##### Responses:

| Code | Description         | Reference |
| ---- | ------------------- | --------- |
| 200  | The connector list. |           |

### /api/Connectors/ConnectionPackage/`{id}`

#### Get

##### Summary:

Returns a connection package corresponding to the provided identifier and its information according
to the provided query.

##### Parameters:

| Name                | Description                               | Required | Type | Reference |
| ------------------- | ----------------------------------------- | -------- | ---- | --------- |
| id                  | Identifier of the connector.              | True     |      |           |
| squery              | Query compliant to the API query grammar. | False    |      |           |
| Path                | Represents the permission path.           | False    |      |           |
| QueryRootEntityType | Defines the query root entity type.       | False    |      |           |
| QueryBinding        | Defines the query binding.                | False    |      |           |
| api-version         | The requested API version                 | True     |      |           |

##### Responses:

| Code | Description    | Reference |
| ---- | -------------- | --------- |
| 200  | The connector. |           |

### /api/Connectors/Connector

#### Get

##### Summary:

Returns all the connectors according to the provided query.

##### Parameters:

| Name                | Description                                          | Required | Type | Reference |
| ------------------- | ---------------------------------------------------- | -------- | ---- | --------- |
| squery              | Query compliant to the API query grammar.            | False    |      |           |
| Path                | Represents the permission path.                      | False    |      |           |
| QueryRootEntityType | Defines the query root entity type.                  | False    |      |           |
| QueryBinding        | Defines the query binding.                           | False    |      |           |
| PageSize            | Page size.                                           | False    |      |           |
| ContinuationToken   | ContinuationToken returned by previous page request. | False    |      |           |
| api-version         | The requested API version                            | True     |      |           |

##### Responses:

| Code | Description         | Reference |
| ---- | ------------------- | --------- |
| 200  | The connector list. |           |

#### Post

##### Summary:

Creates a connector.

##### Parameters:

| Name        | Description               | Required | Type | Reference |
| ----------- | ------------------------- | -------- | ---- | --------- |
| api-version | The requested API version | True     |      |           |

##### Responses:

| Code | Description                           | Reference |
| ---- | ------------------------------------- | --------- |
| 200  | The result of the connector creation. |           |

### /api/Connectors/Connector/`{id}`

#### Get

##### Summary:

Returns a connector corresponding to the provided identifier and its information according to the
provided query.

##### Parameters:

| Name                | Description                               | Required | Type | Reference |
| ------------------- | ----------------------------------------- | -------- | ---- | --------- |
| id                  | Identifier of the connector.              | True     |      |           |
| squery              | Query compliant to the API query grammar. | False    |      |           |
| Path                | Represents the permission path.           | False    |      |           |
| QueryRootEntityType | Defines the query root entity type.       | False    |      |           |
| QueryBinding        | Defines the query binding.                | False    |      |           |
| api-version         | The requested API version                 | True     |      |           |

##### Responses:

| Code | Description    | Reference |
| ---- | -------------- | --------- |
| 200  | The connector. |           |

#### Put

##### Summary:

Updates a connector.

##### Parameters:

| Name        | Description                            | Required | Type | Reference |
| ----------- | -------------------------------------- | -------- | ---- | --------- |
| id          | Identifier of the connector to update. | True     |      |           |
| api-version | The requested API version              | True     |      |           |

##### Responses:

| Code | Description                         | Reference |
| ---- | ----------------------------------- | --------- |
| 200  | The result of the connector update. |           |

#### Delete

##### Summary:

Deletes a connector.

##### Parameters:

| Name        | Description                            | Required | Type | Reference |
| ----------- | -------------------------------------- | -------- | ---- | --------- |
| id          | Identifier of the connector to delete. | True     |      |           |
| force       |                                        | False    |      |           |
| api-version | The requested API version              | True     |      |           |

##### Responses:

| Code | Description                         | Reference |
| ---- | ----------------------------------- | --------- |
| 200  | The result of the connector delete. |           |

### /api/Connectors/Connector/ResourceTypes/`{id}`

#### Get

##### Summary:

Returns the resource type ids corresponding to the provided connector identifier.

##### Parameters:

| Name        | Description                  | Required | Type | Reference |
| ----------- | ---------------------------- | -------- | ---- | --------- |
| id          | Identifier of the connector. | True     |      |           |
| api-version | The requested API version    | True     |      |           |

##### Responses:

| Code | Description | Reference |
| ---- | ----------- | --------- |
| 200  | Success     |           |

### /api/Connectors/EntityAssociationMapping

#### Get

##### Summary:

Returns all the entity types mappings according to the provided query.

##### Parameters:

| Name                | Description                                          | Required | Type | Reference |
| ------------------- | ---------------------------------------------------- | -------- | ---- | --------- |
| squery              | Query compliant to the API query grammar.            | False    |      |           |
| Path                | Represents the permission path.                      | False    |      |           |
| QueryRootEntityType | Defines the query root entity type.                  | False    |      |           |
| QueryBinding        | Defines the query binding.                           | False    |      |           |
| PageSize            | Page size.                                           | False    |      |           |
| ContinuationToken   | ContinuationToken returned by previous page request. | False    |      |           |
| api-version         | The requested API version                            | True     |      |           |

##### Responses:

| Code | Description           | Reference |
| ---- | --------------------- | --------- |
| 200  | The entity type list. |           |

### /api/Connectors/EntityPropertyMapping

#### Get

##### Summary:

Returns all the entity property mappings according to the provided query.

##### Parameters:

| Name                | Description                                          | Required | Type | Reference |
| ------------------- | ---------------------------------------------------- | -------- | ---- | --------- |
| squery              | Query compliant to the API query grammar.            | False    |      |           |
| Path                | Represents the permission path.                      | False    |      |           |
| QueryRootEntityType | Defines the query root entity type.                  | False    |      |           |
| QueryBinding        | Defines the query binding.                           | False    |      |           |
| PageSize            | Page size.                                           | False    |      |           |
| ContinuationToken   | ContinuationToken returned by previous page request. | False    |      |           |
| api-version         | The requested API version                            | True     |      |           |

##### Responses:

| Code | Description                       | Reference |
| ---- | --------------------------------- | --------- |
| 200  | The entity property mapping list. |           |

### /api/Connectors/EntityTypeMapping

#### Get

##### Summary:

Returns all the entity types mappings according to the provided query.

##### Parameters:

| Name                | Description                                          | Required | Type | Reference |
| ------------------- | ---------------------------------------------------- | -------- | ---- | --------- |
| squery              | Query compliant to the API query grammar.            | False    |      |           |
| Path                | Represents the permission path.                      | False    |      |           |
| QueryRootEntityType | Defines the query root entity type.                  | False    |      |           |
| QueryBinding        | Defines the query binding.                           | False    |      |           |
| PageSize            | Page size.                                           | False    |      |           |
| ContinuationToken   | ContinuationToken returned by previous page request. | False    |      |           |
| api-version         | The requested API version                            | True     |      |           |

##### Responses:

| Code | Description           | Reference |
| ---- | --------------------- | --------- |
| 200  | The entity type list. |           |

### /api/Connectors/EntityTypeMapping/`{id}`

#### Get

##### Parameters:

| Name                | Description                         | Required | Type | Reference |
| ------------------- | ----------------------------------- | -------- | ---- | --------- |
| id                  |                                     | True     |      |           |
| squery              |                                     | False    |      |           |
| Path                | Represents the permission path.     | False    |      |           |
| QueryRootEntityType | Defines the query root entity type. | False    |      |           |
| QueryBinding        | Defines the query binding.          | False    |      |           |
| api-version         | The requested API version           | True     |      |           |

##### Responses:

| Code | Description | Reference |
| ---- | ----------- | --------- |
| 200  | Success     |           |

### /api/Connectors/Mapping/PasswordResetSetting

#### Get

##### Summary:

Returns all the password reset settings according to the provided query.

##### Parameters:

| Name                | Description                                          | Required | Type | Reference |
| ------------------- | ---------------------------------------------------- | -------- | ---- | --------- |
| squery              | Query compliant to the API query grammar.            | False    |      |           |
| Path                | Represents the permission path.                      | False    |      |           |
| QueryRootEntityType | Defines the query root entity type.                  | False    |      |           |
| QueryBinding        | Defines the query binding.                           | False    |      |           |
| PageSize            | Page size.                                           | False    |      |           |
| ContinuationToken   | ContinuationToken returned by previous page request. | False    |      |           |
| api-version         | The requested API version                            | True     |      |           |

##### Responses:

| Code | Description                      | Reference |
| ---- | -------------------------------- | --------- |
| 200  | The password reset setting list. |           |

### /api/Connectors/Provisioning/ProvisioningData/`{id}`

#### Get

##### Summary:

Get provisioning orders from server for a connector.

##### Parameters:

| Name        | Description               | Required | Type | Reference |
| ----------- | ------------------------- | -------- | ---- | --------- |
| id          | Id of the connector.      | True     |      |           |
| api-version | The requested API version | True     |      |           |

##### Responses:

| Code | Description | Reference |
| ---- | ----------- | --------- |
| 200  | Success     |           |

### /api/Connectors/Provisioning/ProvisioningResults

#### Put

##### Summary:

Update the status of the provisioned resources.

##### Parameters:

| Name        | Description               | Required | Type | Reference |
| ----------- | ------------------------- | -------- | ---- | --------- |
| api-version | The requested API version | True     |      |           |

##### Responses:

| Code | Description | Reference |
| ---- | ----------- | --------- |
| 200  | Success     |           |

### /api/Connectors/Mapping/ResourceTypeMapping

#### Get

##### Summary:

Returns all the resource types mappings according to the provided query.

##### Parameters:

| Name                | Description                                          | Required | Type | Reference |
| ------------------- | ---------------------------------------------------- | -------- | ---- | --------- |
| squery              | Query compliant to the API query grammar.            | False    |      |           |
| Path                | Represents the permission path.                      | False    |      |           |
| QueryRootEntityType | Defines the query root entity type.                  | False    |      |           |
| QueryBinding        | Defines the query binding.                           | False    |      |           |
| PageSize            | Page size.                                           | False    |      |           |
| ContinuationToken   | ContinuationToken returned by previous page request. | False    |      |           |
| api-version         | The requested API version                            | True     |      |           |

##### Responses:

| Code | Description                     | Reference |
| ---- | ------------------------------- | --------- |
| 200  | The resource type mapping list. |           |

### /api/Connectors/Mapping/ResourceTypeMapping/`{id}`

#### Get

##### Summary:

Returns all the resource types mappings according to its id and the provided query.

##### Parameters:

| Name                | Description                               | Required | Type | Reference |
| ------------------- | ----------------------------------------- | -------- | ---- | --------- |
| id                  | Identifier of the single role.            | True     |      |           |
| squery              | Query compliant to the API query grammar. | False    |      |           |
| Path                | Represents the permission path.           | False    |      |           |
| QueryRootEntityType | Defines the query root entity type.       | False    |      |           |
| QueryBinding        | Defines the query binding.                | False    |      |           |
| api-version         | The requested API version                 | True     |      |           |

##### Responses:

| Code | Description                | Reference |
| ---- | -------------------------- | --------- |
| 200  | The resource type mapping. |           |

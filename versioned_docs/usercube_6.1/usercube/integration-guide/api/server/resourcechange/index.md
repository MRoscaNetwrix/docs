# ResourceChange

### /api/ResourceChange/{type}/{id}

#### Get

##### Summary:

Returns all the resource changes according to the provided query.

##### Parameters:

| Name | Description | Required | Type | Reference |
| --- | --- | --- | --- | --- |
| type | Entity type identifier. | True |  |  |
| id | Identifier of the job instance. | True |  |  |
| Path | Represents the permission path. | False |  |  |
| QueryRootEntityType | Defines the query root entity type. | False |  |  |
| QueryBinding | Defines the query binding. | False |  |  |
| PageSize | Page size. | False |  |  |
| ContinuationToken | ContinuationToken returned by previous page request. | False |  |  |
| primaryKeyFilter | Filter on primary key value. | False |  |  |
| changeOperationType | Filter on change operation type. | False |  | [ChangeOperation](/versioned_docs/usercube_6.1/usercube/integration-guide/api/server/index.md#ChangeOperation) |
| api-version | The requested API version | True |  |  |

##### Responses:

| Code | Description | Reference |
| --- | --- | --- |
| 200 | The resource changes list. |  |

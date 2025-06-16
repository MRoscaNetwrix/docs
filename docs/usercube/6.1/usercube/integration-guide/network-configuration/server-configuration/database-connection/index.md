# Connection to the Database

The connection of Usercube's server to the database is set through the `appsettings` top-level
`ConnectionString` and the `AzureCredentials` attributes:

| Name                              | Details                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| --------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| ConnectionString required         | **Type** String **Description** Identification token used to retrieve the connection information for the server to access Usercube's database in SQL Server. **Note:** must be compliant with [SQL Server connection string syntax](/versioned_docs/usercube_6.1/usercube/installation-guide/production-ready/server.md). [See more information in the Installation Guide](/versioned_docs/usercube_6.1/usercube/installation-guide/production-ready/server.md). **Example**`{     �     "ConnectionString": "data source=.;Database=Usercube;Integrated Security=SSPI;Min Pool Size=10;encrypt=false;"   }`                                                                                                                                                         |
| ConnectionStringGovernor required | **Type** String **Description** Identification token used to retrieve the connection information to SQL Server Resource Governor which is a feature used to manage SQL Server's workload and system resource consumption. **Info:** Resource Governor enables specifying limits on the amount of CPU, physical I/O, and memory that incoming application requests can use. **Note:** must be compliant with [SQL Server connection string syntax](/versioned_docs/usercube_6.1/usercube/installation-guide/production-ready/server.md). **Note:** all tasks and jobs use this connection string, when specified. **Example**`{     �     "ConnectionStringGovernor": "data source=.;Database=Usercube;Integrated Security=SSPI;Min Pool Size=10;encrypt=false;"   }` |
| AzureCredentials required         | **Type** [AzureCredentials](#azurecredentials) **Description** Settings used with the `ConnectionString` to access the database in SQL Server, hosted on Microsoft Entra ID (formerly Microsoft Azure AD).                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |

## AzureCredentials

The database can be accessed one of two ways:

- either by specifying `User Id` and `password` keywords directly in the connection string:

    > For example:
    >
    >                                 ```
    >
    > "ConnectionString": "data source=.;Database=UsercubeContoso;User
    > Id=UsercubeServerContoso;Password=myPassword;Min Pool Size=10;encrypt=false;"
    >
    > ```
    >
    > ```

- or, to avoid exposing the `User Id` and `password` in a connection string sent through the
  network, by using the built-in Microsoft Entra ID authentication method:

    > For example:
    >
    >                                 ```
    >
    > "ConnectionString": "Server=tcp:<server-name>.database.windows.net,1433;Initial
    > Catalog=<database-name>;Persist Security
    > Info=False;MultipleActiveResultSets=False;Encrypt=True;TrustServerCertificate=False;"
    >
    > ```
    >
    > ```

[See Microsoft's documentation for more details about authentication methods](https://docs.microsoft.com/en-us/sql/relational-databases/security/choose-an-authentication-mode?view=sql-server-ver15)

> The following example authenticates with ClientId and ClientSecret:
>
>                         ```
>
>                             appsettings.json
>
> { ... "ConnectionString": "Server=tcp:.database.windows.net,1433;Initial Catalog=;Persist Security
> Info=False;MultipleActiveResultSets=False;Encrypt=True;TrustServerCertificate=False;",
>
> "AzureCredentials": { "ClientId": "", "AADTenantId": "", "ClientSecret": "" } }
>
> ```
>
> ```

> The following example authenticates with a pfx-stored public key certificate (password-protected
> pfx archive):
>
>                         ```
>
>                             appsettings.json
>
> { ... "ConnectionString": "Server=tcp:.database.windows.net,1433;Initial Catalog=;Persist Security
> Info=False;MultipleActiveResultSets=False;Encrypt=True;TrustServerCertificate=False;",
>
> "AzureCredentials": { "ClientId": "", "AADTenantId": "", "EncryptionCertificate": { "File": "",
> "Password": "" } } }
>
> ```
>
> ```

| Name                                                           | Details                                                                                                                                                                                                                                                                                                                                                  |
| -------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| ClientId optional                                              | **Type** String **Description** Client ID obtained from Microsoft Entra ID when [registering Usercube as an application](https://learn.microsoft.com/en-us/entra/identity-platform/quickstart-register-app).                                                                                                                                             |
| AADTenantId optional                                           | **Type** String **Description** Microsoft Entra ID's tenant identifier obtained when [registering Usercube as an application](https://learn.microsoft.com/en-us/entra/identity-platform/quickstart-register-app).**Note:** remember to set Usercube as owner of the targeted database when registering Usercube as an application in Microsoft Entra ID. |
| ClientSecret optional                                          | **Type** String **Description** Microsoft Entra ID's client secret used by Usercube to authenticate.**Note:** used only if `EncryptionCertificate` is not specified.                                                                                                                                                                                     |
| EncryptionCertificate required, if ClientSecret is not defined | **Type** [`EncryptionCertificate`](/versioned_docs/usercube_6.1/usercube/integration-guide/network-configuration/server-configuration/general-purpose/index.md#encryptioncertificate) **Description** Location of the certificate used by Usercube to authenticate, instead of the `ClientSecret`.                                                       |

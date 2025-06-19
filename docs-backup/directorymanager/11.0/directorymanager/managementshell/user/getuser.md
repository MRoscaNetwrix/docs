# Get-User

Use the **Get-User** commandlet to retrieve basic information about a user that match your given
criteria.

## Syntax

```
Get-User
[[-Identity] <string[]>]
[-SearchContainer <string[]>]
[-SearchContainersScopeList <string>]
[-ShouldReturnCollection]
[-MaxItemsToDisplay <int>]
[-ObjectType <string[]>]
[-LdapFilter <string>]
[-SmartFilter <string>]
[-ServerFilter <string>]
[-AttributesToLoad <string[]>]
[-IdentityStoreId <int>]
[-SecurityToken <CustomClaimsPrincipal>]
[-Credential <pscredential>]
[<CommonParameters>]
```

## Required Parameter

- None

Example:

The following command retrieves the specified user from the connected identity store.

```
Get-User -Identity "Osama"
```

See Also

- [All Commands](/docs/directorymanager/11.0/directorymanager/managementshell/commands.md)
- [User Commands](/docs/directorymanager/11.0/directorymanager/managementshell/user/overview.md)
- [Parameters](/docs/directorymanager/11.0/directorymanager/managementshell/parameters/parameters.md)

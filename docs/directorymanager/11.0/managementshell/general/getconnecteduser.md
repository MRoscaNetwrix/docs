# Get-ConnectedUser

The **Get-ConnectedUser** commandlet retrieves the general information about the user connected to
the current instance of Management Shell.

## Syntax

```
Get-ConnectedUser
[-IdentityStoreId <Int32>]
[-SecurityToken <CustomClaimsPrincipal>]
[-Credential <PSCredential>]
[-WarningAction <ActionPreference>]
[-InformationAction <ActionPreference>]
[-WarningVariable <String>]
[-InformationVariable <String>]
[-PipelineVariable <String>]
[<CommonParameters>]
```

## Required Parameter

- None

Example 1:

The example displays the logon name of the connected user, account locked information, identity
store name, role name(s), and ObjectGuid.

```
Get-ConnectedUser
```

See Also

- [All Commands](/docs/directorymanager/11.0/managementshell/commands.md)
- [General Commands](/docs/directorymanager/11.0/managementshell/general/overview.md)
- [Parameters](/docs/directorymanager/11.0/managementshell/parameters/parameters.md)

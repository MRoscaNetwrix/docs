# Stop-Schedule

The commandlet **Stop-Schedule** stops a specified schedule if it is already running.

## Syntax

```
Stop-Schedule
[-ScheduleName <String>]
[-JobId <Int32>]
[-PassThru]
[-IdentityStoreId <Int32>]
[-SecurityToken <CustomClaimsPrincipal>]
[-WarningAction <ActionPreference>]
[-InformationAction <ActionPreference>]
[-WarningVariable <String>]
[-InformationVariable <String>]
[-PipelineVariable <String>]
[<CommonParameters>]
```

## Required Parameter

- ScheduleName

Example 1:

This example stops a schedule smm4 by name.

```
Stop-Schedule -ScheduleName smm4_
```

Example 2:

This example stops a schedule with job type as GUS.

```
Stop-Schedule -JobType GUS | Select-Object -Property Name | Invoke-Schedule
```

Example 3:

This example stops all the daily running GUS jobs.

```
Get-Schedule -JobType GUS -TriggerType RunDaily -MatchingCriteria And | Select-Object -Property Name | Stop-Schedule
```

See Also

- [All Commands](/docs/directorymanager/11.0/managementshell/commands.md)
- [Scheduling Commands](/docs/directorymanager/11.0/managementshell/scheduling/overview.md)
- [Parameters](/docs/directorymanager/11.0/managementshell/parameters/parameters.md)

# SavePreExistingAccessRightsTask

During an initial installation of Usercube, data normally provided by Usercube or through a derogation in the User Interface is already present in the application system.
Loaded during initialization, this data has the automatic flag and is all with provisioningstate to blocked or to pending. This Tool updates the data that are in this case and that are in the present or in the past. This update affects the following properties:

- Workflowstate
- consolidatedworkflowfoundstate
- consolidatedworkflowblockedstate
- consolidatedworkflowblockedcount
- consolidatedworkflowfoundcount
- provisioningState

## Examples

```

  <SavePreExistingAccessRightsTask DisplayName_L1="Pre Existing Assignment Default" Identifier="Pre_Existing_Assignment_Default" />
 
```

## Properties

| Property | Details |
| --- | --- |
| DisplayName\_L1   required | __Type__    String   __Description__   Display name of the task in language 1 (up to 16). |
| AssignedResourceNavigationSQL   optional | __Type__    String   __Description__   The sql to find all AssignedResourceNavigation for update.   _Alternative definition_: If _TaskType_ is:   - SqlCmdTask: Database provider |
| AssignedResourceScalarSQL   optional | __Type__    String   __Description__   The sql to find all AssignedResourceScalar for update.   _Alternative definition_: If _TaskType_ is:   - SqlCmdTask: SQL Command to execute |
| AssignedResourceTypeSQL   optional | __Type__    String   __Description__   The sql to find all AssignedResourceType for update.   _Alternative definition_: If _TaskType_ is:   - SqlCmdTask: Database provider assembly qualified name |
| Identifier   optional | __Type__    String   __Description__   Unique identifier of the task. |

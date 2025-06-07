# Policy

A policy is a next generation access control (NGAC) which works by assigning permissions to users based on their roles within an organization, and other dimensions and attributes. A policy is a sub-group of the role model, containing roles and rules, that allows an administrator to manage the access specific to their applications.

## Examples

Code attributes enclosed with <> need to be replaced with a custom value before entering the script in the command line.

```
<Policy Identifier="Default" DisplayName_L1="Default Policy" IsProvisioningEnabled="true" />
```

All ```ResourceType```, ```SingleRole```, ```CompositeRole``` and ```Category``` must belong to a Policy. This is done by specifying the ```Policy``` attribute. See the [Resource Type](/docs/product_docs/usercube/usercube/integration-guide/toolkit/xml-configuration/provisioning/resourcetype/index.md), [
Single Role
](/docs/product_docs/usercube/usercube/integration-guide/toolkit/xml-configuration/provisioning/singlerole/index.md), [
Composite Role
](/docs/product_docs/usercube/usercube/integration-guide/toolkit/xml-configuration/provisioning/compositerole/index.md) and [
Category
](/docs/product_docs/usercube/usercube/integration-guide/toolkit/xml-configuration/provisioning/category/index.md) topics for additional information.

```
<Category Policy="Default" Identifier="AD" DisplayName_L1="Active Directory" />
```

## Properties

| Property | Type | Details |
| --- | --- | --- |
| CommentActivationOnApproveInReview   default value: Optional | CommentActivation | Indicates if a comment is enabled when reviewing a role request associated with the policy, and deciding to approve it.  0 - Disabled.   1 - Optional.   2 - Required. |
| CommentActivationOnDeclineInReview   default value: Required | CommentActivation | Indicates if a comment is enabled when reviewing a role request associated with the policy, and deciding to refuse it.  0 - Disabled.   1 - Optional.   2 - Required. |
| CommentActivationOnDeleteGapInReconciliation   default value: Optional | CommentActivation | Indicates if a comment is enabled when reviewing a non-conforming role assignment associated with the policy, and deciding to delete it.  0 - Disabled.   1 - Optional.   2 - Required. |
| CommentActivationOnKeepGapInReconciliation   default value: Required | CommentActivation | Indicates if a comment is enabled when reviewing a non-conforming role assignment associated with the policy, and deciding to keep it.  0 - Disabled.   1 - Optional.   2 - Required. |
| D0   optional | Int64 | Value of the dimension 0 (up to 127) that filters the access to the policy and its roles. |
| DisplayName\_L1   required | String | Display name of the policy in language 1 (up to 16). |
| GracePeriod   default value: 0 | Int32 | Duration (in minutes) for which a lost automatic entitlement associated with this policy is prolonged.  The grace period is only applied if the loss of the entitlement is due to a change in the rules (rule deletion or criteria changes).  A review will be required to validate or decline the entitlement prolongation. Inferred entitlements won't be lost unless the end of the grace period is reached or the prolongation is declined.  This value can be overwritten for each composite role and single role. |
| HasImplicitApproval   default value: false | Boolean | True to skip the approval circuit when the requester has the appropriate review permissions.  This value can be overwritten for each policy object (composite role, single role, resource type). |
| Identifier   required | String | Unique identifier of the policy. |
| IsExternal   default value: false | Boolean | True to indicate that the policy's roles are outside Identity Manager's scope. The roles are managed by an external source, and Identity Manager cannot add, update nor delete any role. |
| IsProvisioningEnabled   default value: false | Boolean | True to enable the provisioning policy. |
| IsSimulationEnabled   default value: false | Boolean | True to enable the provisioning policy simulation. |
| ManualAssignmentEndDateLockedToContextMode  default value: ExplicitNotContextBoundByDefault | ManualAssignmentEndDateLockedToContextMode | The values are:  0 - ExplicitNotContextBoundByDefault — By default, the assignment's end date will not be context bound in order to encourage the manual entry of an end date  1 - ExplicitContextBoundByDefault — By default, the assignment's end date will be context bound and therefore locked, but a manual date can be entered.  2 - Never — The assignment's end date will never be locked and needs to be specified manually  3 - Always — The assignment's end date is always locked according to the applicable context rule. |
| MaxDuration   default value: 0 | Int32 | Duration (in minutes) after which the assignments induced by the policy will be automatically revoked, if no earlier end date is specified. It impacts only the assignments which are performed after the maximum duration is set. Pre-existing assignments are not impacted. |
| ProlongationWithoutApproval   default value: false | Boolean | True to allow the policy's roles to be extended without any validation. |

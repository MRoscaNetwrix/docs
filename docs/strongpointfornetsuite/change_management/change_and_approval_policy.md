# Change and Approval Policy

The Advanced Change Management system uses a set of policy records called Change and Approval Policies.
These Change and Approval Policies define:

- Level of change management required for a given change, for example, modifying a script vs. a search.
- Level of approval required
- Approvers

The [Setting Up Policies](setting_up_policies.md) topic has details on setting up the Change / Approval Policies.

When Process Issues or Change Requests are created, the impacted customizations and processes are analyzed. The change policy that applies is identified based on the IT risk from the Customization Record and the process risk from the Process Records.

The Change and Approval Policy also determines the change level required for any detected changes to be compliant. This ensures that even changes that do not go through the planned change management process are analyzed against the policy for compliance.

For example, a company may have multiple policies. For example:

- __Default Policy__ applies to any customization or process without a specific policy. Requires scripted changes go through a relatively high level of review compared to non-scripted changes.
- __Financial Processes Policy__ applies to the core financial processes. Under this policy, any changes to the financial processes could require full development and testing and approval of the CFO.
- __Critical Operational Processes Policy__ applies to vital operational processes or customizations such as those comprising a critical integration. This policy might require approval by the CFO as well as the expert owners of the specific objects concerned.
- __Controls Policy__ applies to key reports and controls listed on the policy that need specific approval to modify and ensures there are no changes without a proper audit review.

Once in place, the policies remind users of the level of change management required as well as monitors the changes that do occur and raises alerts to IT if there are any change violations.

You can create a custom change request form for a Policy Approval. Refer to [Using Custom Change Request Forms](use_custom_cr_forms.md) for information on implementing your custom form.

## Non-Material Changes

Non-material changes are changes detected in objects that are not performed by a human and do not have functional impact. You can review these changes on the [Non-Material Changes report](change_management_reports.md).

Here is the criteria for non-material changes:

- System generated changes.
- XML changes that do not directly affect the object definition. For example, Script Deployment where it shows all related scripts that are deployed to the same record.
- Customization record changes that sets references to other customizations but there is no change in actual record definition. For example, the list customization is added as dependency to the field customization.
- When the __Internal Id__ changes for a __Script Deployment__ that belongs to a __Bundle with Update Deployment__ settings which deletes the original deployment and creates a new deployment record on bundle updates. This __Internal Id__ change is flagged as non-material because a deletion log is created.
- Initial setting of __Bundle Id__ to a customization record because some customizations (for example, __custom record field__) do not have the bundle information within their metadata.
- __Scripting/Workflow to Field Update__ when a script/workflow is added as reference in the field customization record. The valid change is documented on the __Script__ or __Workflow__ instead of the field.
- Change log is flagged as duplicate after confirming the actual change date and changed by for that customization already exists. Duplicates can occur as changes are captured from different sources such as object metadata, audit trail, history, and system notes
- Create logs of customization where duplicated customizations (same type, name, scriptid, and name).
- __Script File Date__ has changed because of bundle update but there is no change found in the file contents and hash.

## Managed and Non-Managed Bundles

Platform Governance for NetSuite can process changes that are bundled together as a group. There are different processes for __Managed Bundles__ (changes pushed by a third party) and __Non-Managed Bundles__ (your own packaged changes). System generated __Manage Bundle__ change requests are now created with an approved status to be consistent with the change logs (compliant) that are attached to it.

| Change Type | Change Request | Action When Change Detected | Status | Report |
| --- | --- | --- | --- | --- |
| Non-managed Bundle push or manual change | An open and approved change request with the __Bundle ID__ in the __Affected Bundle ID__ field. __Type__ must be __Bundle Update__ | Attach the change logs to the change request. | Compliant | Compliant Changes |
| Non-managed Bundle push or manual change | No open and approved change request exists and the object requires a change request. __Type__ must be __Bundle Update__ | Marks the change as __Non-compliant__. | Non-compliant | Open Non-Compliant Changes |
| Managed Bundle change pushed to Production | An open and approved change request with the __Bundle ID__ in the __Affected Bundle ID__ field and change request __Type__ is __Managed Bundle Update__ | Attach the change logs to the change request. | Compliant | Managed Bundle Changes |
| Managed Bundle change pushed to Production | No open and approved change request exists and the object requires a change request. | Creates a change request of __Type__ __Managed Bundle Update__, attaches the changes to the change request and marks the change logs as __Compliant__. | Compliant | Managed Bundle Changes |

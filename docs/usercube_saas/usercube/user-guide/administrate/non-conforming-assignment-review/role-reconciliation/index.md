# Reconcile a Role

How to review non-conforming permissions, i.e. approve or decline the role suggestions made by Identity Manager after every synchronization. The aim is to handle the differences between the navigation values from the managed systems and those computed by Identity Manager according to the role catalog.

## Overview

Non-conforming roles are considered as non-conforming assignments because no rule from Identity Manager's model can justify their actual assignment to an identity.

### Role reconciliation with property reconciliation

For some managed systems, roles are tightly linked to navigation properties.

> For example, the AD hosts groups dedicated to various applications, and a role is assigned through group membership. An entitlement can be assigned to an identity by adding said identity's DN to the ```member``` property of the appropriate group. Identity Manager translates it by editing the identity's ```memberOf``` property with the new group.

In this case, when a role is assigned in the managed system without an existing rule that justifies the role, then new items appear on the __Role Reconciliation__and the __Resource Reconciliation__ screens.

> In the case of the AD example, consider that we want to assign a specific role in SAP. Then, we find the corresponding group in the AD and add the identity's DN to its ```member``` property.
>   
> The result is a new item on the __Role Reconciliation__ screen for said SAP role, plus an item on the __Resource Reconciliation__ screen for the new ```memberOf``` property for said identity.
>   
> If the identity didn't have an AD account yet, then it is automatically created, and the item on the __Resource Reconciliation__ screen displays also a modification of the ```accountExpires``` property.

As roles and navigation properties are technically bonded together, their reviews are linked too:

- If the role is reviewed (approved/declined), then the corresponding property is automatically reconciled accordingly.
- If the property is reviewed (approved/declined), then the corresponding role is automatically reviewed too, its [Entitlement Assignment](../../../../integration-guide/role-assignment/assignments-of-entitlements/index.md) workflow state transitioned to ```Manual``` (if approved) or ```Cancellation``` (if declined, then a deprovisioning order is sent).

> So let's say we add ```Cedric Blanc``` to the list of members of the SAP groups ```SG_APP_SAP_1``` and ```SG_APP_SAP_211```. Then, after the next synchronization, Identity Manager displays one item for each role on the __Role Reconciliation__ screen, and one item for all changes in the AD account on the __Resource Reconciliation__ screen:
>
> ![Example - Role Reconciliation](../../../../../../../static/img/product_docs/usercube/usercube/user-guide/administrate/non-conforming-assignment-review/property-reconciliation/reviewrole_examplerole_v602.webp)
>
> ![Example - Resource Reconciliation](../../../../../../../static/img/product_docs/usercube/usercube/user-guide/administrate/non-conforming-assignment-review/property-reconciliation/reviewrole_exampleresource_v602.webp)
>
> ![Example - Resource Reconciliation - Properties](../../../../../../../static/img/product_docs/usercube/usercube/user-guide/administrate/non-conforming-assignment-review/property-reconciliation/reviewrole_exampleresourceprop_v602.webp)

## Participants and Artifacts

This operation should be performed in cooperation with managers who know their team's expected entitlements.

| Input | Output |
| --- | --- |
| [Provision](../../provisioning/index.md) (required) | Complying roles |

## Review a Non-conforming Permission

Review a non-conforming permission by proceeding as follows:

1. Ensure that the [
   Compute Role Model Task
   ](../../../../integration-guide/toolkit/xml-configuration/jobs/tasks/server/computerolemodeltask/index.md) was launched recently, through the complete job on the __Job Execution__ page

   ![Home Page - Job Execution](../../../../../../../static/img/product_docs/usercube/usercube/user-guide/set-up/synchronization/home_jobexecution_v602.webp)

   Or through the connector's overview page, __Jobs__ > __Compute Role Model__.

   ![Resource Type Jobs](../../../../../../../static/img/product_docs/usercube/usercube/user-guide/set-up/categorization/classification/synchro_resourcetype_v602.webp)
2. On the home page, click on the entity type that you want to manage in the __Role Reconciliation__ section, to get to the non-conforming permissions page.

   ![Home Page - Role Reconciliation](../../../../../../../static/img/product_docs/usercube/usercube/user-guide/administrate/non-conforming-assignment-review/role-reconciliation/home_rolereconciliation_v523.webp)

   ![Role Reconciliation Page](../../../../../../../static/img/product_docs/usercube/usercube/user-guide/administrate/non-conforming-assignment-review/role-reconciliation/reviewrole_rolereconciliation_v603.webp)

   Each non-conforming permission can be commented by clicking on the corresponding icon.

   ![Comment Icon](../../../../../../../static/img/product_docs/usercube/usercube/user-guide/administrate/access-certification/certification-campaign-execution/certifcampaign_iconcomment_v522.svg)
3. Choose one of the two possibilities to verify the permission:

   Contrary to resources, reviewed roles are then displayed on the __Role Review__ page accessible from the home page, and can be reviewed again.

   - Either click on the approval icon to keep the non-conforming permission.

   ![Approval Icon](../../../../../../../static/img/product_docs/usercube/usercube/user-guide/administrate/non-conforming-assignment-review/role-reconciliation/orphan_iconapprove_v602.svg)

   - Or click on the decline icon to delete the non-conforming permission.

   ![Decline Icon](../../../../../../../static/img/product_docs/usercube/usercube/user-guide/administrate/non-conforming-assignment-review/role-reconciliation/orphan_icondecline_v522.svg)
4. Trigger provisioning by launching, on the appropriate connector's overview page, __Jobs__ > __Generate Provisioning Orders__, then, after this first task is done, __Jobs__ > __Fulfill__. See the [Provision](../../provisioning/index.md) topic for additional information.

   ![Resource Type Jobs](../../../../../../../static/img/product_docs/usercube/usercube/user-guide/set-up/categorization/classification/synchro_resourcetype_v602.webp)

### Use bulk provisioning

Several roles can be reconciled simultaneously by clicking on __Bulk Reconcile Roles__.

![Bulk Reconcile Roles](../../../../../../../static/img/product_docs/usercube/usercube/user-guide/administrate/non-conforming-assignment-review/role-reconciliation/reviewrole_rolereconciliationbulk_v603.webp)

## Verify Role Reconciliation

In order to verify the process, check that the changes you ordered appear on the corresponding user's __View Permissions__ tab.

![View Permissions Tab](../../../../../../../static/img/product_docs/usercube/usercube/user-guide/set-up/provisioning-rule-creation/resource-creation/viewpermissions_v602.webp)

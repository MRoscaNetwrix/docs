---
sidebar_position: 1239
title: Reconcile a Property
---

# Reconcile a Property

How to review unreconciled properties. The aim is to handle the differences between the property values from the managed systems and those computed by Identity Manager according to [Create a Provisioning Rule](../../../set-up/provisioning-rule-creation/index "Create a Provisioning Rule").

## Overview

Unreconciled properties are considered as non-conforming assignments because Identity Manager's role model has computed property values that are different from the values in the managed systems.

### Property reconciliation with role reconciliation

For some managed systems, roles are tightly linked to navigation properties.

> For example, the AD hosts groups for various applications, and a role is assigned through a group membership. An entitlement can be assigned to an identity by adding said identity's DN to the `member` property of the appropriate group. Identity Manager translates it by editing the identity's `memberOf` property with the new group.

In this case, when a role is assigned in the managed system without an existing rule that justifies the role, then new items appear on the **Role Reconciliation**and the **Resource Reconciliation** screens.

> In the case of the AD example, consider that we want to assign a specific role in SAP. Then, we find the corresponding group in the AD and add the identity's DN to its `member` property.
>   
>   
> The result is a new item on the **Role Reconciliation** screen for said SAP role, plus an item on the **Resource Reconciliation** screen for the new `memberOf` property for said identity.
>   
>   
> If the identity didn't have an AD account yet, then it is automatically created, and the item on the **Resource Reconciliation** screen displays also a modification of the `accountExpires` property.

As roles and navigation properties are technically bonded together, their reviews are linked too:

* If the role is reviewed (approved/declined), then the corresponding property is automatically reconciled accordingly.
* If the property is reviewed (approved/declined), then the corresponding role is automatically reviewed too, its workflow state transitioned to `Manual` (if approved) or `Cancellation` (if declined, then a deprovisioning order is sent).

> So let's say we add `Cedric Blanc` to the list of members of the SAP groups `SG_APP_SAP_1` and `SG_APP_SAP_211`. Then, after the next synchronization, Identity Manager displays one item for each role on the **Role Reconciliation** screen, and one item for all changes in the AD account on the **Resource Reconciliation** screen:
>
> ![Example - Role Reconciliation](../../../../../../../../static/images/Usercube_6.2/Content/Resources/Images/ReviewRole_exampleRole_V602.png)
>
> ![Example - Resource Reconciliation](../../../../../../../../static/images/Usercube_6.2/Content/Resources/Images/ReviewRole_exampleResource_V602.png)
>
> ![Example - Resource Reconciliation - Properties](../../../../../../../../static/images/Usercube_6.2/Content/Resources/Images/ReviewRole_exampleResourceProp_V602.png)

## Participants and Artifacts

This operation should be performed in cooperation with application owners in charge of applications' entitlements.

| Input | Output |
| --- | --- |
| [Provision](../../provisioning/index "Provision") (required) | Complying properties |

## Review an Unreconciled Property

Review an unreconciled property by proceeding as follows:

1. Ensure that the task for the computation of the role model was launched recently, through the complete job on the **Job Execution** page�

   ![Home Page - Job Execution](../../../../../../../../static/images/Usercube_6.2/Content/Resources/Images/Home_jobExecution_V602.png)

   � Or through the connector's overview page, **Jobs** > **Compute Role Model**.

   ![Resource Type Jobs](../../../../../../../../static/images/Usercube_6.2/Content/Resources/Images/Synchro_resourceType_V602.png)
2. Get to the **Resource Reconciliation** page, accessible from the corresponding section on the home page.

   ![Home Page - Resource Reconciliation](../../../../../../../../static/images/Usercube_6.2/Content/Resources/Images/Home_resourceReconciliation_V523.png)
3. Select `Unreconciled properties` as a `Workflow State`.

   ![Unreconciled Property](../../../../../../../../static/images/Usercube_6.2/Content/Resources/Images/ReviewProp_unreconciled_V522.png)
4. Choose the default resource view or the property view with the top right toggle. See the [Reconcile a Property](# "Reconcile a Property") topic for additional information.
5. Select a property to review.

   > In the following example, the user `Nicolas Faure` is the owner of a given resource, here a nominative SAB account associated with his email address. In the **Resource Properties to be Verified** frame, there is one unreconciled property that happens to be `Group`.
   >
   > ![Unreconciled Property Example](../../../../../../../../static/images/Usercube_6.2/Content/Resources/Images/ReviewProp_example_V602.png)

   * `Name`: unreconciled property name.
   * `Proposed Value`: value proposed by Identity Manager.
   * `Current Value`: value currently in the managed system.
   * `Provisioning State`: provisioning state.
   * `Start Date`: date for the beginning of the property value existence.
   * `End Date`: date for the end of the property value existence.

   The **Other Resource Properties** frame shows the complying properties associated with the resource.
6. Choose one of the three possibilities to verify the property:

   :::warning
Decisions must be made with caution as they cannot be undone.
   :::

   * Either click on the approval icon to update the property with the proposed value. It discards the whole property history.

     ![Addition Icon](../../../../../../../../static/images/Usercube_6.2/Content/Resources/Images/ProvManual_iconApprove_V602.svg)

     ![Edition Icon](../../../../../../../../static/images/Usercube_6.2/Content/Resources/Images/ProvManual_iconEdit_V602.svg)

     ![Deletion Icon](../../../../../../../../static/images/Usercube_6.2/Content/Resources/Images/ReviewRole_iconDelete_V602.svg)

     :::note
Automatic changes are essential for frequently-changing attributes. However, saving history information can sometimes be important for some attributes such as logins and emails.
     :::
   * Or click on the decline icon to not update the property and keep the resource value. In the future, this property will no longer be changed automatically.

     ![Decline Icon](../../../../../../../../static/images/Usercube_6.2/Content/Resources/Images/ProvManual_iconDecline_V522.svg)

     :::note
Retaining manual control of changes for sensitive data (i.e. SAMAccountName) can be of interest. Identity Manager won't be able to change this data and the service account manager will avoid authentication errors. It can be interesting to keep manual some sensitive data changes like SAMAccountName for example, so that Identity Manager does not change it and the service account manager does not risk problems in authentication.
     :::
   * Or click on the postponement icon to delay the decision. An unreconciled property is ignored by Identity Manager, and therefore cannot be modified.

     ![Postponement Icon](../../../../../../../../static/images/Usercube_6.2/Content/Resources/Images/ProvManual_iconPostpone_V522.svg)
7. Click on **Confirm Property Values**.
8. Trigger provisioning by launching, on the appropriate connector's overview page, **Jobs** > **Generate Provisioning Orders**, then, after this first task is done, **Jobs** > **Fulfill**.

   ![Resource Type Jobs](../../../../../../../../static/images/Usercube_6.2/Content/Resources/Images/Synchro_resourceType_V602.png)

### Use property view

By default, non-conforming assignments are listed by resource. It is possible to click on a resource and then access the list of all unreconciled properties for said resource.

![Resource View](../../../../../../../../static/images/Usercube_6.2/Content/Resources/Images/Orphan_resourceView_V523.png)

It can be helpful to have the non-conforming assignments regrouped by property, as some of the changes can be similar, so very likely to be validated by the same user. This is why a property view can be enabled by clicking on the `Property View` toggle at the top right corner.

Once enabled, select a resource type to display all unreconciled properties linked to said resource type. In addition, select a property to display only the unreconciled properties linked to said resource type and property.

![Property View](../../../../../../../../static/images/Usercube_6.2/Content/Resources/Images/Orphan_propertyView_V603.png)

The review process is the same with both views. However with property view, reviewers don't click on a given line, but choose a decision directly on the left of the property line.

In addition, using property view enables bulk reconciliation to approve the proposed values or keep the current values for several resources simultaneously.

![Bulk Reconcile](../../../../../../../../static/images/Usercube_6.2/Content/Resources/Images/Orphan_bulkReconcile_V603.png)

## Verify Property Reconciliation

In order to verify the process, check that the changes you ordered appear on the corresponding user's page in the directory.
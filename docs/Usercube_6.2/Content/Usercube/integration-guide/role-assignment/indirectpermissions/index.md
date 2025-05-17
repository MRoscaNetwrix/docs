---
sidebar_position: 1021
title: Indirect Permissions
---

# Indirect Permissions

Identity Manager can compute, for a given identity, permissions that are obtained implicitly or indirectly through assignments. The [Compute Role Model Task](../../toolkit/xml-configuration/jobs/tasks/server/computerolemodeltask/index "ComputeRoleModelTask") is responsible for this functionality.

## Overview

Assigning a role to a user can give them new permissions in a managed system by giving access to a new role or a new group, for example. This assignment is direct as it is entirely explicit.
However, the user might also receive some **additional permissions that are inherited through the new permission** and that are not explicit. For instance in some systems, users can get permissions by being a member of a group but groups can also be members of other groups, and therefore allow for transitive permission acquisitions. These permissions are called indirect. This notion can also be extended when permissions in a managed system also give other permissions in an external system.

:::note
Indirect Permissions are automatically computed by the
Compute Role Model Task
along with standard explicit or direct permissions during a full update. Indirect permissions will not be computed when processing a single user (for instance through "Repair Data (helpdesk)") or during simulations.
:::

## Configuration

The computation of Indirect Permissions is based on the configured [Indirect Resource Rule](../../toolkit/xml-configuration/provisioning/indirectresourcerule/index "IndirectResourceRule"). These rules tell Identity Manager how to navigate the managed system and how to recover permissions that a user inherits implicitly. An Indirect Resource Rule is composed of the following properties:

* `ResourceType`—The [Resource Type](../../toolkit/xml-configuration/provisioning/resourcetype/index "Resource Type") to which the rule will be applied.
* `Property` — The [Entity Type](../../toolkit/xml-configuration/metadata/entitytype/index "EntityType") which corresponds to the user permission in the *target* system.
* `Correspondence` (optional)— The [Entity Type](../../toolkit/xml-configuration/metadata/entitytype/index "EntityType") that is used to recover the correspondence of a resource from the *target* system in the *external* system.
* `CorrespondenceMembershipProperty` (optional) — The [Entity Type](../../toolkit/xml-configuration/metadata/entitytype/index "EntityType") which corresponds to the user permission in an *external* system.
* `Entitlement` (optional) — The [Entity Type](../../toolkit/xml-configuration/metadata/entitytype/index "EntityType") that can be configured if the permission in the *external* system needs to be recovered from the discovered resources. For instance one can use this property to recover the entitlements of Sharepoint groups (while `CorrespondenceMembershipProperty` will be used to recover the group membership graph).

:::note
If either Correspondence or CorrespondenceMembershipProperty is specified, then the other property must be specified as well.
:::

:::note
If Entitlement is specified, then both Correspondence and CorrespondenceMembershipProperty also need to be specified.
:::

* `TargetEntityTypeProperty` — The [Entity Type](../../toolkit/xml-configuration/metadata/entitytype/index "EntityType") which identifies each rule given a resource type.
* `TargetEntityTypeReflexiveProperty` — The [Entity Type](../../toolkit/xml-configuration/metadata/entitytype/index "EntityType") which corresponds to the user permission in the *target* system.
* `IndirectResourceBinding`— The [Bindings](../../toolkit/bindings/index "Bindings") that is used to recover an assignment from a permission in either system (target or external). It is also used to define the correspondence between resources in both systems.
* `IndirectResourceReflexiveProperty` (optional): The [Entity Type](../../toolkit/xml-configuration/metadata/entitytype/index "EntityType") which corresponds to the user permission in an *external* system.

:::note
Correspondences between resources are necessarily one-sided: the Indirect Permissions computation is started in the managed system and if a correspondence is found, the computation will be continued in the external system. Correspondences won't be checked in the external system.
:::

:::note
An example of an Indirect Resource Rule configuration is available in How-To:
Configure Indirect Permissions
in an Active Directory.
:::

## What Can Be an Indirect Permission?

The [Compute Role Model Task](../../toolkit/xml-configuration/jobs/tasks/server/computerolemodeltask/index "ComputeRoleModelTask") will create indirect Assigned Resource Navigations for the permissions that it finds, but if and only if these permissions are associated with a [Resource Type](../../toolkit/xml-configuration/provisioning/resourcetype/index "Resource Type").

If a [Single Role](../../toolkit/xml-configuration/provisioning/singlerole/index "SingleRole") is associated with one of these Resource Navigation Rules, then an indirect Single Role will also be recovered.

Finally, if at least one indirect Single Role is used to recover a [Composite Role](../../toolkit/xml-configuration/provisioning/compositerole/index "CompositeRole"), then the Composite Role will also be indirect.

## What Can Be Done with Indirect Permissions?

Currently, Indirect Permissions are only displayed and found in the users' `View Permissions` tab in the `Advanced View`: Indirect Permissions (except Composite Roles) are hidden in the `Simplified View`.

Although Indirect Permissions are marked as `Non-conforming`, they can be neither approved nor deleted. They also won't appear in Access certification campaigns.

:::note
Indirect Permissions are always indicated by the following icon:
:::

## Disabling the Indirect Permission Computation

In case of emergency, one can disable the computation of indirect permissions by adding the `"DisableIndirectPermissions": true` field to the root of the `appsettings`. While the computation is disabled, indirect permissions will be frozen in time: any existing one will not be deleted and any potential new one will not be added.
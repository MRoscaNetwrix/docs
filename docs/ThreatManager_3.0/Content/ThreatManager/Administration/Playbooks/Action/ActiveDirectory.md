---
sidebar_position: 2496
title: Active Directory Target Actions
---

# Active Directory Target Actions

The following actions target Active Directory.

## Active Directory Group Membership

The Active Directory Group Membership action provides configuration options to add or remove Active Directory group membership.

![](../../../../../../../static/images/ThreatManager_3.0/Content/Resources/Images/ThreatManager/Admin/Playbooks/Action/ADGroupMembership.png)

* Users – Select the users for whom to alter group membership. If not specified, the user who triggered the threat will be used.
* Action – Select the action to take on the user's group membership.
  * Add
  * Remove
* Group – Specify the identity of the group to manage. If not specified, the group affected by the threat will be used.
* Credential – Select a credential profile that contains valid Active Directory credentials. Credential profiles are configured on the [Integrations Interface](../../Configuration/Integrations/Overview "Integrations Interface"). If not specified, the action will be run as the credentials of the Action Service.

## Change Password at Next Logon

The Change Password at Next Logon action forces the user to change their password the next time the user logs on.

![](../../../../../../../static/images/ThreatManager_3.0/Content/Resources/Images/ThreatManager/Admin/Playbooks/Action/ChangePassword.png)

* Users – Select the users for whom to reset passwords at next logon. If not specified, the user who triggered the threat will be used.
* Credential – Select a credential profile that contains valid Active Directory credentials. Credential profiles are configured on the [Integrations Interface](../../Configuration/Integrations/Overview "Integrations Interface"). If not specified, the action will be run as the credentials of the Action Service.

## Disable Active Directory Account

The Disable Active Directory Account action disables the specified account.

![](../../../../../../../static/images/ThreatManager_3.0/Content/Resources/Images/ThreatManager/Admin/Playbooks/Action/DisableADAccount.png)

* Active Directory Credentials – Select a credential profile that contains valid Active Directory credentials. Credential profiles are configured on the [Integrations Interface](../../Configuration/Integrations/Overview "Integrations Interface"). If not specified, the action will be run as the credentials of the Action Service.
* Users – Select users to disable. If not specified, the user who triggered the threat will be used.

## Disable Active Directory Computer

The Disable Active Directory Computer action disables the specified computer object in Active Directory.

![](../../../../../../../static/images/ThreatManager_3.0/Content/Resources/Images/ThreatManager/Admin/Playbooks/Action/DisableADComputer.png)

* Disable Domain Controllers – When selected, allows domain controllers to be disabled.
* Active Directory Credentials – Select a credential profile that contains valid Active Directory credentials. Credential profiles are configured on the [Integrations Interface](../../Configuration/Integrations/Overview "Integrations Interface"). If not specified, the action will be run as the credentials of the Action Service.
* Computer – Select the computer to disable. If not selected, the host computer will be used.

## Reset Password

The Reset Password action resets the password of the specified account.

![](../../../../../../../static/images/ThreatManager_3.0/Content/Resources/Images/ThreatManager/Admin/Playbooks/Action/ResetPassword.png)

* Users – Select the users for whom to reset passwords. If not specified, the user who triggered the threat will be used.
* Credential – Select a credential profile that contains valid Active Directory credentials. Credential profiles are configured on the [Integrations Interface](../../Configuration/Integrations/Overview "Integrations Interface") . If not specified, the action will be run as the credentials of the Action Service.

## Revert Permission Change

The Revert Permission Change action reverts a permission change on an Active Directory Object.

![](../../../../../../../static/images/ThreatManager_3.0/Content/Resources/Images/ThreatManager/Admin/Playbooks/Action/RevertPermissionChange.png)

* Credential – Select a credential profile that contains valid Active Directory credentials. Credential profiles are configured on the Integrations Interface. If not specified, the action will be run as the credentials of the Action Service.

See the [Integrations Interface](../../Configuration/Integrations/Overview "Integrations Interface") topic for additional information.
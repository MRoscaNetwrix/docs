---
sidebar_position: 6655
title: Enterprise Password Enforcer
---

# Enterprise Password Enforcer

Attackers often use dictionaries of previously breached passwords or knowledge of well-known passwords to compromise accounts. To mitigate this risk and the likelihood of generic or known passwords used in organizations, Threat Prevention Enterprise Password Enforcer (EPE) proactively prevents their usage when passwords are set (even when they meet complexity requirements).

An optional module, EPE User Feedback, is packaged with the zip file for Threat Prevention installation. It provides feedback to end users on the Windows login screen for why their pending password change was rejected. It lists the failed complexity requirements set up in the Password Rules policy (see the [Password Rules Filter](../Admin/Policies/EventType/PasswordEnforcement#Password "Password Rules Filter") of the Password Enforcement event type). The user can use this information to create a new password that passes the complexity requirements of the organization.

You can choose a method to deploy the EPE User Feedback module; however, logon scripts are a suggested way to deploy this zero configuration msi. Prior to deploying the EPE User Feedback module, you must select the Enable EPE User Feedback Module checkbox in the [EPE Settings Window](../Admin/Configuration/EPESettings "EPE Settings Window"). See the [EPE User Feedback Module](../Install/EPEUserFeedback "EPE User Feedback Module") topic for additional information.

**NOTE:** The Password Enforcement module is available under all licenses for monitoring weak passwords. However, you need the Enterprise Password Enforcer solution license to block weak passwords.

The following event type is available for Enterprise Password Enforcer:

* [Password Enforcement Event Type](../Admin/Policies/EventType/PasswordEnforcement "Password Enforcement Event Type")

## Enforce Password Reset with Microsoft Entra ID Password Writeback

You can use Threat Preventionto enforce password policies for passwords reset from Microsoft Entra ID and O365 by enabling password writeback in Microsoft Entra ID. See the [How does self-service password reset writeback work in Microsoft Entra ID?](https://docs.microsoft.com/en-us/azure/active-directory/authentication/concept-sspr-writeback "How does self-service password reset writeback work in Microsoft Entra ID?") Microsoft knowledge base article for additional information on password writeback in Microsoft Entra ID. Password writeback sends all new passwords from Microsoft Entra ID to an available, on-premises domain controller to check with Threat Prevention. This happens while the user is resetting their password. See the [Tutorial: Enable Microsoft Entra self-service password reset writeback to an on-premises environment](https://docs.microsoft.com/en-us/azure/active-directory/authentication/tutorial-enable-sspr-writeback "Tutorial: Enable Microsoft Entra self-service password reset writeback to an on-premises environment") and [How it works: Microsoft Entra self-service password reset](https://docs.microsoft.com/en-us/azure/active-directory/authentication/concept-sspr-howitworks#on-premises-active-directory-password-filters "How it works: Microsoft Entra self-service password reset") Microsoft knowledge base articles for additional information on password writeback for Microsoft Entra ID.
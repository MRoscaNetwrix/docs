---
sidebar_position: 6328
title: Offline Add-on
---

# Offline Add-on

## What is the Offline Add-on?

The Offline Add-on enables you to work without an active connection to the Netwrix Password Secure server. If the corresponding setting has been configured ([Setup and sync](Setup/Setup and sync "Setup and sync")), the local copy of the server database will be automatically synchronized according to freely definable cycles. This ensures that you can always use a (relatively) up-to-date version of the database offline.

Facts

* “Microsoft SqlServer Compact 4.0.8876.1” is used for creating offline databases
* The database is encrypted using AES-128 or SHA-256. A so-called “platform default” is used for this purpose
* In addition, RSA encryption processes are used
* More on this subject…::https://technet.microsoft.com/en-us/library/gg592949(v=sql.110).aspx

#### Installation

The Offline Add-on is automatically installed together with the main client. No database profiles need to be created – this task is performed by the client during the initial synchronization, together with the creation of the offline database.

#### Operation

Operation of the Offline Add-on is generally based on the [Operation and setup](../Server Manager/Operation and setup/Operation and setup Admin Client "Operation and setup"). Since the Offline Add-on only has a limited range of functions, the following must be taken into account with regards to its operation:

* There is no dashboard
* Only the password module is available
* The filter is not available. Records are found using the [Search](../Advanced view/Operation and Setup/Search/Search "Search")
* The automatic login data entry can be performed via the [Autofill Add-on](../Autofill Add-on/Autofill Add-on "SSO Agent"), independently of the Offline Add-on

![Offline Client](../../../../../../static/images/PasswordSecure_9.2/Content/Resources/Images/Installation_with_parameters_264-en.png "Offline Client")

#### What data is synchronised?

[Seals](../Advanced view/PermissionConcept/Predefining rights/Protective mechanisms/Seals/Seals "Seals") enhance the security concept in Netwrix Password Secure to include a double-check principle that can be defined in fine detail. This means that releases for protected information are linked to the positive authentication of one or more users. Naturally, it is not possible to issue these releases when the server is not connected. For this reason, sealed records are not synchronized and thus do not form part of offline databases.

Otherwise, all records for which the user has the **export right** are synchronised.

Records with **password masking** are adopted into the offline database and can be used as normal.
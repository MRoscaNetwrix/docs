---
title: Autofill Add-on Configuration
sidebar_label: Autofill Add-on
description: Configure automatic login data entry for applications with hidden password protection and authorization mechanisms for secure credential management.
---

# Autofill Add-on

## What is the Autofill Add-on?

The Autofill Add-on is responsible for the automatic entry of login data in applications. This
enables logins without knowledge of the password, which can be a particularly valuable tool in
combination with
[Password masking](/docs/passwordsecure/9.1/configuration/permissions/protective-mechanisms/password-masking.md).
The
[Authorization and protection mechanisms](/docs/passwordsecure/9.1/web-application/authorization-protection.md)
is used to define which users should receive access.

However, the password remains hidden because it is entered by Netwrix Password Secure.

#### Requirements

The Autofill Add-on is installed together with the Netwrix Password Secure client and can then be
used by users (assuming they have sufficient permissions). A separate installation is thus not
necessary. A desktop link is created for both the client and also for the Autofill Add-on.

User rights

The right **Can create web applications** is required for creating new web applications\*

NOTE: The agent can control multiple databases at the same time

#### Functionality

The functionality of the Autofill Add-on is illustrated in the following diagram.

![Automatic entries diagram](/img/versioned_docs/passwordsecure_9.1/passwordsecure/configuration/autofill_add-on/installation_with_parameters_125-en.webp)

RDP and SSH
sessions(![1](/img/versioned_docs/passwordsecure_9.1/passwordsecure/configuration/autofill_add-on/1.webp)
) are not automatically started via the Autofill Add-on. Applications are created for this purpose
in the Netwrix Password Secure client. The creation and use of these connections is explained in
detail in the corresponding section.

Automatically starting all other types of connection is the task of the **Autofill Add-on**. The
following types of connections exist:

- Entering login data in Windows applications: Alongside the above-mentioned RDP and SSH sessions,
  other Windows applications can also be automated
  (![2](/img/versioned_docs/passwordsecure_9.1/passwordsecure/configuration/autofill_add-on/2.webp)).
  A major difference is that the two above-mentioned connections are set up and “embedded” in a
  separate tab. Other applications, such as e.g. VMware, are directly started as usual. In these
  cases, the Autofill Add-on takes over the communication between the application server and the
  Windows applications.

NOTE: For entering data on websites, the record must contain at least the following fields: User
name, password, URL.

#### Conclusion

As the Autofill Add-on is directly connected to the application server, login data can also be
entered without the main client. Exceptions are the RDP and SSH connections. These are forced to
remain part of the client. The Autofill Add-on thus acts as a lean alternative for the use of the
client with the two limitations mentioned. Naturally, all of the steps completed are still entered
in the logbook and are always traceable.

# Configuration

## Starting the Autofill Add-on

The Autofill Add-on can be directly started via the desktop link that is automatically created when
it is installed. The login data correspond to the normal user data for the client.

![Login SSO](/img/versioned_docs/passwordsecure_9.1/passwordsecure/configuration/autofill_add-on/configuration/installation_with_parameters_129-en.webp)

To log in, the desired database and the associated login data are firstly selected. The Autofill
makes all of the databases configured on the client available. It is also possible to create
profiles as usual so that the connection data for certain databases can be used efficiently in the
future.

NOTE: The agent accesses the same configuration file as the client. All changes to profiles will
thus also affect the client. New profiles can thus also be created via the Autofill.

#### Context menu functionality

After successfully logging in, the Autofill Add-on firstly runs in the background. Right click on
the icon in the system tray to open the context menu.

![icon options](/img/versioned_docs/passwordsecure_9.1/passwordsecure/configuration/autofill_add-on/configuration/installation_with_parameters_130-en.webp)

- **Disconnect**: Connect to database/disconnect from database. (All connections are shown for
  multiple databases)
- **Login** enables you to log into another database
- **Disable/Enable agent** allows you the option of temporarily disabling automatic login
- A diverse range of variables can be defined via the **Settings**
- **Reload all Data**

Settings

![settings sso agent](/img/versioned_docs/passwordsecure_9.1/passwordsecure/configuration/autofill_add-on/configuration/installation_with_parameters_131-en.webp)

- The desktop notifications display various information, such as when data is entered
- Start with Windows includes the Autofill Add-on in the autostart menu

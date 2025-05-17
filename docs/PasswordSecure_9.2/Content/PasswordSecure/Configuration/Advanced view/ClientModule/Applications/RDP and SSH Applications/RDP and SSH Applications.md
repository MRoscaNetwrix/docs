---
sidebar_position: 6429
title: RDP and SSH Applications
---

# RDP and SSH Applications

**RDP and SSH applications** can be used "embedded" inside Netwrix Password Secure. Starting one of those applications opens a new tab inside Netwrix Password Secure.

## Creating RDP and SSH Applications

A new RDP or SSH application can be created via the ribbon or the context menu. The corresponding form appears in which you define the variables for a connection.

![new rdp application](../../../../../../../../../static/images/PasswordSecure_9.2/Content/Resources/Images/rdp_and_ssh_applications_1-en.png "new rdp application")

These variables correspond exactly to those that can be configured (here using the RDP example) when creating an RDP connection via "mstsc". The window mode defines whether the connection should be started in a tab, in full screen mode or in a separate window.

## Working with RDP and SSH Applications

For example, if you have created an RDP application, you can start it directly from the ribbon. With the icon "Establish RDP connection" the connection to the desired session will be established.

![establish RDP](../../../../../../../../../static/images/PasswordSecure_9.2/Content/Resources/Images/applications_4-en.png "establish RDP")

Netwrix Password Secure now tries to log in to the target system with the available information. All missing information will be requested directly after the connection is established. It is therefore also possible to enter the IP address and/or password after starting the application.

![RDP connection](../../../../../../../../../static/images/PasswordSecure_9.2/Content/Resources/Images/rdp_and_ssh_applications_3-en.png "RDP connection")

## Login via SSH certificates

It is also possible to use SSH-certificates for authentication. For this purpose, the certificate is stored as a document in .ppk format. The document is then linked to the data record via the footer. The data record does not have to contain a password, but it must be linked to an SSH application.

NOTE: The file extension may first have to be enabled via the settings.

## Keyboard shortcuts

Netwrix Password Secure supports various [Keyboard shortcuts](../../../Operation and Setup/Dashboard and widgets/Keyboard shortcuts "Keyboard shortcuts  "). For example transferring user name and password to the corresponding application. However, it should be noted that this only works if the application is opened directly from Netwrix Password Secure
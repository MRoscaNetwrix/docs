---
sidebar_position: 6318
title: Installation with parameters
---

# Installation with parameters

## What is installation with parameters?

The installation of the Netwrix Password Secure client can also be optionally run on the command line. This method also requires the transfer of parameters. These can be combined with one another. In this case, the individual parameters are separated from one another by a blank space. The parameters listed in the following section enable you to adapt the type of client installation.

## Running on the command line with parameters

Run the installation via the command line: **MSI-FILE.msi [PARAMETER]**

**Parameter**

* **AUTOFILL\_ADDON\_AUTOSTART=“0”**: Deactivates launching the Autofill Add-on in Windows autostart
* **INSTALL\_AUTOFILL\_ADDON=“0**”: Deactivates the installation of the Autofill Add-on. In the list of the components to be installed in the setup, a check mark has not been set but this can be set again by the user
* **INSTALL\_OFFLINE\_ADDON=“0”**: Deactivates the installation of the Offline Add-on. In the list of the components to be installed in the setup, a check mark has not been set but this can be set again by the user
* **IGNORE\_TS\_SERVICES=“1”**: Deactivates the installation of the terminal server services, no matter on which system the installation is running
* **INSTALL\_IDP\_SERVICE="1"**
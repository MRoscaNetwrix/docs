---
title: Application Silent Installer Option
sidebar_label: silent installation
description: Installation procedures, system requirements, and deployment configuration for Privilege Secure components and services.
---

# Application Silent Installer Option

Follow the steps to install the Privilege Secure application from the command prompt.

**Step 1 –** Copy the `NPS.exe` file to the desktop of the application server.

**Step 2 –** Run the following command as an administrator:

nps.exe /quiet

- To add a non-default installation directory, append the following to the command where the
  `[Path]` parameter is the desired installation directory location:

  nps.exe /quiet PRODUCTDIR="[Path]"

  For example: `nps.exe /quiet PRODUCTDIR="D:\Stealthbits\PAM"`

The Privilege Secure application installs in the background to the specified folder location.

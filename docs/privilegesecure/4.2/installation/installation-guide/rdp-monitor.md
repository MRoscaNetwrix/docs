---
title: Install Remote Desktop Monitor Service on Target RDP Hosts
sidebar_label: rdp monitor
description: Installation procedures, system requirements, and deployment configuration for Privilege Secure components and services.
---

# Install Remote Desktop Monitor Service on Target RDP Hosts

The Netwrix Privilege Secure Remote Desktop Monitor service needs to be installed on the target host
that users will establish RDP connections to via an Access Policy session. Run the **NPS.TSMon.exe**
on the target host to install and enable this service. The EXE file is located in the Extras folder
of the Privilege Secure installation download ZIP file.

The Windows event activity that occurs during an RDP session is then displayed and is searchable
within the [Live Session Viewer Window](/docs/privilegesecure/4.2/user-guide/common-features/session-management/live-viewer.md) and the
[Replay Viewer Window](/docs/privilegesecure/4.2/user-guide/common-features/session-management/replay-viewer.md) with keystroke details, which are
monitored and recorded without this service.

Follow the steps to install the Remote Desktop Monitor service.

**Step 1 –** Copy the **NPS.TSMon.exe** file to the target host.

_Remember,_ this file is in the Extras folder of the Privilege Secure installation download
extracted ZIP file.

**Step 2 –** Run the EXE file. The Netwrix Privilege Secure Terminal Services Monitor Setup window
opens.

**Step 3 –** Check the I agree to the license terms and conditions box.

_Remember,_ it is a best practice to read the terms before agreeing to them.

**Step 4 –** Click Install.

**Step 5 –** When the installation has completed successfully, click Close. The Netwrix Privilege
Secure Terminal Services Monitor Setup window closes.

**Step 6 –** Open Services (`services.msc`) to verify the Netwrix Privilege Secure Remote Desktop
Monitor service is installed and enabled with Automatic Startup Type and Log On As Local System.

The service is now listening for terminal services connections.

**NOTE:** It is necessary for the Record Proxy Sessions option to be enabled on the connection
profile for the associated access policy. See the
[Connection Profiles Page](/docs/privilegesecure/4.2/administration/policies/connection-profiles/add-connection-profile.md) topic for additional
information.

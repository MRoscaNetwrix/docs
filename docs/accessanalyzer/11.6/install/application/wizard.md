---
title: "Enterprise Auditor Core Installation"
description: "Enterprise Auditor Core Installation"
sidebar_position: 20
---

# Enterprise Auditor Core Installation

Save the organization’s Enterprise Auditor license key, received from your Netwrix Sales
Representative, to the server where Enterprise Auditor is to be installed. Then follow the steps to
install Enterprise Auditor.

:::note
The process explained in this topic assumes that both the downloaded binary and the
license (.lic) file are located on the server which will become the Enterprise Auditor Console.
:::


:::warning
If User Account Control (UAC) is enabled on the server, ensure the installation package
is run in Administrative/privilege mode.
:::


**Step 1 –** Run the **Netwrixaccessanalyzer.exe** executable to open the Enterprise Auditor
Setup Wizard.

![Setup Wizard Welcome page](/img/product_docs/accessanalyzer/11.6/install/application/welcome.webp)

**Step 2 –** On the Welcome page, click **Next** to begin the installation.

![ End User License Agreement](/img/product_docs/accessanalyzer/11.6/install/application/eula.webp)

**Step 3 –** On the End-User License Agreement page, read the End User License Agreement, then check
the **I accept the terms in the License Agreement** box and click **Next**.

![Destinations Folder page](/img/product_docs/accessanalyzer/11.6/install/application/destination.webp)

**Step 4 –** On the Destination Folder page, click **Change** to select the folder location to
install Enterprise Auditor. The default destination folder is
`C:\Program Files (x86)\STEALTHbits\StealthAUDIT\`. Click **Next** to continue.

|                                                                                                         |     |                                                                                                                                           |
| ------------------------------------------------------------------------------------------------------- | --- | ----------------------------------------------------------------------------------------------------------------------------------------- |
| ![License File page](/img/product_docs/accessanalyzer/11.6/install/application/license.webp) |     | ![License File page with mapped file](/img/product_docs/accessanalyzer/11.6/install/application/licensemapped.webp) |
| Default License File Page                                                                               |     | Mapped License File                                                                                                                       |

**Step 5 –** On the License File page, click **Browse** and navigate to your **StealthAUDIT.lic**
file. When the path to the file is visible in the textbox, click **Next**.

:::note
The license file must be stored on the Enterprise Auditor Console server before the
installation begins.
:::


![License Features page](/img/product_docs/accessanalyzer/11.6/install/application/licensefeatures.webp)

**Step 6 –** The License Features page displays a list of all features covered by the imported
license. It also displays the name of the organization which owns the license, the expiration date,
and the host limit. These are the features that will be installed. Click **Next**.

![Ready to install Netwrix Access Governance page](/img/product_docs/accessanalyzer/11.6/install/application/ready.webp)

**Step 7 –** On the Ready to install Enterprise Auditor page, click **Install** to begin the
installation.

![Setup Wizard Completed page](/img/product_docs/accessanalyzer/11.6/install/application/completed.webp)

**Step 8 –** When the installation has completed, click **Finish** to exit the wizard.

The Enterprise Auditor Console has been installed, and two desktop icons have been created:
Enterprise Auditor and Published Reports. Launch the Enterprise Auditor application to complete the
initial configuration.

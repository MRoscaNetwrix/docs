---
sidebar_position: 7701
title: Install Components & Methods
---

# Install Components & Methods

The `NPS.zip` file that can be downloaded from the Netwrix Customer portal contains the following:

![Contents of the NPS.zip file download](../../../../../../static/images/PrivilegeSecure_4.2/Content/Resources/Images/PrivilegeSecure/AccessManagement/Install/NPSzip.png "Contents of the NPS.zip file download")

* NPS\_Setup.exe – Opens the Netwrix Setup Launcher to install the Privilege Secure components:

  * Prerequisites Setup – Checks for prerequisites. If any are missing it downloads and installs the missing components.
  * PostgreSQL Setup – Installs the PostgreSQL database on the application server.

    **CAUTION:** The PostgreSQL database must be installed before installing the application. It can be installed separately or through the Netwrix Setup Launcher.
  * Privilege Secure Setup – Installs the application
* Pre-Reqs folder – Contains an application executable for installed the required version of .NET Framework. By default, this installer is run as part of the Netwrix Setup Launcher.
* The Extras folder – Contains additional standalone installers:

  * Enablement Toolkit.exe – Installs a utility that offers a GUI for common testing scenarios used when troubleshooting the application. See the [Troubleshooting](../Admin/Troubleshooting "Troubleshooting") topic for additional information.
  * NPS.ActionService.exe – Installs the NPS Action Service nodes. By default, this service is installed on the application server. This executable can be copied to other servers to install the service. See the [Action Service Install](ActionService "Action Service Install") topic for additional information.
  * NPS.DbCfg.msi – Installs NPS Windows database configuration
  * NPS.exe – Installs the Privilege Secure application. By default, this installer is run as part of the Netwrix Setup Launcher. It installs the following components:

    * NPS Action Service
    * NPS Email Service
    * NPS License Service
    * NPS Proxy Service
    * NPS Scheduler Service
    * Web Service

    **NOTE:** Use this installer if you are not using the Netwrix Setup Launcher. Run the installer as an administrator and follow the [Install Application](SetupLauncher#Install "Install Application") instructions, starting with Step 2.
  * NPS.HaMgr.exe – Installs the High Availability Management tool. If high availability setup is desired, please coordinate with [Netwrix Support](https://www.netwrix.com/support.html "Netwrix Support") and consult the [How to Configure High Availability (HA) Using SbPAM.HaMgr.exe (now NPS.HaMgr.exe)](https://helpcenter.netwrix.com/bundle/z-kb-articles-salesforce/page/kA04u0000000HfOCAU.html "How to Configure High Availability (HA) Using SbPAM.HaMgr.exe (now NPS.HaMgr.exe)") knowledge base article.
  * NPS.ProxyService – Installs the NPS Proxy Service nodes. It is available as both an EXE and MSI format. By default, this service is installed on the application server. This executable can be copied to other servers to install the service. The MSI can be used with a software deployment tool. See the [Proxy Service Install](ProxyService "Proxy Service Install") topic for additional information.
  * NPS.SchedulerService.exe – Installs the NPS Scheduler Service nodes. By default, this service is installed on the application server. This executable can be copied to other servers to install the service. See the [Scheduler Service Install](SchedulerService "Scheduler Service Install") topic for additional information.
  * NPS.SiemService.exe – Installs the NPS SIEM Service nodes. This executable can be copied to other servers to install the service. See the SIEM Service Install topic for additional information.
  * NPS.TSMon.exe – Installs the Netwrix Privilege Secure Remote Desktop Service. This service is used to monitor Windows events during an RDP session. See the [Install Remote Desktop Monitor Service on Target RDP Hosts](RDPMonitor "Remote Desktop Monitor Service Install on Target RDP Hosts") topic for additional information.
  * SbPAMPowershellModules.msi – Installs the Netwrix Privilege Secure PowerShell modules. These modules allow for custom PowerShell scripting tasks to be run against the application API.

    **NOTE:** PowerShell 7.1 is a prerequisite to install these modules.
  * sbpam-url.exe – Installs the sbpam-url URL handler. This will automatically launch SSH sessions from the browser in your preferred SSH client program. See the [Invoking Desktop SSH Client Automatically](https://helpcenter.netwrix.com/bundle/z-kb-articles-salesforce/page/kA04u0000004n11CAA.html "Invoking Desktop SSH Client Automatically") Knowledge Base Article for additional information.
  * SbPostgreSQL16.exe – Installs the PostgreSQL v16 database. By default, this installer is run as part of the Netwrix Setup Launcher. It installs the following components:

    * postgresql-x64-16 service
    * PostgreSQL directory and database

    **NOTE:** Use this installer if you are not using the Netwrix Setup Launcher. Run the installer as an administrator and follow the [Install PostgreSQL Database](SetupLauncher#Install2 "Install PostgreSQL Database") instructions, starting with Step 2.

***RECOMMENDED:*** Antivirus software should be disabled during the component installation.

The Netwrix Setup Launcher checks for prerequisites and installs both the database and application on the sames server. See the [Netwrix Setup Launcher](SetupLauncher "Netwrix Setup Launcher") topic for instructions. If the desire is to install the database on a different server, use the appropriate EXE files from the Extras folder.

The application also has a silent installation option. When installing by command line, the directory path is respected only when the installer is run in silent mode. See the [Application Silent Installer Option](Silent "Application Silent Installer Option") topic for additional information.

There is also a Browser Extension that can be installed for Privilege Secure users. See the [Browser Extension App](../EndUser/BrowserExtension/BrowserExtension "Browser Extension App") topic for additional information.

*Remember,* Privilege Secure licensing is done according to user count. Any user who is provisioned access to Privilege Secure will consume a license after their first login. This is true for all users, regardless of role (Administrator, Reviewer, User, or Custom Role). See [Import the License File](../Admin/ImportLicense "Import the License File") topic for additional information.
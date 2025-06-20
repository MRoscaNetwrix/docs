# Installation

Threat Prevention consists of a number of components that work together to monitor activity on a
network.

- Threat Prevention Enterprise Manager
- Threat Prevention Windows console (Administration Console)
- Threat Prevention Agents deployed across the environment
- Threat Prevention EPE Rest Site that third parties can use to integrate with the Enterprise
  Password Enforcer (EPE) solution
- Netwrix Threat Manager Reporting Module that is installed with a separate installation package

**NOTE:** With SteathINTERVEPT v7.3.5 through 7.3.9, you could only install one instance of the
Administration Console, and that too on the same machine as the Enterprise Manager. Threat
Prevention v7.4 supports the deployment of remote Administration Console, enabling you to install
additional consoles on standalone machines, like administrator or user workstations. In this way,
users can launch the Administration Console on their workstations, as an alternate to using it on
the Enterprise Manager server only.

The following components are installed by the Threat Prevention installation package:

- Threat Prevention Prerequisites – Checks for .NET Framework 4.7+ and installs .NET Framework 4.7
  if it is not detected
- Enterprise Manager

  - Creates the NVMonitorConfig and NVMonitorData databases on the designated SQL Server
  - Installs the Threat Prevention Enterprise Manager service

- Administration Console – Installs the user application for administering the Threat Prevention
  application

See the following topics for additional information:

- [Application Server Install](/docs/threatprevention/7.4/install/application.md)
- [Administration Console Remote Install](/docs/threatprevention/7.4/install/adminconsole.md)
- [Agent Information](/docs/threatprevention/7.4/install/agent/overview.md)
- [EPE Rest Site Install](/docs/threatprevention/7.4/install/eperestsite.md)
- [Reporting Module Installation](/docs/threatprevention/7.4/install/reportingmodule/overview.md)

## Software Download

Current customers can log in to the Netwrix Customer Portal to download software binaries and
license keys for purchased products. See the
[Customer Portal Access](https://helpcenter.netwrix.com/bundle/NetwrixCustomerPortalAccess/page/Customer_Portal_Access.html)
topic for information on how to register for a Customer Portal account.

Threat Prevention can integrate with the Netwrix Activity Monitor for monitoring event data on NAS
Devices. See the
[Netwrix Activity Monitor Documentation](https://helpcenter.netwrix.com/category/activitymonitor)
for information on this integration.

The following files are available for download:

- threatprevention-server-7.4.x.msi
- threatprevention-agent-7.4.x.exe
- stealthintercept-reporting-2.8.x.zip – Contains the Netwrix Threat Manager Reporting Module
  installer. See the
  [Reporting Module Installation](/docs/threatprevention/7.4/install/reportingmodule/overview.md)
  topic for additional information.

## Antivirus Software Considerations

Occasionally, an organization’s anti-virus program may shut down the processes launched by Threat
Prevention. The processes that may be impacted are listed below.

Threat Prevention Server

Files located within the Threat Prevention installation directory:
`…\Netwrix\Netwrix Threat Prevention`

- SIWinConsole.exe
- SIEnterpriseManager.exe
- SI.ReportingServicesHost.exe
- SI.Services.Schedule.Host.exe
- SIWindowsAgent.exe

Agent Server

Files located within the Threat Prevention Agent installation directory:
`…\Netwrix\Netwrix Threat Prevention\SIWindowsAgent`

- SIWindowsAgent.exe
- SIAgentUpdater.exe
- plsahlp.sys
- ActiveDirectoryMonitorLoader.dll
- SI.ActiveDirectoryMonitor.dll

The following file in the directory: `…\Netwrix\\Netwrix Threat Prevention\Group Policy`

- SIGPOAgent.exe

The following file in the directory: `…\Netwrix\StealthAudit\FSAC`

- SBTService.exe

Client Machines

If you are using Threat Prevention's Enterprise Password Enforcer (EPE) User Feedback module for
client machines, the following file should be excluded:

- SI_CredentailProvider.dll

If this file is blocked by antivirus software, the reasons for rejecting a candidate password will
not be displayed to the end-user, but all EPE rules will be fully enforced.

Domain Controllers

- PPE.dll – If PPE.dll does not load, the password policy will not get enforced

### Netwrix Password Policy Enforcer (PPE)

If you are using Netwrix Password Policy Enforcer, the processes that may be impacted are listed
below.

Client Machines

The following DLLs on the client machines (all computers, mostly end user desktops/laptops) will not
work if they get blocked by antivirus software:

- PPEClt.dll
- APRClt.dll

Netwrix Password Reset Server

If you are using Netwrix Password Reset, then make sure the antivirus program does not block the
following files on the Netwrix Password Reset server:

- apr.sdf
- aprlog.sdf

These files get updated frequently, so there may be some performance benefit, and they do not
contain any executable code.

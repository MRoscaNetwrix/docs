# Supported Data Sources

This section lists platforms and systems that can be monitored with Netwrix Auditor.

## Active Directory

Auditor supports monitoring the following domain controller operating system versions:

- Windows Server 2022
- Windows Server 2019
- Windows Server 2016
- Windows Server 2012 R2
- Windows Server 2012
- Windows Server 2008 R2
- Windows Server 2008

See the [Active Directory](/versioned_docs/auditor_10.6/auditor/configuration/activedirectory/overview.md) topic for additional information.

## Active Directory Federation Services (AD FS)

Auditor supports monitoring the following AD FS operating system versions:

- AD FS 5.0 – Windows Server 2019
- AD FS 4.0 – Windows Server 2016
- AD FS 3.0 – Windows Server 2012 R2

See the [AD FS](/versioned_docs/auditor_10.6/auditor/configuration/activedirectoryfederatedservices/overview.md) topic for additional information.

## Exchange

Auditor supports monitoring the following Exchange Server versions:

- Microsoft Exchange Server 2019
- Microsoft Exchange Server 2016
- Microsoft Exchange Server 2013

See the [Exchange](/versioned_docs/auditor_10.6/auditor/configuration/exchange/overview.md) topic for additional information.

## File Servers

Dell Data Storage

Auditor supports monitoring the following device versions:

- Dell Data Storage (Unity XT, UnityVSA) running any of the following operating environment versions:

  - 5.2.x
  - 5.0.x
  - 4.5.x
  - 4.4.x
- Dell VNX/VNXe/Celerra families

__NOTE:__ Only CIFS configuration is supported.

See the [Dell Data Storage](/versioned_docs/auditor_10.6/auditor/configuration/fileservers/delldatastorage/overview.md) topic for additional information.

Dell Ilison/PowerScale

Auditor supports monitoring the following device versions:

- Dell Isilon/PowerScale versions 7.2 – 9.4

__NOTE:__ Only CIFS configuration is supported.

Auditing of _System_ zone is not supported. As stated by Dell, this zone should be reserved for configuration access only. Current data should be stored in other access zones. See the [Isilon OneFS 8.2.1 CLI Administration Guide](https://www.dellemc.com/en-us/collaterals/unauth/technical-guides-support-information/2019/09/docu95372.pdf) for additional information.

See the [Dell Isilon/PowerScale](/versioned_docs/auditor_10.6/auditor/configuration/fileservers/dellisilon/overview.md) topic for additional information.

NetApp Data ONTAP

Auditor supports monitoring the following device versions:

- Clustered-Mode

  - 9.0 – 9.14
  - 8.3, 8.3.1, 8.3.2
  - 8.2.1 – 8.2.3

__NOTE:__ Only CIFS configuration is supported.

See the [NetApp Data ONTAP](/versioned_docs/auditor_10.6/auditor/configuration/fileservers/netappcmode/overview.md) topic for additional information.

Nutanix

Auditor supports monitoring the following device versions:

- Files 3.6 - 4.3.0

See the [Nutanix](/versioned_docs/auditor_10.6/auditor/configuration/fileservers/nutanix/overview.md) topic for additional information.

Qumulo

Auditor supports monitoring the following device versions:

- Core 3.3.5 - 6.x.x

See the [Qumulo](/versioned_docs/auditor_10.6/auditor/configuration/fileservers/qumulo/overview.md) topic for additional information.

Synology

Auditor supports monitoring the following device versions:

- DSM 7.2
- DSM 7.1
- DSM 7.0
- DSM 6.2.3

See the [Synology](/versioned_docs/auditor_10.6/auditor/configuration/fileservers/synology/overview.md) topic for additional information.

Windows File Servers

Auditor supports monitoring the following operating system versions:

- Windows Server 2022
- Windows Server 2019
- Windows Server 2016
- Windows Server 2012 R2
- Windows Server 2012
- Windows Server 2008 R2
- Windows Server 2008

- Windows 11
- Windows 10 (32 and 64-bit)
- Windows 8.1 (32 and 64-bit)
- Windows 7 (32 and 64-bit)

See the [Windows File Servers](/versioned_docs/auditor_10.6/auditor/configuration/fileservers/windows/overview.md) topic for additional information.

## Group Policy

Auditor supports monitoring the following domain controller operating system versions:

- Windows Server 2022
- Windows Server 2019
- Windows Server 2016
- Windows Server 2012 R2
- Windows Server 2012
- Windows Server 2008 R2
- Windows Server 2008

See the [Group Policy](/versioned_docs/auditor_10.6/auditor/configuration/grouppolicy/overview.md) topic for additional information.

## Logon Activity

Auditor supports monitoring the following domain controller operating system versions:

- Windows Server 2022
- Windows Server 2019
- Windows Server 2016
- Windows Server 2012 R2
- Windows Server 2012
- Windows Server 2008 R2
- Windows Server 2008

See the [Logon Activity](/versioned_docs/auditor_10.6/auditor/configuration/logonactivity/overview.md) topic for additional information.

## Microsoft 365

Exchange Online

Auditor supports monitoring the following versions:

- Exchange Online version provided within Microsoft 365
- Microsoft GCC (government community cloud) and GCC High

  __NOTE:__ DoD tenant types are not supported.

See the [Exchange Online](/versioned_docs/auditor_10.6/auditor/configuration/microsoft365/exchangeonline/overview.md) topic for additional information.

Microsoft Entra ID (formerly Azure AD)

Auditor supports monitoring the following versions:

- Microsoft Entra ID version provided within Microsoft 365
- Microsoft GCC (government community cloud) and GCC High

  __NOTE:__ DoD tenant types are not supported.

See the [Microsoft Entra ID (formerly Azure AD)](/versioned_docs/auditor_10.6/auditor/requirements/microsoft365/azureactivedirectory/overview.md) topic for additional information.

Microsoft Teams (MS Teams)

Auditor supports monitoring the following versions:

- Microsoft Entra ID version provided within Microsoft 365
- Microsoft GCC (government community cloud) and GCC High

  __NOTE:__ DoD tenant types are not supported.

See the [MS Teams](/versioned_docs/auditor_10.6/auditor/configuration/microsoft365/teams/overview.md) topic for additional information.

SharePoint Online

Auditor supports monitoring the following versions:

- SharePoint Online version provided within Microsoft 365
- Microsoft GCC (government community cloud) and GCC High

  __NOTE:__ DoD tenant types are not supported.

See the [SharePoint Online](/versioned_docs/auditor_10.6/auditor/configuration/microsoft365/sharepointonline/overview.md) topic for additional information.

## Network Devices

Cisco ASA Devices

Auditor supports monitoring the following device versions:

- ASA (Adaptive Security Appliance) 8 and above

See the [Configure Cisco ASA Devices](/versioned_docs/auditor_10.6/auditor/configuration/networkdevices/ciscoasa.md) topic for additional information.

Cisco IOS Devices

Auditor supports monitoring the following device versions:

- IOS (Internetwork Operating System) 12, 15, 16, and 17

See the [Configure Cisco IOS Devices](/versioned_docs/auditor_10.6/auditor/configuration/networkdevices/ciscoios.md) topic for additional information.

Cisco Meraki Dashboard

Auditor supports monitoring the following device versions:

- Netwrix recommends the latest version of the Meraki Dashboard

See the [Cisco Meraki Dashboard ](/versioned_docs/auditor_10.6/auditor/configuration/networkdevices/ciscomerakidashboard.md) topic for additional information.

Cisco FTD

Auditor supports monitoring the following device versions:

- FTD (Firepower Threat Defense) 6.5

Fortinet FortiGate Devices

Auditor supports monitoring the following device versions:

- FortiOS 5.6 and above

See the [Configure Fortinet FortiGate Devices](/versioned_docs/auditor_10.6/auditor/configuration/networkdevices/fortinetfortigate.md) topic for additional information.

HPE Aruba Devices

Auditor supports monitoring the following device versions:

- Aruba OS 6.46.4.x – 8.6.0.x (Mobility Master, Mobility Controller)

See the [Configure Pulse Secure Devices](/versioned_docs/auditor_10.6/auditor/configuration/networkdevices/pulsesecure.md) topic for additional information.

Juniper Devices

Auditor supports monitoring the following device versions:

- vSRX with Junos OS 12.1, Junos OS 18.1, Junos OS 20.4R2
- vMX with Junos OS 17.1

See the [Configure Juniper Devices](/versioned_docs/auditor_10.6/auditor/configuration/networkdevices/juniper.md) topic for additional information.

PaloAlto Devices

Auditor supports monitoring the following device versions:

- PAN-OS 7.0, 8.0, 9.0, 10.0

See the [Configure PaloAlto Devices](/versioned_docs/auditor_10.6/auditor/configuration/networkdevices/paloalto.md) topic for additional information.

Pulse Secure Devices

Auditor supports monitoring the following device versions:

- 9.1R3 and above

See the [Configure Pulse Secure Devices](/versioned_docs/auditor_10.6/auditor/configuration/networkdevices/pulsesecure.md) topic for additional information.

SonicWall Devices

Auditor supports monitoring the following device versions:

- WAF 2.0.0.x / SMA v9.x & v10.x
- NS 6.5.х.х with SonicOS 6.5.х and 7.0.x
- SMA 12.2

See the [Configure SonicWall Devices](/versioned_docs/auditor_10.6/auditor/configuration/networkdevices/sonicwall.md) topic for additional information.

## Oracle

Auditor supports monitoring the following versions:

- Database 23c On-Premise
- Database 21c On-Premise
- Database 19c On-Premise
- Database 18c On-Premise
- Database 12c On-Premise (12.1, 12.2)
- Database 11g, limited support

  __NOTE:__  See the [Considerations for Oracle Database 11g](/versioned_docs/auditor_10.6/auditor/configuration/oracle/overview.md#Considerations-for-Oracle-Database-11g) topic for additional information.
- Oracle Database Cloud Service (Enterprise Edition)

See the [Oracle Database](/versioned_docs/auditor_10.6/auditor/configuration/oracle/overview.md) topic for additional information.

## SharePoint

Auditor supports monitoring the following versions:

- Microsoft SharePoint Server Subscription Edition
- Microsoft SharePoint Server 2019
- Microsoft SharePoint Server 2016
- Microsoft SharePoint Foundation 2013 and SharePoint Server 2013
- Microsoft SharePoint Foundation 2010 and SharePoint Server 2010

See the [SharePoint](/versioned_docs/auditor_10.6/auditor/configuration/sharepoint/overview.md) topic for additional information.

## SQL Server

Auditor supports monitoring the following versions:

- Microsoft SQL Server 2022
- Microsoft SQL Server 2019
- Microsoft SQL Server 2017
- Microsoft SQL Server 2016
- Microsoft SQL Server 2014
- Microsoft SQL Server 2012

__NOTE:__ Linux-based versions are not supported.

See the [SQL Server](/versioned_docs/auditor_10.6/auditor/configuration/sqlserver/overview.md) topic for additional information.

## User Activity

Auditor supports monitoring the following versions:

- Windows Server 2022
- Windows Server 2019
- Windows Server 2016
- Windows Server 2012 R2
- Windows Server 2012
- Windows Server 2008 R2
- Windows Server 2008

- Windows 11
- Windows 10 (32 and 64-bit)
- Windows 8.1 (32 and 64-bit)
- Windows 7 (32 and 64-bit)

User Activity data source can support around 300 targets with one user session per target without scalability issues:

- Depending on how dense is the actual user activity, the number can be more for servers but less for workstations.
- 50-100 concurrent sessions per terminal server.

Netwrix recommends using the User Activity auditing only for those infrastructure areas that require more attention due to their sensitivity or criticality. Applicable usage scenarios include, for example:

- Terminal servers where users can log in from external locations
- Areas accessible by contractor personnel
- Servers with sensitive information
- Sessions with elevated privileges

See the [User Activity](/versioned_docs/auditor_10.6/auditor/configuration/useractivity/overview.md) topic for additional information.

## VMware Servers

Auditor supports monitoring the following versions:

- VMware ESX/ESXi: 6.0 – 6.7, 7.0, 8.0
- VMware vCenter Server: 6.0 – 6.7, 7.0, 8.0

See the [VMware](/versioned_docs/auditor_10.6/auditor/configuration/vmware/overview.md) topic for additional information.

## Windows Servers

Windows Servers & Desktops

Auditor supports monitoring the following operating system versions:

- Windows Server 2022
- Windows Server 2019
- Windows Server 2016
- Windows Server 2012 R2
- Windows Server 2012
- Windows Server 2008 R2
- Windows Server 2008

- Windows 11
- Windows 10 (32 and 64-bit)
- Windows 8.1 (32 and 64-bit)
- Windows 7 (32 and 64-bit)

DNS & DHCP

Auditor supports monitoring the following operating system versions:

- Windows Server 2022
- Windows Server 2019
- Windows Server 2016
- Windows Server 2012 R2
- Windows Server 2012
- Windows Server 2008 R2
- Windows Server 2008

__NOTE:__ DNS support is limited on Windows Server 2008 to Windows Server 2008 SP2 (32 and 64-bit). DHCP is not supported on Windows Server 2008.

Internet Information Services (IIS)

Auditor supports monitoring the following operating system versions:

- IIS 7.0 and above.

See the [Windows Server](/versioned_docs/auditor_10.6/auditor/configuration/windowsserver/overview.md) topic for additional information.

## Netwrix Integration API

In addition to data sources monitored within the product, Auditor supports technology integrations leveraging its API. Download free add-ons from [Netwrix Auditor Add-on Store](https://www.netwrix.com/netwrix_addons.html) to enrich your audit trails with activity from the following systems and applications.

Also, there are even add-ons that can export data collected by Auditor to other systems (e.g., ArcSight and ServiceNow).

See the [Integration API](/versioned_docs/auditor_10.6/auditor/api/overview.md) topic for additional information.

## Monitored Object Types, Actions, and Attributes

Review the list of object types, attributes and components audited and reported by Netwrix Auditor.

- [Active Directory](/versioned_docs/auditor_10.6/auditor/configuration/activedirectory/overview.md)
- [AD FS](/versioned_docs/auditor_10.6/auditor/configuration/activedirectoryfederatedservices/overview.md)
- [Exchange](/versioned_docs/auditor_10.6/auditor/configuration/exchange/overview.md)
- [File Servers](/versioned_docs/auditor_10.6/auditor/configuration/fileservers/overview.md)

  - [Dell Data Storage](/versioned_docs/auditor_10.6/auditor/configuration/fileservers/delldatastorage/overview.md)
  - [Dell Isilon/PowerScale](/versioned_docs/auditor_10.6/auditor/configuration/fileservers/dellisilon/overview.md)
  - [NetApp Data ONTAP](/versioned_docs/auditor_10.6/auditor/configuration/fileservers/netappcmode/overview.md)
  - [Nutanix](/versioned_docs/auditor_10.6/auditor/configuration/fileservers/nutanix/overview.md)
  - [Qumulo](/versioned_docs/auditor_10.6/auditor/configuration/fileservers/qumulo/overview.md)
  - [Synology](/versioned_docs/auditor_10.6/auditor/configuration/fileservers/synology/overview.md)
  - [Windows File Servers](/versioned_docs/auditor_10.6/auditor/configuration/fileservers/windows/overview.md)
- [Group Policy](/versioned_docs/auditor_10.6/auditor/configuration/grouppolicy/overview.md)
- [Logon Activity](/versioned_docs/auditor_10.6/auditor/configuration/logonactivity/overview.md)
- [Microsoft 365](/versioned_docs/auditor_10.6/auditor/configuration/microsoft365/overview.md)

  - [Exchange Online](/versioned_docs/auditor_10.6/auditor/configuration/microsoft365/exchangeonline/overview.md)
  - [Microsoft Entra ID](/versioned_docs/auditor_10.6/auditor/configuration/microsoft365/microsoftentraid/overview.md)
  - [SharePoint Online](/versioned_docs/auditor_10.6/auditor/configuration/microsoft365/sharepointonline/overview.md)
  - [MS Teams](/versioned_docs/auditor_10.6/auditor/configuration/microsoft365/teams/overview.md)
- [Network Devices](/versioned_docs/auditor_10.6/auditor/configuration/networkdevices/overview.md)
- [Oracle Database](/versioned_docs/auditor_10.6/auditor/configuration/oracle/overview.md)
- [SharePoint](/versioned_docs/auditor_10.6/auditor/configuration/sharepoint/overview.md)
- [SQL Server](/versioned_docs/auditor_10.6/auditor/configuration/sqlserver/overview.md)
- [User Activity](/versioned_docs/auditor_10.6/auditor/configuration/useractivity/overview.md)
- [VMware](/versioned_docs/auditor_10.6/auditor/configuration/vmware/overview.md)
- [Windows Server](/versioned_docs/auditor_10.6/auditor/configuration/windowsserver/overview.md)

Review the list of actions audited and reported by Netwrix Auditor. Actions vary depending on the data source and the object type.

| Action | Active Directory | Active Directory Federation Services | Exchange  Exchange Online | File Servers | Group Policy | Logon Activity | Microsoft Entra ID (formerly Azure AD) | Oracle database | SharePoint  SharePoint Online | SQL Server | User Activity | VMware Servers | Windows Server |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Added | + | - | +\* | + | + | – | + | + | + | + | – | + | + |
| Removed | + | - | +\* | + | + | – | + | + | + | + | – | + | + |
| Modified | + | – | +\* | + | + | – | + | + | + | + | – | + | + |
| Add (failed attempt) | – | – | – | + | – | – | – | + | – | – | – | – | – |
| Remove (failed attempt) | – | – | – | + | – | – | – | + | – | – | – | – | – |
| Modify (failed attempt) | – | – | – | + | – | – | – | + | – | – | – | – | + |
| Read | – | – | +\* | + | – | – | – | + | + | – | – | – | – |
| Read (failed attempt) | – | – | – | + | – | – | – | + | – | – | – | – | – |
| Renamed | – | – | – | + | – | – | – | + | +\*\* | – | – | – | – |
| Moved | – | – | +\* | + | – | – | – | – | + | – | – | – | – |
| Rename (failed attempt) | – | – | – | + | – | – | – | + | – | – | – | – | – |
| Move (failed attempt) | – | – | – | + | – | – | – | – | – | – | – | – | – |
| Checked in | – | – | – | – | – | – | – | – | + | – | – | – | – |
| Checked out | – | – | – | – | – | – | – | – | + | – | – | – | – |
| Discard check out | – | – | – | – | – | – | – | – | + | – | – | – | – |
| Successful logon | – | + | – | – | – | + | + | + | – | + | – | + | – |
| Failed logon | – | + | – | – | – | + | + | + | – | + | – | +\*\*\* | – |
| Logoff | – | – | – | – | – | – | – | + | – | – | – | – | – |
| Copied | – | – | +\* | + | – | – | – | – | +\*\* | – | – | – | – |
| Sent | – | – | +\* | – | – | – | – | – | – | – | – | – | – |
| Activated | – | – | – | – | – | – | – | – | – | – | + | – | – |
| Support for state-in-time data collection | + | – | + | + | + | - | + | - | + | - | - | + | + |

\* —these actions are reported when auditing non-owner mailbox access for Exchange or Exchange Online.

\*\* — these actions are reported for SharePoint Online only.

\*\*\* — Auditor will not collect data on _Failed Logon_ event for VMware in case of incorrect logon attempt through VMware vCenter Single Sign-On; also, it will not collect logons using SSH.

# Upgrade to the Latest Version

Netwrix recommends that you upgrade from the older versions of Netwrix Auditor to the latest version available to take advantage of the new features.

Seamless upgrade to Netwrix Auditor 10.6 is supported for versions 10.5 and 10.0.

If you use an earlier version of Netwrix Auditor, then you need to upgrade sequentially right to version 10.5. Review the following Netwrix knowledge base article for more information: [Upgrade Increments for Netwrix Auditor](https://helpcenter.netwrix.com/bundle/z-kb-articles-salesforce/page/kA00g000000H9eJCAS.html).

## Before Starting the Upgrade

Before you start the upgrade, it is strongly recommended taking the following preparatory steps:

__Step 1 –__ If your Netwrix Auditor Server is running on Windows Server 2008 or 2008 R2, you must upgrade its OS to a supported version before upgrading Netwrix Auditor itself.

__Step 2 –__ Check that the account under which you plan to run Netwrix Auditor setup has the local Administrator rights.

__Step 3 –__ Back up Netwrix databases – these are all Audit databases, Integration API database, and others (their default names start with _Netwrix_). For that:

1. Start Microsoft SQL Server Management Studio and connect to SQL Server instance hosting these databases.
2. In Object Explorer, right-click each Netwrix database and select Tasks → Back Up.
3. Wait for the process to complete.

__Step 4 –__ Back up the Long-Term Archive folder, by default located at _C:\ProgramData\Netwrix Auditor\Data_. You can, for example, copy and archive this folder manually, or use your preferred backup routine.

__Step 5 –__ If you can capture a snapshot of the server where Netwrix Auditor Server resides, Netwrix recommends doing so.

__Step 6 –__ Finally, close the Netwrix Auditor console.

### General Considerations and Known Issues

During the seamless upgrade from previous versions, Netwrix Auditor preserves its configuration, so you will be able to continue auditing right after finishing the upgrade. However, there are some considerations you should examine - they refer to the upgrade process and post-upgrade product operation. The issues listed below apply to upgrade from 9.96 and 10.

- After the upgrade you may receive temporary data collection errors – they occur when the program tries to upload collected data to the Audit Database before the database upgrade is finished.
- Microsoft Exchange Server 2010 is no longer supported. Please upgrade your Exchange Server to a new version.
- For Netwrix Auditor for SharePoint Online, the following data will be available within 24 hours after upgrade:

  - Current values for SharePoint Online risk metrics (Microsoft 365)
  - Data in the Objects Shared with External or Anonymous Users state-in-time report
  - Numbers of shared objects and drill downs to reports in the SharePoint Online Site Collections External Sharing state-in-time report.
- For auditing cloud-based applications (Microsoft Entra ID, Exhange Online, SharePoint Online, and MS Teams) with Netwrix Auditor using basic authentication: before an upgrade from version 10.0 and earlier, make sure that the account under which the upgrade will be performed has sufficient rights and permissions to perform initial data collection and upgrade. Review the following for more information about required rights and permissions:

  - [Permissions for Microsoft Entra ID Auditing](/versioned_docs/auditor_10.6/auditor/configuration/microsoft365/microsoftentraid/permissions.md)
  - [Permissions for Exchange Online Auditing](/versioned_docs/auditor_10.6/auditor/configuration/microsoft365/exchangeonline/permissions.md)
  - [Permissions for SharePoint Online Auditing
    ](/versioned_docs/auditor_10.6/auditor/configuration/microsoft365/sharepointonline/permissions.md)
  - [Permissions for Teams Auditing](/versioned_docs/auditor_10.6/auditor/configuration/microsoft365/teams/permissions.md)
- For auditing cloud-based applications (Microsoft Entra ID, Exchange Online, SharePoint Online, and MS Teams) with Netwrix Auditor using modern authentication: additional configuration of the Entra ID app permissions is required. Review the following for more information about required rights and permissions:

  - [Permissions for Microsoft Entra ID Auditing](/versioned_docs/auditor_10.6/auditor/configuration/microsoft365/microsoftentraid/permissions.md)
  - [Permissions for Exchange Online Auditing](/versioned_docs/auditor_10.6/auditor/configuration/microsoft365/exchangeonline/permissions.md)
  - [Permissions for SharePoint Online Auditing
    ](/versioned_docs/auditor_10.6/auditor/configuration/microsoft365/sharepointonline/permissions.md)
  - [Permissions for Teams Auditing](/versioned_docs/auditor_10.6/auditor/configuration/microsoft365/teams/permissions.md)
- Netwrix Auditor for Oracle Database. If you use the following combination of the audit settings: Mixed Mode + Fine Grained Auditing, please check your configuration. You may need to re-configure your audit since the Oracle Database data collection mechanism was changed. See the [Supported Data Sources](/versioned_docs/auditor_10.6/auditor/requirements/supporteddatasources.md) and [Verify Your Oracle Database Audit Settings](/versioned_docs/auditor_10.6/auditor/configuration/oracle/verifysettings.md) topics for additional information.
- During the initial data collection, the product automatically upgrades services responsible for Windows Server and SharePoint network traffic compression. Consider the following:

  - During the Netwrix Auditor for SharePoint Core Service upgrade, your SharePoint sites will be temporarily unavailable. The duration of the upgrade depends on your SharePoint Farms size and usually it takes a few minutes. For bigger SharePoint farms, consider up to 10 minutes for a successful service upgrade and the same for the rollback in case of an upgrade failure.
  - During the Netwrix Auditor for Windows Server Compression Service upgrade you may see the following errors: _"The Compression Service has encountered an internal error: Unable to update the Compression Service on the following server: `<server name>`"_. Ignore these errors and wait up to one hour for the upgrade completes.
- For the User Password Changes report to function properly after the upgrade, you need to comment out or delete the "\*._PasswordChanged_" line in the omitproplist.txt file again.
- For Exchange Online, the "_Who_" field in search, reports, Activity Summary emails, etc., shows User Principal Name (UPN) instead of Display Name.

## Upgrade Procedure

You can upgrade Netwrix Auditor 10.0 and 10.5 to 10.6 by running the installation package.

Customers who are logged in to the Netwrix Customer Portal can download the latest version of their software products from the My Products page: [https://www.netwrix.com/my_products.html](https://www.netwrix.com/my_products.html). See the [Customer Portal Access](https://helpcenter.netwrix.com/bundle/NetwrixCustomerPortalAccess/page/Customer_Portal_Access.html) topic for information on how to register for a Customer Portal account.

Partners and MSPs who are logged into the Netwrix Partner Portal can download the latest version of their software products from the My Product page: [https://www.netwrix.com/par/site/products](https://www.netwrix.com/my_products.html). To receive an invitation to the Partner Portal, please contact [netwrix.msp@netwrix.com](http://netwrix.msp@netwrix.com/).

Follow the steps to perform the upgrade.

__Step 1 –__ Make sure you have completed the preparatory steps above.

__Step 2 –__ Run the setup on the computer where the Auditor  Server resides. See the [Installation](/versioned_docs/auditor_10.6/auditor/install/overview.md) topic for additional information.

__Step 3 –__ If you have a client-server deployment, then after upgrading the server run the setup on all remote machines where the Auditor Client resides.

Netwrix recommends reviewing your current port configuration after every re-installation or upgrade.

If you were auditing Windows Server or SharePoint server/farm, and the corresponding Core Services were installed automatically according to the monitoring plan settings, then they will be upgraded automatically during the initial data collection. During the Netwrix Auditor for SharePoint Core Service upgrade, your SharePoint sites will be temporarily unavailable.

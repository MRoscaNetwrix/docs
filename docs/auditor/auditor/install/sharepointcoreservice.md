# Install for SharePoint Core Service

This section contains instructions on how to install Netwrix Auditor for SharePoint Core Service.

During the Netwrix Auditor for SharePoint Core Service installation / uninstallation your SharePoint sites may be unavailable.

Prior to the Netwrix Auditor for SharePoint Core Service installation, review the following prerequisites and make sure that:

- Netwrix Auditor for SharePoint Core Service is going to be installed on the computer that hosts SharePoint Central Administration in the audited SharePoint farm.
- [.Net Framework 3.5 SP1](http://www.microsoft.com/en-us/download/details.aspx?id=22) is installed on the computer that hosts SharePoint Central Administration in the audited SharePoint farm.
- The SharePoint Administration (SPAdminV4) service is started on the target computer. See [SharePoint](../configuration/sharepoint/overview.md) for more information.
- The user that is going to run the Core Service installation:
  - Is a member of the local Administrators group on SharePoint server, where the Core Service will be deployed.
  - Is granted the SharePoint_Shell_Access role on SharePoint SQL Server configuration database. See [Permissions for SharePoint Auditing](../configuration/sharepoint/permissions.md) topic for more information.

Follow the steps to install Netwrix Auditor for SharePoint Core Service manually.

__Step 1 –__ On the computer where Auditor Server resides,navigate to _%Netwrix Auditor installation folder%\SharePoint Auditing__\SharePointPackage_ and copy SpaPackage_`<version>`.msi to the computer where Central Administration is installed.

__Step 2 –__ Run the installation package.

__Step 3 –__ Follow the instructions of the setup wizard. When prompted, accept the license agreement and specify the installation folder.

# Using Basic Authentication with SharePoint Online

With basic authentication, your SharePoint Online will be accessed on behalf of a user. You will need to provide Office 365 user name and password in the monitored item properties. To access the Microsoft Entra ID (formerly Azure AD)/Office 365 organization and perform initial data collection, the user account will need an administrative role in the cloud-based infrastructure.

The user account should be a _Cloud-only_ account.

Further permission assignment will depend on the data you plan to collect:

- To collect both activity and state-in-time data, the administrative role will be still needed. See the table below for details.
- To collect activity data only, the privileged role can be revoked from the specified account after the initial data collection.

## Required Roles and Permissions

| To... | Requirement | Comment |
| --- | --- | --- |
| Collect activity and state-in-time data | Any of the following role combinations:   - Application Administrator & Privileged Role Administrator  OR - Cloud Application Administrator & Privileged Role Administrator  OR - _Global Admin_ (_Company Administrator_ in Microsoft Entra ID PowerShell terms) | Prepare a __Cloud-only__ user account and specify it in the monitored item properties. See the [SharePoint Online](/docs/product_docs/auditor/auditor/configuration/microsoft365/sharepointonline/overview.md) topic for additional information. |
| Collect activity data only | 1. For initial connection to SharePoint Online, initial data collection, and Netwrix Auditor upgrade from previous version — any of the role combinations listed above. 2. After the initial data collection, the privileged roles can be revoked from this account. |  |

## Assigning a Privileged Role for SharePoint and Office 365

When configuring a monitored item for Microsoft Entra ID (formerly Azure AD) or Office 365 auditing with basic authentication, specify a data collecting account that has sufficient privileges in Microsoft Entra ID. This account should be able to create a dedicated application in your Microsoft Entra ID domain. Depending on your requirements and company policies, you can select one of the following approaches:

- Assign a privileged role (for example, _Application Administrator_ & _Privileged Role Administrator_) to the account, then revoke it after the application creation and initial data collection, and assign a less-privileged role to this account (for example, _Security Reader_).
- Use the account with a privileged role on a regular basis. Any additional role assignments will not be necessary in this case. If you select this method, contact your security administrator to avoid violations of security policies in your organization.

__NOTE:__ If you previously used a non-privileged account for Microsoft Entra ID data collection in your Netwrix Auditor, consider that after the upgrade you will have to perform the role assignment procedure again, selecting one of these approaches. Until then, data collection will not be performed.

Follow the steps to assign a privileged role to the account.

__Step 1 –__ Sign in to Microsoft Entra ID portal using your Microsoft account.

__Step 2 –__ Select Microsoft Entra ID on the left.

__Step 3 –__ Select the account that you want to use as data collecting account, or create a new user.

__Step 4 –__ Make sure you have disabled multi-factor authentication for this account.

__Step 5 –__ Expand Directory role and select the role you need (for example, Global admin or any other privileged role).

_Remember,_ In Microsoft Graph API, Microsoft Entra ID Graph API, and Microsoft Entra ID PowerShell, the Global admin role is identified as Company Administrator.

__Step 6 –__ Click OK.

__Step 7 –__ In Auditor, create a monitoring plan for auditing Microsoft Entra ID and specify this account with this privileged role on the Specify the account for collecting data step.

__Step 8 –__ Wait until initial data collection completes.

__Step 9 –__ Open Microsoft Entra ID portal and remove the privileged role from the account.

__Step 10 –__ Assign a less-privileged role to this account.

A less privileged role has now been assigned to the account.

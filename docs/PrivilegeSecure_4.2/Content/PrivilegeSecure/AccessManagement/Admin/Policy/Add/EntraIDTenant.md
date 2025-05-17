---
sidebar_position: 7789
title: Add New Microsoft Entra ID Tenant
---

# Add New Microsoft Entra ID Tenant

Follow the steps to add Microsoft Entra ID (formerly Azure AD) resource to the Privilege Secure Console.

**Step 1 –** Navigate to the **Resources** page.

**Step 2 –** Click **Add** > **New Microsoft Entra ID Tenant**

![Add Azure AD Tenant](../../../../../../../../static/images/PrivilegeSecure_4.2/Content/Resources/Images/PrivilegeSecure/AccessManagement/Admin/Policy/Resources/AddAzureADTenant.png "Add Azure AD Tenant")

**Step 3 –** Enter the following information:

* Enter Entra ID Name — Displays the name of the resource
* Platform — Displays the type of platform, which defines the resource
* Tenant ID — Displays the globally unique identifier for the targeted tenant implementation as found in Entra ID
* Logon URL — Displays the primary logon page
* Email Domain — Displays the domain part of the user principal name used by the Tenant as found in Entra ID on the Users page, under “Identity Issuer”
* Associated Domain — For hybrid Entra ID environments, assign the on-premises Active Directory domain that is synchronized with the tenant, otherwise leave set to **None**
* Process Group Memberships — Select this checkbox to enable Netwrix Privilege Secure to collect group membership information. This is unchecked by default.
* Synchronize Now button — Scans the domain for users, groups, members, and computers. The Cancel button, which is only visible when scanning can be used to stop the resource scan. This scan can also be scheduled from the [Platforms Page](../Page/Platforms/Overview "Platforms Page").
* Service Account — Displays the service account associated with the resource
* * Visit icon — Go to the Service Account page to view details of the selected service account.
  * Add New Service Account icon — Open the Add New Service Account window. The fields are identical to those on the Service Accounts page.

**Step 4 –** Click **Save** to add the Microsoft Entra ID Tenant to the console.

The new Microsoft Entra ID tenant has been on-boarded. See the [Microsoft Entra ID Details Page](../Page/Details/EntraID "Microsoft Entra ID Details Page") topic for additional information.
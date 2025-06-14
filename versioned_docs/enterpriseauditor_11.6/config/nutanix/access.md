# Nutanix Appliance Access & Sensitive Data Auditing Configuration

The credentials used to run Enterprise Auditor scans on Nutanix appliances must have the __Backup Admin: Backup Access only__ role assigned.

## Nutanix Prism Central Interface

Follow the steps to configure the required account in the Nutanix Prism Central Interface.

__Step 1 –__ Select the __Home__ dropdown and select __File Server__.

__Step 2 –__ On the file server page, under actions select __Launch Files Console__.

__Step 3 –__ On the new files URL page, locate the __Configuration__ dropdown and select __Manage Roles__.

![Nutanix Backup Admin: Backup Access only role](/img/versioned_docs/enterpriseauditor_11.6/config/nutanix/nutanixbackupadminrole.png)

__Step 4 –__ On the Manage Roles window, add an account with the __Backup Admin: Backup Access only__ role.

This account must be used for running the Enterprise Auditor scans on Nutanix appliances.

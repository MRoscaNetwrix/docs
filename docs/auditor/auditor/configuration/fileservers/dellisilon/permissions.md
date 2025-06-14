# Permissions for Dell Isilon/PowerScale Auditing

Before you start creating a monitoring plan to audit your Dell Isilon/PowerScale file storage system, plan for the account that will be used for data collection.
See the Configuring Your Dell Isilon/PowerScale Cluster for Auditing section for additional information.
The following scenarios are possible:

- Automatic configuration: you can use a special shell script for configuring an audited Dell Isilon/PowerScale cluster and granting necessary privileges to the account used to collect audit data. See the following topics for additional information:
  - [Configure Dell Isilon/PowerScale Cluster in Normal or Enterprise Mode via Shell Script](/docs/auditor/auditor/configuration/fileservers/dellisilon/normal.md#configure-dell-isilonpowerscale-cluster-in-normal-or-enterprise-mode-via-shell-script)
  - [Configure Dell Isilon/PowerScale Cluster in Compliance Mode Via Shell Script](/docs/auditor/auditor/configuration/fileservers/dellisilon/compliance.md#configure-dell-isilonpowerscale-cluster-in-compliance-mode-via-shell-script)
- Manual configuration: you can grant all the necessary permissions to data collecting account manually. See the following topics for additional information:
  - [Configure Dell Isilon/PowerScale Cluster in Normal or Enterprise Mode Manually](/docs/auditor/auditor/configuration/fileservers/dellisilon/normal.md#configure-dell-isilonpowerscale-cluster-in-normal-or-enterprise-mode-manually)
  - [Configure Dell Isilon/PowerScale Cluster in Compliance Mode Manually](/docs/auditor/auditor/configuration/fileservers/dellisilon/compliance.md#configure-dell-isilonpowerscale-cluster-in-compliance-mode-manually)

For manual configuration, ensure the account meets the requirements listed below.

On the target server:

__Step 1 –__  The account must be a member of the local Administrators group.

__Step 2 –__ The account requires Read permissions on the audited shared folders.

__Step 3 –__ The account requires Read permissions on the folder where audit events are logged (_/ifs/.ifsvar/audit/_)

__Step 4 –__ To connect to Dell Isilon/PowerScale storage cluster, an account must be assigned a custom role (e.g., _netwrix\_audit_) that has the following privileges:

|  |  |
| --- | --- |
| Platform API (ISI\_PRIV\_LOGIN\_PAPI) | readonly |
| Auth (ISI\_PRIV\_AUTH) | readonly |
| Audit (ISI\_PRIV\_AUDIT) | readonly |
| Backup (ISI\_PRIV\_IFS\_BACKUP) | readonly |

__NOTE:__ If you plan to connect to a cluster that works in the compliance mode, the account must meet additional requirements.

## Configuring Your Dell Isilon/PowerScale Cluster for Auditing

A Dell Isilon/PowerScale cluster can operate in one of the following modes:

- Standard or Normal mode
- Smartlock Enterprise mode
- Smartlock Compliance mode

For your convenience, Netwrix provides a special shell script for configuring an audited Dell Isilon/PowerScale cluster and granting necessary privileges to the account that is used to collect audit data.

To grant the necessary permissions to Isilon/PowerScale data collecting account manually, you need to perform all steps for manual audit configuration, otherwise the product will not function properly.

See the [Normal and Enterprise Modes for Clusters](/docs/auditor/auditor/configuration/fileservers/dellisilon/normal.md) topic for additional information.

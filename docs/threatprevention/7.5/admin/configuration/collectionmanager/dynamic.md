# Dynamic Collections

Certain options in the upper-left corner of the
[Add New Collection Window](listcollections.md#add-new-collection-window) are only enabled for the
following collection categories:

- Domains & Servers – Dynamic Domains & Servers Collection Table Requirements
- Objects – Dynamic Objects Collection Table Requirements
- Perpetrators and Lockdown Perpetrators – Dynamic Perpetrators Collections Table Requirements
- IP Addresses – Dynamic IP Addresses Collection Table Requirements
- Hosts – Dynamic Hosts Collection Table Requirements
- File Paths – Dynamic File Paths Collection Table Requirements

![Options on the Add New Collection window](/img/product_docs/threatprevention/threatprevention/admin/configuration/collectionmanager/addcollectionoptions.webp)

- The _I will provide a list_ option button enables the default setting for a static collection. See
  the [Add New Collection Window](listcollections.md#add-new-collection-window) topic to manually
  add a new collection.
- The _I want a list to come from the database table_ option button enables a dynamic collection.
  Enter the table name in the textbox that appears or select it from the drop-down menu.

The dynamic collection tables can be populated manually or with a third-party product as long as
they meet the table requirements for the intended collection category.

Any policy that has been assigned a dynamic collection uses the current table’s data for the policy
filter, resulting in a dynamic policy.

Any changes to the selected table’s data are recognized by an active policy when the Agent
communicates with the Threat Prevention Enterprise Manager. This may result in a maximum delay of
five minutes between a change in the table and the Agent refresh.

## Dynamic Domains & Servers Collection Table Requirements

When using a dynamic Domains & Servers collection, the table to be referenced must meet the
following requirements:

- Table Location – Must be in the NVMonitorConfig database
- Table Naming Convention – Must have a prefix of ‘dc*domain_server*’
- Table Schema – Must have the following column:

| Column Name      | Column Type     | Column Description                            |
| ---------------- | --------------- | --------------------------------------------- |
| DomainServerName | NVARCHAR (1024) | Name of the domain or server. Cannot be null. |

Example table entry for domain:

ExampleDomain

Example table entry for server:

ExampleServer

**NOTE:** Threat Prevention creates an empty table with the required prefix and schema if the [Table
name] entered does not exist in the NVMonitorConfig database.

## Dynamic Objects Collection Table Requirements

When using a dynamic Object collection, the table to be referenced must meet the following
requirements:

- Table Location – Must be in the NVMonitorConfig database
- Table Naming Convention – Must have a prefix of ‘dc*ad_objects*’
- Table Schema – Must have the following column:

| Column Name | Column Type     | Column Description                                                 |
| ----------- | --------------- | ------------------------------------------------------------------ |
| AdObject    | NVARCHAR (1024) | Distinguished name of the Active Directory object. Cannot be null. |

Example table entry:

CN=User,DC=Domain,DC=Local

**NOTE:** Threat Prevention creates an empty table with the required prefix and schema if the [Table
name] entered does not exist in the NVMonitorConfig database.

## Dynamic Perpetrators Collections Table Requirements

When using a dynamic Perpetrators or Lockdown Perpetrators collection, the table to be referenced
must meet the following requirements:

- Table Location – Must be in the NVMonitorConfig database
- Table Naming Convention – Must have a prefix of ‘dc*perpetrators*’
- Table Schema – Must have the following columns:

| Column Name    | Column Type     | Column Description                                                                                                                                                                 |
| -------------- | --------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| AccountName    | NVARCHAR (1024) | Distinguished name of the account. Cannot be null.                                                                                                                                 |
| AccountSid     | NVARCHAR (184)  | SDDL form of the account Security ID. Cannot be null.                                                                                                                              |
| AccountType    | INT             | Account type using the following values: - 0 = none - 1 = user - 2 = group - 3 = context - 4 = orgRole - 5 = sidtype - 6 = other - 7 = dynamic - 8 = dynamic_group Cannot be null. |
| IncludeSubtree | INT             | Indicates if child containers should be used: - 0 = Child containers NOT included - 1 = Child containers included Cannot be null.                                                  |

Example table entry:

CN=User,DC=Domain,DC=Local | S-1-5-21-1004336348-1177238915-682003330-500 | 3 | 0

**NOTE:** Threat Prevention creates an empty table with the required prefix and schema if the [Table
name] entered does not exist in the NVMonitorConfig database.

## Dynamic IP Addresses Collection Table Requirements

When using a dynamic IP Addresses collection, the table to be referenced must meet the following
requirements:

- Table Location – Must be in the NVMonitorConfig database
- Table Naming Convention – Must have a prefix of 'dc*ip_addresses*'
- Table Schema – Must have the following column:

| Column Name | Column Type     | Column Description                   |
| ----------- | --------------- | ------------------------------------ |
| IpAddress   | NVARCHAR (1024) | Address of the host. Cannot be null. |

Example table entry:

192.168.1.3

**NOTE:** Threat Prevention creates an empty table with the required prefix and schema if the [Table
name] entered does not exist in the NVMonitorConfig database.

## Dynamic Hosts Collection Table Requirements

When using a dynamic Hosts collection, the table to be referenced must meet the following
requirements:

- Table Location – Must be in the NVMonitorConfig database
- Table Naming Convention – Must have a prefix of ‘dc*hosts*’
- Table Schema – Must have the following columns:

| Column Name     | Column Type     | Column Description                        |
| --------------- | --------------- | ----------------------------------------- |
| NetbiosHostName | NVARCHAR (1024) | Name of the host                          |
| DnsHostName     | NVARCHAR (1024) | Domain Name System (DNS) name of the host |
| IpAddress       | NVARCHAR (1024) | IP v4 Address of the host                 |
| IpV6Address     | NVARCHAR (1024) | IP v6 Address of the host                 |

\*\*At least one column cannot be null.

Example table entry with all fields populated:

host | host.dc.com | 10.0.10.19 | fe80::4d72:80e9:72cf:425f%10

Example table entry tjat excludes IP v6 Address:

host | host.dc.com | 10.0.10.19 | [null]

Example table entry that excludes IP v4 Address:

host | host.dc.com | [null]  | fe80::4d72:80e9:72cf:425f%10

**NOTE:** Threat Prevention creates an empty table with the required prefix and schema if the [Table
name] entered does not exist in the NVMonitorConfig database.

## Dynamic File Paths Collection Table Requirements

When using a dynamic File Paths collection, the table to be referenced must meet the following
requirements:

- Table Location – Must be in the NVMonitorConfig database
- Table Naming Convention – Must have a prefix of 'dc*file_path*'
- Table Schema – Must have the following columns:

| Column Name    | Column Type     | Column Description                                                                   |
| -------------- | --------------- | ------------------------------------------------------------------------------------ |
| Path           | NVARCHAR (1024) | File path to the desired folder. Cannot be null.                                     |
| IncludeSubtree | INT             | Indicates whether or not subfolders are processed: - 0 = Not Included - 1 = Included |
| TargetAgent    | NVARCHAR (1024) | Agent that monitors the target server. Cannot be null.                               |

Example table entry:

c:\Windows | 0 | ExampleFSserver

**NOTE:** Threat Prevention creates an empty table with the required prefix and schema if the [Table
name] entered does not exist in the NVMonitorConfig database.

Two tables are created during the installation/upgrade process for the File Path collections:

- Folders with Sensitive Data Collection – dc_file_path_SensitiveDataFolders table
- Open Shares Collection – dc_file_path_OpenShares table

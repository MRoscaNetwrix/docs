title: SQL Server Requirements
sidebar_label: SQL Server
description: Database server requirements and supported SQL Server versions for Recovery for Active Directory including Windows operating system support.

# SQL Server Requirements

The Windows server can be physical or virtual. The following Windows server operating systems are
supported:

- Windows Server 2022
- Windows Server 2019
- Windows Server 2016
- Windows Server 2012 R2
- Windows Server 2012

The server requirements for the SQL Server databases are:

- SQL Server 2022
- SQL Server 2019
- SQL Server 2017
- SQL Server 2016
- SQL Server 2014
- SQL Server 2012

RAM, CPU, and Disk Space

These depend on the size of the target environment.

| Environment | Large                          | Medium                    | Small                  |
| ----------- | ------------------------------ | ------------------------- | ---------------------- |
| Definition  | 15,000 - 1 million+ AD objects | 2,000 - 15,000 AD objects | Up to 2,000 AD objects |
| RAM         | 64+ GB                         | 32 GB                     | 16 GB                  |
| Cores       | 4+ CPU                         | 4 CPU                     | 2 CPU                  |
| Disk Space  | 256 GB                         | 64 GB                     | 16 GB                  |

Additional Server Requirements

The following are additional requirements for the SQL Server:

- All SQL Server databases configured to use ‘Simple Recovery Model’

Database Permissions

The following permissions are required on the databases for the accounts used to run Recovery for
Active Directory:

- Create a database
- Create Tables
- Read/Write

Additional Considerations

The following additional considerations are recommended for the SQL Server:

- Microsoft SQL Server supports TLS 1.2, which requires the Recovery for Active Directory server to
  have either SQL Server Native Client 11 or Microsoft Ole DB 18 installed.
- _Optional_: SQL Server Management Studio installed on the Recovery for Active Directory server

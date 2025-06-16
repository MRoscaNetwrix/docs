# Firewall Rules for Forest Server Backups

The following firewall settings are required for communicating with Recovery for Active Directory
and the domain controller when executing a domain controller backup. The firewall rules must be
configured on both the domain controller and the application server.

| Communication Direction                 | Protocol | Ports | Description            |
| --------------------------------------- | -------- | ----- | ---------------------- |
| Domain Controller to Application Server | TCP      | 9001  | Outbound Communication |
| Application Server to Domain Controller | TCP      | 9001  | Inbound Communication  |

**NOTE:** 9001 is the default port. If a different port is specified on the Netwrix Recovery Server
Configuration page of the Recovery for Active Directory Setup wizard while installing the
application, then that specific port is applicable here.

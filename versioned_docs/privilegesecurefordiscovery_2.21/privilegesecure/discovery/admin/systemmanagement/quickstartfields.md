# Quickstart Fields Demystified

Quickstart Fields Demystified

# Quickstart Fields Demystified

The following tables provide details and explanations of the Quickstart report fields.

## Admin List Sheet

| Sheet Field | QS Field Type | Description | Privilege Secure or LDAP/AD Attribute | DB 'ldap\_store' Computer Document Feild |
| --- | --- | --- | --- | --- |
| is | Pulled/Downloaded data | Identifier for the user. | Privilege Secure | \_id |
| system | Pulled/Downloaded data | Computer system attribute returned from LDAP/AD | LDAP/AD | cn |
| domain | Pulled/Downloaded data | Account's NetBIOS name | LDAP/AD | admins.current.domain |
| user | Pulled/Downloaded data | Username of account (AD sAMAccountName attribute) | LDAP/AD | admins.current.user |
| sid | Pulled/Downloaded data | SID identifier of the account | LDAP/AD | admins.current.sid |
| type | Pulled/Downloaded data | Defining the type of account; 2=Group, 1=User | LDAP/AD | admins.current.sidusage |
| local | Pulled/Downloaded data | True/False to an local computer account.  True when the computer's cn equals the admin's domain. | n/a | n/a |
| onHost | Pulled/Downloaded data | True/False flag if the account is in the local administrators group on the computer. | Privilege Secure | admins.current.onHost |
| persistent | Pulled/Downloaded data | True/False flag if the account is marked as persistent. Persistent accounts will not be removed from the local administrators group. | Privilege Secure | admins.current.persistent |
| default\_admin | Pulled/Downloaded data | Exists and is True if the account is the built-in admin account on a Windows endpoint (e.g. Administrator). If Privilege Secure has managed this account, the current and previous passwords can be retrieved using the Computer Local Account Password API. | Privilege Secure | admins.current.default\_admin |
| inserted\_ts | Pulled/Downloaded data | Timestamp when the record was created in the Privilege Secure database. | Privilege Secure | admins.current.inserted\_ts |
| Intentionally Blank | -- | Intentionally left blank. | -- | -- |
| Filtered | Pulled/Downloaded data | TRUE indicates a Windows Server OS found in AD.  FALSE indicates a Window OS without 'server' in the OS name found in AD. | Privilege Secure |  |
| Persistent | Change to push/upload | True/False flag to set administrator persistence on computer:  True = persistent; False = non-persistent | Privilege Secure | admins.current.persistent |
| Delete from Inventory | Change to push/upload | True flag to delete this administrator from the computer's Administor Accounts inventory. | Privilege Secure | admins.current.<admin in array> |

## Computer Data Sheet

| Sheet Field | QS Field Type | Description | Privilege Secure or LDAP/AD Attribute | DB Field in 'ldap\_store' Collection |
| --- | --- | --- | --- | --- |
| id | Pulled/Downloaded data | Identifier for the computer | Privilege Secure | \_id |
| cn | Pulled/Downloaded data | Computer cn attribute returned from LDAP/AD | LDAP/AD | cn |
| domain\_fqdn | Pulled/Downloaded data | Computer's domain FQDN returned from LDAP/AD | LDAP/AD | domain\_fqdn |
| distinguishedName | Pulled/Downloaded data | Computer distinguishedName attribute returned from LDAP/AD | LDAP/AD | distinguishedName |
| OU | Pulled/Downloaded data | OU derived from distinguishedName returned from LDAP/AD | Privilege Secure | n/a |
| operatingSystem | Pulled/Downloaded data | Computer operatingSystem attribute returned from LDAP/AD | LDAP/AD | operatingSystem |
| lastLogonTimestamp | Pulled/Downloaded data | Computer lastLogonTimestamp attribute returned from LDAP/AD | LDAP/AD | lastLogonTimestamp |
| last\_scanned | Pulled/Downloaded data | Details about the last scan attempt by Privilege Secure | Privilege Secure | last\_scanned |
| prev\_scan\_success | Pulled/Downloaded data | Timestamp when the computer was last successfully scanned | Privilege Secure | lastScan.success |
| prev\_scan\_msg | Pulled/Downloaded data | Message from the last scan attempt by Privilege Secure | Privilege Secure | lastScan.msg |
| Scanned in last 2 weeks | Pulled/Downloaded data | True/False flag that indicates that the computer was scanned in the last 2 weeks, based off last\_scanned field date. | Privilege Secure | n/a |
| protect\_mode | Pulled/Downloaded data | Indicates computer's Protect Mode setting:  JITA, DENY, or FALSE (disabled) | Privilege Secure | policy .secure |
| scan\_mode | Pulled/Downloaded data | True/False flag that indicates if the computer is included in active permission scans. | Privilege Secure | policy.scan |
| directory\_bridging\_strategy | Pulled/Downloaded data | Indicates directory bridging provider set for Linux computer. |  |  |
| edr\_integration | Pulled/Downloaded data | Indicates if Privilege Secure EDR (Endpoint Detection and Response) integration is enabled for computer. | Privilege Secure | config.edr\_integration.enabled |
| registered | Pulled/Downloaded data | Mac registered system |  |  |
| <QuickStart provisionUser> | Pulled/Downloaded data | True/False flag that indicates if the provisionUser specificed in the QuickStart script is on a computer. | Privilege Secure | n/a |
| Intentionally Blank | -- | Intentionally left blank. | -- | -- |
| Filtered | Pulled/Downloaded data | TRUE indicates a Windows Server OS found in AD.  FALSE indicates a Window OS without 'server' in the OS name found in AD. |  |  |
| OAM (Offline Access Management) Enabled | Pulled/Downloaded data | True/False flag that indicates if OAM is managed on computer. |  | config.policies.offline\_access\_management.enabled |
| OAM Strategy | Pulled/Downloaded data | Indicates current OAM strategy set for computer | Privilege Secure | config.policies.offline\_access\_management.strategy |
| OAM Name Template | Pulled/Downloaded data | Currenlty set name template for OAM alternate administrator account. Wildcards expressed by question marks (?).  Default value is S1\_ALT\_ADMIN. | Privilege Secure | config.policies.offline\_access\_management.break\_glass\_account\_name\_template |
| OAM JITA User Can Access PW | Pulled/Downloaded data | True/False flag that indicates Privilege Secure application “User” role members with JITA or persistent access to systems to access OAM passwords. | Privilege Secure | config.policies.offline\_access\_management.jita\_or\_persistent\_users\_can\_access\_passwords |
| OAM Use Alt Admin | Pulled/Downloaded data | True/False flag that indicates if Privilege Secure is to create and use an Alternate Admin account, named according to the OAM Name Template. | Privilege Secure | config.policies.offline\_access\_management.use\_alternate\_admin |
| OAM Manage Built-in PW | Pulled/Downloaded data | True/False flag indicating if Privilege Secure is managing the computer's built-in local administrator (RID 500) account password. | Privilege Secure | config.policies.offline\_access\_management.manage\_built\_in\_admin\_password |
| OAM Disable Built-in Admin | Pulled/Downloaded data | True/False flag that indicates if Privilege Secure will disable computer's built-in local administrator account (RID 500). | Privilege Secure | config.policies.offline\_access\_management.disable\_built\_in\_admin |
| Enable Protect | Change to push/upload | Set computer's Protect Mode:  JITA, DENY, or FLASE (disabled) | Privilege Secure | policy .secure |
| Enable Scan | Change to push/upload | True/False flag setting indicates if the computer is included in active permission scans. | Privilege Secure | policy.scan |
| Enable EDR Integration | Change to push/upload | True/False flag  setting Privilege Secure EDR (Endpoint Detection and Response) integration:  True = enabled; False = disabled | Privilege Secure | config.edr\_integration.enabled |
| Provision Account | Change to push/upload | DOMAIN\sAMAccountName.  Comma delimited.  To persist add ;true after sAMAccountName (still comma delimited). | Privilege Secure |  |
| Set OAM Enabled | Change to push/upload | True/False flag setting Privilege Secure OAM managment of computer:  True = enabled; False = disabled If set to false with no other parameters, then other OAM existing values will be left as-is, and only the enabled field will be set accordingly. | Privilege Secure | config.policies.offline\_access\_management.enabled |
| Set OAM Strategy | Change to push/upload | Set OAM strategy.  May be entered with any of following case-insensitive values:  OS-BEST-PRACTICE MANAGED-BUILT-IN CUSTOM If left blank it will default to the current value, or to OS-BEST-PRACTICE if no previous policy was set. | Privilege Secure | config.policies.offline\_access\_management.strategy |
| Set OAM Name Template | Change to push/upload | Name template for OAM alternate administrator account. Accepts a string with wildcards expressed by question marks (?) ex: MY\_ADMIN\_???. If left blank it will default to the current value, or to S1\_ALT\_ADMIN. | Privilege Secure | config.policies.offline\_access\_management.break\_glass\_account\_name\_template |
| Set OAM JITA User Can Access PW | Change to push/upload | True/False flag setting Privilege Secure “Users” with JITA/persistent access to systems access OAM passwords:  True = access; False = no access | Privilege Secure | config.policies.offline\_access\_management.jita\_or\_persistent\_users\_can\_access\_passwords |
| Set OAM Use Alt Admin | Change to push/upload | True/False flag setting creation and use of an Alternate Administrator account, named according to the OAM Name Template:  True = create/use; False = Do not create/use | Privilege Secure | config.policies.offline\_access\_management.use\_alternate\_admin |
| Set OAM Manage Built-in PW | Change to push/upload | True/False flag setting management of built-in local administrator (RID 500) account password:  True = manage; False = do not manage | Privilege Secure | config.policies.offline\_access\_management.manage\_built\_in\_admin\_password |
| Set OAM Disable Built-in Admin | Change to push/upload | True/False flag setting if Privilege Secure is to disable computer's built-in local administrator account (RID 500):  True = disable; False = do not disable | Privilege Secure | config.policies.offline\_access\_management.disable\_built\_in\_admin |
| Set Directory Bridging Strategy | Change to push/upload | Set directory bridging provider for Linux computer:  privilegesecure, centrify, powerbroker | Privilege Secure | config.directory\_bridging.strategy |
| Set Directory Bridging Domain | Change to push/upload | Set domain for bridging provider for Linux computer if not set to Privilege Secure. | Privilege Secure | domain\_fqdn |
| Set Sudoers Representation | Change to push/upload | Insert sudoers ID from a computer to replicated that sudoers file to other computer(s) | Privilege Secure | staged\_sudoers\_history.sudoers\_hash |

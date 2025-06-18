# Active Directory Threats

The following threats are monitored for Active Directory:

## AdminSDHolder ACL Tampering

| AdminSDHolder ACL Tampering |                                                                                                                                                                                                                                                                                                             |
| --------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Definition                  | Modifying the Access Control List (ACL) of the AdminSDHolder container in Active Directory enables an attacker to achieve and maintain persistence in an already compromised domain, even if an administrator finds and removes the attacker's permission on a protected object the AdminSDHolder controls. |

## AS-REP Roasted Users

| AS-REP Roasted Users |                                                                                                                                                                                                     |
| -------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Definition**       | AS-REP roasting is a technique that allows retrieving password hashes for users that have 'Do not require Kerberos pre-authentication' property selected. Those hashes can then be cracked offline. |

## DCShadow

| DCShadow   |                                                                                                                                                                                                                                             |
| ---------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Definition | DCShadow is a feature of Mimikatz and a technique for elevating a regular workstation account to a domain controller and executing malicious replication against the domain. DCShadow can set arbitrary attributes within Active Directory. |

## DC Sync

| DC Sync    |                                                                                                                                                                                                              |
| ---------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| Definition | Replication from a non-domain controller account can be evidence of a Mimikatz DCSync attack. Performing a DCSync remotely extracts the NTLM password hash for the account that is the target of the attack. |

**NOTE:** The domain monitoring policy must be configured to exclude domain controllers. See the
[Integration with Other Netwrix Products](/docs/threatmanager/3.0/threatmanager/install/integration/overview.md) topic for additional
information.

## Domain Backup Key Compromise

| Domain Backup Key Compromise |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| ---------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Definition                   | The Data Protection API (DPAPI) is used by Windows to encrypt user secrets such as saved credentials, browser cookies, website passwords, and other sensitive information. For computers joined to an Active Directory domain, secrets protected by the DPAPI are also encrypted with a domain backup key. This key is stored in Active Directory and enables recovery of DPAPI-protected secrets should the user lose their own backup key. Because the domain backup key cannot be rotated, its exposure is a significant event. |

## Exposed Administrative Credentials

| Exposed Administrative Credentials |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| ---------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Definition                         | Highly privileged accounts, groups, and systems have direct or indirect administrative control over the Active Directory forest/domain. Given the sensitive nature of these accounts, they should only be used on domain controllers. Pass-the-Hash attacks are successful because highly privileged credentials are used to access lower security systems. Having access to a privileged user's hash allows attackers to move laterally. This threat aligns to best practices for securing Active Directory. If an organization does not enforce limiting privileged account access to only Domain Controllers, this threat should remain disabled to eliminate noise. |

## Golden Ticket

| Golden Ticket |                                                                                                                                                                                                                                                                                             |
| ------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Definition    | By obtaining the password hash for the most powerful service account in Active Directory, the KRBTGT account, an attacker is able to compromise every account within Active Directory, giving them unlimited and virtually undetectable access to any system connected to Active Directory. |

## Forged Ticket

| Forged Ticket |                                                                                                                                                                                                                                                                                                                                                               |
| ------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Definition    | Forged Tickets provide a way for an attacker to elevate privileges by injecting additional group membership into their Kerberos tickets, giving them more privileges than they actually have in Active Directory. Threat Manager will compare PAC data in authentication to the user's actual group member and generate a threat when it finds a discrepancy. |
| Trigger       | Perform Authentication using fabricated/invalid tickets with groups present in the authentication Ticket PAC data that does not match the users Active Directory group membership.                                                                                                                                                                            |

## GMSA Password Access

| GMSA Password Access |                                                                                                                                                                                                                                                                                                                                                                                    |
| -------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Definition           | The passwords for Group Managed Service Accounts (GMSA) are stored in BLOB format in the msDS-ManagedPassword attribute of the GMSA account object in Active Directory. It is trivial to convert the BLOB to a useable clear text password. It is suspicious for a user to attempt to read this attribute, as only authorized computer accounts should retrieve a GMSA’s password. |

## GMSA Permissions Assignment

| GMSA Permissions Assignment |                                                                                                                                                                                                                                                                                                                               |
| --------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Definition                  | Permissions to retrieve passwords for Group Managed Service Accounts (GMSA) are typically granted only to the computer account of each computer running the service. The assignment of privileges to non-computer accounts (e.g. human accounts) can be indicative of an adversary's attempt to compromise the GMSA password. |

## Hidden Object

| Hidden Object |                                                                                                                                                                                                                                                                                                   |
| ------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Definition    | Changing object Deny Read or Deny List Contents permissions can effectively hide an Active Directory object as it will not be returned in LDAP queries. This causes the object to avoid monitoring and detection, as service accounts used by these solutions will be unable to query the object. |

## Honeytoken

| Honeytoken |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| ---------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| Definition | Honeytokens are fake credentials stored in memory. When an attack scans memory they may try to authenticate or query the domain for information about the account. A Honeytoken threat can be generated by two methods: LDAP or Authentication. An authentication Honeytoken threat is generated when a perpetrator attempts to authenticate with a Honeytoken user account. An LDAP Honeytoken threat is generated when a perpetrator performs an LDAP query against a Honeytoken user account. |

## Insecure UAC Change

| Insecure UAC Change |                                                                                                                                                                                                                                 |
| ------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Definition          | Some changes to User Account Control Flags on Active Directory Objects can potentially expose security risks."PASSWD_CANT_CHANGE", "TRUSTED_FOR_DELEGATION", "USE_DES_KEY_ONLY", and "DONT_REQ_PREAUTH" are particularly risky. |

## Kerberoasting

| Kerberoasting |                                                                                                                                                                 |
| ------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Definition    | Kerberoasting is an attack method that allows an attacker to crack the passwords of service accounts in Active Directory offline and without fear of detection. |

## LDAP Reconnaissance

| LDAP Reconnaissance |                                                                                                                                                                                                                                                                                                                                                                                           |
| ------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Definition          | When an attacker initially compromises a system on a network, they will have few to no privileges within the domain. However, due to the architecture of Active Directory, once an attacker has infiltrated any domain-joined computer, they are able to query the directory and its objects using LDAP, allowing them to locate sensitive accounts and assets to target in their attack. |

## LSASS Process Injection

| LSASS Process Injection |                                                                                                                                                                                                                                                                            |
| ----------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Definition              | LSASS process injection is a deliberate and common method used by a variety of attacks including: Skeleton Key, MemSSP, and SID History Tampering. By injecting code into the lsass.exe process an attacker can scrape the password hashes directly out of process memory. |

## Pass-The-Ticket

| Pass-The-Ticket |                                                                                                                                                                                                                                                  |
| --------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| Definition      | A Pass-the-Ticket event occurs when a user extracts a valid Kerberos ticket from one system and uses it to authenticate from another system. This allows the attacker to compromise a user's account and use it from any domain-joined computer. |

## Password Spraying

| Password Spraying |                                                                                                                                                                                                        |
| ----------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| Definition        | Password Spraying indicates an attempt to gain access to credentials by using common passwords against large numbers of accounts while also staying below an organization’s defined lockout threshold. |

## Replication Permissions

| Replication Permissions |                                                                                                                                                                                                    |
| ----------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Definition              | Providing a user with replication permissions allows the user to execute domain replication commands against domain controllers. This type of behavior is common with DCSync and DCShadow threats. |

## Sensitive Group Changes

| Sensitive Group Changes |                                                                                                                                                                                                                                                                                                                                     |
| ----------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Definition              | Sensitive Group Changes indicate that the membership of a group containing extremely sensitive permissions has been modified. This includes any Active Directory group with the Sensitive tag in Threat Manager, which includes many standard Active Directory Groups such as: Domain Admins, Enterprise Admins, and Schema Admins. |

## Service Account Misuse

| Service Account Misuse |                                                                                                                                                                                                                                                                                                                                                                                        |
| ---------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Definition             | Indicates that a service account was used to log into a machine that is not listed in their service principal names attribute. This threat aligns to best practices for securing Active Directory. If an organization does not enforce service accounts to only authenticate to hosts within their servicePrincipalName values, this threat should remain disabled to eliminate noise. |

## SID History Tampering

| SID History Tampering |                                                                                                                                                                                                                           |
| --------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Definition            | Mimikatz or other tools can be used to inject SID History into user accounts. This allows an account to effectively be given permissions, such as Domain Admin, even though it is not actually a member of Domain Admins. |

## SPN Assigned to Privileged User

| SPN Assigned to Privileged User |                                                                                                                                                                                                                                                                                           |
| ------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Definition**                  | An account is only vulnerable to Kerberoasting attacks if it has a service principal name. Service accounts should not have more privileges than required to perform their function. Visit [Netwrix Attack Catalog](https://www.netwrix.com/attack.html) to learn more about this threat. |

## Zerologon Exploitation

| Zerologon Exploitation |                                                                                                                                                                                                                                                                                                                                                                                  |
| ---------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Definition             | CVE-2020-1472 (a.k.a. "Zerologon") is an elevation of privilege vulnerability that allows an unauthenticated attacker to escalate their privileges to domain administrator by exploiting a flaw in the Netlogon Remote Protocol (MS-NRPC). To exploit this vulnerability, an attacker requires only the ability to communicate over the MS-NRPC protocol to a domain controller. |

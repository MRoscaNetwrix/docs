# Active Directory

Threat Prevention for Active Directory is a real-time change and access monitoring solution designed to detect, block, and alert on unauthorized or high-risk activity within Active Directory environments - without relying on native Windows logging mechanisms. It captures and inspects all authentication, access, and modification activity at the domain controller level, providing full visibility into changes across individual Active Directory objects, attributes, group memberships, and Group Policy Objects (GPOs). All actions are recorded in a detailed audit trail that includes pre- and post-change values with actor context.

Key aspects of the Active Directory solution are:

- Proactive Enforcement — Blocks unauthorized or policy-violating changes (for example, group membership or GPO edits) before they are applied, strengthening native Active Directory controls
- Real-Time Authentication Monitoring — Captures and logs all authentication requests, including Kerberos and NTLM logons, providing visibility into authentication events across the environment
- Granular Change Monitoring — Provides detailed monitoring of all changes within Active Directory, including object-level modifications, access permissions, and group memberships, ensuring complete visibility into any action that could impact security or compliance
- Customizable Security Policies — Allows administrators to define custom rules for blocking and alerting on specific types of changes or access attempts, offering tailored security enforcement based on organizational needs

Some important events Threat Prevention captures are:

- Changes
- Account Lockouts
- Password Resets
- Comprised and Weak Password Use
- Group Policy Object (GPO) Modifications
- Object Moves/Adds/Deletes
- Permission Modifications
- Groups Membership
- DNS Changes
- LSASS Modifications
- AD Replication
- Replication Impersonations
- Active Directory Read Monitoring
- Authentication (Kerberos & NTLM)

  - Authentication-based Attacks (e.g. Horizontal/Lateral Movement, Brute Force Attacks, User Account Hacking, Breached Passwords, Golden Tickets, and more)
  - Privileged Account Authentications

## Active Directory Event Types

The following event types are available for Active Directory:

- [Active Directory Changes Event Type](/docs/threatprevention/threatprevention/admin/policies/eventtype/activedirectorychanges.md)
- [Active Directory Lockdown Event Type](/docs/threatprevention/threatprevention/admin/policies/eventtype/activedirectorylockdown.md)
- [Active Directory Read Monitoring Event Type](/docs/threatprevention/threatprevention/admin/policies/eventtype/activedirectoryreadmonitoring.md)
- [AD Replication Lockdown Event Type](/docs/threatprevention/threatprevention/admin/policies/eventtype/adreplicationlockdown.md)
- [AD Replication Monitoring Event Type](/docs/threatprevention/threatprevention/admin/policies/eventtype/adreplicationmonitoring.md)
- [Authentication Lockdown Event Type](/docs/threatprevention/threatprevention/admin/policies/eventtype/authenticationlockdown.md)
- [Authentication Monitoring Event Type](/docs/threatprevention/threatprevention/admin/policies/eventtype/authenticationmonitoring.md)
- [Effective Group Membership Event Type](/docs/threatprevention/threatprevention/admin/policies/eventtype/effectivegroupmembership.md)
- [FSMO Role Monitoring Event Type](/docs/threatprevention/threatprevention/admin/policies/eventtype/fsmorolemonitoring.md)
- [GPO Setting Changes Event Type](/docs/threatprevention/threatprevention/admin/policies/eventtype/gposettingchanges.md)
- [GPO Setting Lockdown Event Type](/docs/threatprevention/threatprevention/admin/policies/eventtype/gposettinglockdown.md)
- [LSASS Guardian – Monitor Event Type](/docs/threatprevention/threatprevention/admin/policies/eventtype/lsassguardianmonitor.md)
- [LSASS Guardian – Protect Event Type](/docs/threatprevention/threatprevention/admin/policies/eventtype/lsassguardianprotect.md)
- [Password Enforcement Event Type](/docs/threatprevention/threatprevention/admin/policies/eventtype/passwordenforcement.md)

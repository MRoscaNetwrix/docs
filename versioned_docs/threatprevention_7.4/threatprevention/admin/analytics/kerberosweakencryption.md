# Kerberos Weak Encryption Analytic Type

The __Kerberos Weak Encryption__ analytic type identifies Kerberos tickets with RC4\_HMAC\_MD5 encryption by detecting the use of weak encryption. Various attack methods utilize weak Kerberos encryption cyphers, including Overpass-the-Hash.

| Kerberos Weak Encryption |  |
| --- | --- |
| Definition | Kerberos tickets with RC4\_HMAC\_MD5 encryption. |
| Example | Kerberos tickets are used as a sort of “pass card” to obtain access to resources. Once a domain controller authenticates a user, a TGT (ticket granting ticket) is granted with a limited lifespan. This is then used to obtain TGS (ticket granting service) and the TGS is what identifies a user to a resource on the network.  If RC4\_HMAC\_MD5 encryption is used then it makes possible to obtain password value using Kerberoasting attack. If a user on the network were to attempt to use such a ticket, this analytic would detect this ticket and generate an alert. |
| Trigger | Ticket uses RC4\_HMAC\_MD5 encryption. |
| Recommended Settings | No additional configuration is needed |

Analytic Workflow

1. Configure the analytic policy
2. Enable the analytic policy
3. Enable alerting on incidents through the [System Alerting Window](/versioned_docs/threatprevention_7.4/threatprevention/admin/configuration/systemalerting/overview.md).

See the [Kerberos Weak Encryption Analytic Data Grid](#kerberos-weak-encryption-analytic-data-grid) topic for information on event data collected per incident.

## Configure Kerberos Weak Encryption Analytic Policy

Open the Kerberos Weak Encryption Policy in any of the following ways:

- Click Analytics in the left pane to launch the Analytics interface. Then click the gear icon for the analytic.
- Expand the Analytics node and click the desired analytic. On the analytic window, click the gear icon available in the top right corner.

The Configure Analytics window has one tab:

- Policy – Where filters can be added, additional actions configured, a custom schedule set, and the policy enabled

Policy Tab

![Kerberos Weak Encryption Analytic Type - Policy tab](/img/versioned_docs/threatprevention_7.4/threatprevention/admin/analytics/policytab.png)

The __Policy__ tab for configuring analytics consists of three sub-tabs:

- General tab – Configured the same way a regular policy’s [General Tab](/versioned_docs/threatprevention_7.4/threatprevention/admin/policies/general.md) is configured. The only exception is that the Name and Description are hard coded, and cannot be modified. The Tags field is disabled for analytics.
- Event Type tab – Configured the same way a regular policy’s [Event Type Tab](/versioned_docs/threatprevention_7.4/threatprevention/admin/policies/eventtype/overview.md) is configured. The only exception is that the [Authentication Monitoring Event Type](/versioned_docs/threatprevention_7.4/threatprevention/admin/policies/eventtype/authenticationmonitoring.md) is hard coded, and the Success filter cannot be modified.

  - Scope the servers to be included in or excluded from monitoring on the IP Addresses (from) filter, the IP Addresses (to) filter, the Hosts (from) filter, or the Hosts (to) filter.

    __NOTE:__ Some authentication events may return only a host name (NetBIOS or FQDN), others may return only an IP address. It is recommended to take this into account when entering filter values.
  - _Alternatively:_ Scope the domains to be included in or excluded from monitoring on the Domains/Servers filter.
  - _Optional:_Scope the protocol to be monitored on the Authentication Protocol filter. If enabling the analytic on a domain controller, also scope the login type. The Authentication Protocol filter is hard coded to ensure the Kerberos protocol is monitored.

    __NOTE:__ The Exclude failed authentications with ‘N-2’ passwords option requires a GPO within the organization be configured to ‘Enforce password history’ with a setting of a minimum of ‘3 passwords remembered’ or it will not have an effect.
  - _Optional_ – Scope the accounts to include in or exclude from being monitored on the AD Perpetrator filter.
- Actions tab – Configured the same way a regular policy’s [Actions Tab](/versioned_docs/threatprevention_7.4/threatprevention/admin/policies/actions/overview.md) is configured. The only exceptions are that the “Send to Event DB” and “Email Notifications” options are disabled. The event data collected by analytic policies are stored in memory until an incident is triggered. For the “Send Raw Data to SIEM” option, use _caution_, as this will send all event data not the triggered incident, which could be a large volume of data. To send notifications on incidents, use the [System Alerting Window](/versioned_docs/threatprevention_7.4/threatprevention/admin/configuration/systemalerting/overview.md) to configure Email and SIEM alerts.

## Kerberos Weak Encryption Analytic Data Grid

The data grid on the __Kerberos Weak Encryption__ node lists one row per incident identified.

![kerberosweakencryption](/img/versioned_docs/threatprevention_7.4/threatprevention/admin/analytics/kerberosweakencryption.png)

The data grid can be filtered according to the Event Tracker status: All, New, or Reviewed. See the [Event Tracker Window](/versioned_docs/threatprevention_7.4/threatprevention/admin/policies/recentevents/eventtracker.md) topic for additional information.

The top data grid includes the following information for each incident:

- From Host – Name of the originating host
- From Host IP Address – IP address of the originating host
- To Host – Name of the target host
- To Host IP Address – IP address of the target host
- Account Name – Security principal of the account that triggered the incident
- Account SID – Security Identifier of the account used in the event
- Access Type – Type of authentication with encryption, e.g. TGS: cifs/ enc:23/18, TGS: krbtgt/ enc: 23/18, etc.
- SPN – The service principal name (SPN) included in the Kerberos ticket data
- Status – Indication of whether the authentication was successful
- Date/Time – Date timestamp of the monitored event. Hover over the data in this column to view the local time (of the Enterprise Manager) and UTC time simultaneously.
- Detected on DC – Fully-qualified name of the domain controller that detected the event
- Encryption Type – Type of encryption identified as weak that triggered the incident
- Agent Time Logged – Timestamp for when the Agent detected the event. This can be different from the Enterprise Manager time (displayed in the Date/Time column) due to latency.

This data grid employs features for sorting, filtering, searching, and more. See the [ Data Grid Functionality](/versioned_docs/threatprevention_7.4/threatprevention/admin/navigation/datagrid.md) topic for additional information.

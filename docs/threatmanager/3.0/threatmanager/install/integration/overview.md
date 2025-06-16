# Integration with Other Netwrix Products

The following Netwrix products can be configured to send data to Threat Manager:

- [Netwrix Activity Monitor Integration](activitymonitor.md) – Activity Monitor can be configured to
  send file system data and/or Active Directory data to Threat Manager.
    - The Active Directory data stream requires a unique App Token to be generated within Threat
      Manager.
- [Netwrix Threat Prevention Integration](threatprevention.md) – Threat Prevention can be configured
  to send file system data and/or Active Directory data to Threat Manager.
    - Requires a unique App Token to be generated within Threat Manager.
- [Netwrix Access Analyzer (formerly Enterprise Auditor) Integration](enterpriseauditor.md) – Access
  Analyzer, formerly Netwrix StealthAUDIT, can be configured to send File System Sensitive Data to
  Threat Manager
    - Requires a unique App Token to be generated within Threat Manager.

Configure the desired product to feed data into the Threat Manager Console. Depending upon the data
source, a Threat Manager app token may need to be generated. See the
[App Tokens Page](../../administration/configuration/integrations/apptoken.md) topic for additional
information.

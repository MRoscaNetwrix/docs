# Choose Appropriate Execution Scenario

Auditor Add-on for the SIEM solution runs on any computer in your environment. For example, you can run the add-on on the computer where Auditor is installed or on a remote server. Depending on the execution scenario you choose, you have to define a different set of parameters. See the [Define Parameters](/docs/product_docs/auditor/auditor/addon/logrhythm/parameters.md) topic for additional information.

Netwrix suggests the following execution scenarios:

| Scenario | Example |
| --- | --- |
| The add-on runs on theAuditorServer with the current user credentials. Activity Records are exported to a local event log. | C:\Add-ons\Netwrix\_Auditor\_Add-on\_for\_LogRhythm.ps1 |
| The add-on runs on the Auditor Server with explicitly defined credentials. Activity Records are exported to a local event log. | C:\Add-ons\Netwrix\_Auditor\_Add-on\_for\_ LogRhythm.ps1 -NetwrixAuditorUserName enterprise\NAuser -NetwrixAuditorPassword NetwrixIsCool |
| The add-on exports Activity Records from a remote Auditor Server using current user credentials and writes data to a local event log. | C:\Add-ons\Netwrix\_Auditor\_Add-on\_for\_ LogRhythm.ps1-NetwrixAuditorHost 172.28.6.15 |
| The add-on exports Activity Records from a remote Auditor Server using explicitly defined credentials and writes data to a local event log. | C:\Add-ons\Netwrix\_Auditor\_Add-on\_for\_ LogRhythm.ps1-NetwrixAuditorHost 172.28.6.15 -NetwrixAuditorUserName enterprise\NAuser -NetwrixAuditorPassword NetwrixIsCool |

For security reasons, Netwrix recommends running the script with current user credentials (skipping user credentials). Create a special user account with permissions to both Auditor data and event log and use it for running the script.

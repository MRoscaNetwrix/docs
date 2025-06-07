# Configure Cisco Meraki Devices

To configure Cisco Meraki devices, configure the Syslog server for each of your networks.

Netwrix recommends assigning a unique identificator to each Cisco Meraki device; otherwise, the product may count them as a single anonymous device.

Follow the steps to configure the Syslog server.

__Step 1 –__ Sign in to [Cisco Meraki Dashboard](https://account.meraki.com/secure/login/dashboard_login).

__Step 2 –__ Navigate to __Network wide__ > __Configure__ > __General__.

![nand_meraki_network](/static/img/product_docs/auditor/auditor/configuration/networkdevices/nand_meraki_network.png)

__Step 3 –__ Locate the Reporting section and click Add a syslog server.

![nand_meraki_server](/static/img/product_docs/auditor/auditor/configuration/networkdevices/nand_meraki_server.png)

__Step 4 –__ In the dialog that opens, complete the following fields:

| Option | Description |
| --- | --- |
| Server IP | Provide the IP address of the computer that hosts your Netwrix Auditor Server. |
| Port | Provide the port configured in your monitoring plan for Network Devices (514 by default). See the[Network Devices](/docs/product_docs/auditor/auditor/admin/monitoringplans/networkdevices.md) topic for additional information. |
| Roles | Select the following roles:   - Appliance event log - Switch event log - Wireless event log |

### Cisco Meraki Devices Configuration

If you need any additional information about the Cisco Meraki devices configuration, refer to Cisco documentation: [Syslog Server Overview and Configuration](https://documentation.meraki.com/zGeneral_Administration/Monitoring_and_Reporting/Syslog_Server_Overview_and_Configuration).

Review a full list of object types Netwrix Auditor can collect on Cisco Meraki network devices.

| Object type | Actions | Event ID |
| --- | --- | --- |
|---|---|---|
|---|---|---|
| Cisco Meraki |  |  |
| Authentication | - Successful Logon | - 716038 - 113012 - ```client_vpn_connect``` - ```authentication on``` - ```type=8021x_auth``` - ```type=8021x_eap_success``` - ```type=splash_auth``` - ```type=wpa_auth``` |
| - Failed Logon | - 113020 - 113015 - ```type=8021x_eap_failure``` - ```type=disassociation``` |  |
| Session | - Successful Logon | - 716001 - 713228 - 722033 - 722022 - 725001 - 725002 - 725003 |
| - Failed Logon | - 716039 - 722056 - 725006 - 725014 |  |
| - Logoff | - 716002 - 713259 - 302014 - 302304 - 302016 - 722023 - 725007 - 722030 - 722031 - 113019 - ```client_vpn_disconnect``` - ```type=8021x_deauth``` - ```type=8021x_client_deauth``` - ```type=wpa_deauth``` |  |
| Rule | - Activated | - ```ids-alerts``` - ```security_event ids_alerted``` - ```security_event security_filtering_file_scanned``` - ```security_event security_filtering_disposition_change``` - ```type=device_packet_flood``` - ```type=rogue_ssid_detected``` - ```type=ssid_spoofing_detected``` |
| URL | - Read / Failed read | - 716003 - 716004 |

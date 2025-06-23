---
title: Panzura Storage System Monitoring
sidebar_label: Panzura
description: Configure Panzura CloudFS storage system monitoring settings including device configuration and cloud storage activity tracking.
---

# Panzura Tab

The Panzura Tab provides features to configure settings for monitoring Panzura devices.

![Agent Properties - Panzura Tab](/img/product_docs/activitymonitor/activitymonitor/admin/agents/properties/panzuratab.webp)

The available options are:

- Agent server port (TCP) - Enter the agent server port. The default is 4497.
- Users can protect the port with a username and password. The credentials will be configured in
  Panzura

  - User name – Enter a custom user name or click **Generate** to create a random username and
    password
  - Password – Enter a custom password or use the generated password. Click **Copy** to copy the
    user name and password to the clipboard.

- IPv4 or IPv6 allowlist – IP Addresses of the remote hosts, which are allowed to connect to the API
  port, can be whitelisted by entering them in the box. IP Addresses should be entered as separate
  addresses with space, comma (,), semicolon (;), or a multi-line list. Leave the box blank to
  accept connections from any hosts.

Click **OK** to commit the modifications. Click **Cancel** to discard the modifications. The Agent
Properties window closes.

# Panzura

Understanding File Activity Monitoring

The Activity Monitor can be configured to monitor the following:

- Ability to collect all or specific file activity for specific values or specific combinations of
  values

It provides the ability to feed activity data to SIEM products. The following dashboards have been
specifically created for Activity Monitor event data:

- For IBM® QRadar®, see the
  [Netwrix File Activity Monitor App for QRadar](/docs/activitymonitor/8.0/integrations/siem/qradar.md) for additional
  information.
- For Splunk®, see the [File Activity Monitor App for Splunk](/docs/activitymonitor/8.0/integrations/siem/splunk.md) for
  additional information.

It also provides the ability to feed activity data to other Netwrix products:

- Netwrix Threat Prevention
- Netwrix Threat Manager

## Add Panzura Host

Prior to adding a Panzura host to the Activity Monitor, the prerequisites for the target environment
must be met. See the [Panzura CloudFS Monitoring](/docs/activitymonitor/8.0/platform-configuration/storage-platforms/other-storage.md) topic for
additional information.

_Remember,_ the Activity Agent must be deployed to a Windows server that acts as a proxy for
monitoring the target environment.

Follow the steps to add a Panzura host to be monitored.

**Step 1 –** In Activity Monitor, go to the Monitored Hosts tab and click Add. The Add New Host
window opens.

![Choose Agent](/img/product_docs/activitymonitor/activitymonitor/admin/monitoredhosts/add/chooseagent.webp)

**Step 2 –** On the Choose Agent page, select the **Agent** to monitor the storage device. Click
**Next**.

![Add Host](/img/product_docs/activitymonitor/activitymonitor/admin/monitoredhosts/add/addhostpanzura.webp)

**Step 3 –** On the Add Host page, select the **Panzura** radio button and enter the **Panzura filer
name**. Click **Next**.

![Panzura Properties](/img/product_docs/activitymonitor/activitymonitor/admin/monitoredhosts/add/panzuraoptions.webp)

**Step 4 –** On the Panzura Options page, enter the **Username**, **Password**, and select the
**Protocol** to be used by the Panzura host.

- The different protocols that can be selected are:

  - Auto Detect (Default)
  - HTTPS
  - HTTPS, ignore certificate errors

  Click **HTTPS Options** to open the Trusted server certificate window.

Click **Next**.

![Customize Certifiacte Verification](/img/product_docs/activitymonitor/activitymonitor/admin/monitoredhosts/add/trustedservercertificate.webp)

- HTTPS Options – Opens the Trusted server certificate window to customize the certificate
  verification during a TLS session

  - Import – Click to browse for a trusted server certificate
  - Remove – Click to remove selected trusted server certificate
  - Enable hostname verification – Select this checkbox to ensure that the host name the product
    connects to matches the name in the certificate (CN name)
  - Click OK to close the window and save the modifications

  Click **Connect** to connect to the Panzura device. Click **Next**.

![Configure Operations](/img/product_docs/activitymonitor/activitymonitor/admin/monitoredhosts/add/panzuraconfigureoperations.webp)

**Step 5 –** On the Configure Operations page, select the **File Operations** and **Directory
Operations** to be monitored.

- Suppress Microsoft Office operations on temporary files – Filters out events for Microsoft Office
  temporary files. When Microsoft Office files are saved or edited, many temporary files are
  created. With this option enabled, events for these temporary files are ignored.

Click **Next**.

![configurebasicoptionspanzura](/img/product_docs/activitymonitor/activitymonitor/admin/monitoredhosts/add/configurebasicoptionspanzura.webp)

**Step 6 –** On the Configure Basic Options page, choose which of the following settings to enable:

- Add C:\ to the beginning of the reported file paths - Adds ‘C:\” to file paths to be displayed
  like a Windows file path:
  - Display example if checked – C:\Folder\file.txt
  - Display example if unchecked – /Folder/file.text
- Report UNC paths - Adds a UNC Path column and a Rename UNC Path column in the generated TSV files
  - This option corresponds to the REPORT_UNC_PATH parameter in the INI file. It is disabled by
    default. The UNC Path is in the following format:
    - For CIFS activity – \\[HOST]\[SHARE]\[PATH]
    - Example CIFS activity – \\ExampleHost\TestShare\DocTeam\Temp.txt
    - For NFS activity – [HOST]:/[VOLUME]/[PATH]
    - Example NFS activity – ExampleHost:/ExampleVolume/DocTeam/Temp.txt
  - When the option is enabled, the added columns are populated when a file is accessed remotely
    through the UNC Path. If a file is accessed locally, these columns are empty. These columns
    have also been added as Syslog macros.
- Report operations with millisecond precision - Changes the timestamps of events being recorded in
  the TSV log file for better ordering of events if multiple events occur within the same second.
  - Access Analyzer 8.1+ is required to use this feature.

Click **Next**.

![wheretologgeneric](/img/product_docs/activitymonitor/activitymonitor/admin/monitoredhosts/add/wheretologgeneric.webp)

**Step 7 –** On the Where To Log The Activity page, select whether to send the activity to either a
**Log File)** or **Syslog Server**. Click **Next**.

**NOTE:** An option must be selected before moving to the next step.

![fileoutput](/img/product_docs/activitymonitor/activitymonitor/admin/monitoredhosts/add/fileoutput.webp)

**Step 8 –** If **Log File)** is selected on the **Where To Log The Activity** page, the **File
Output** page can be configured.

- Specify output file path – Specify the file path where TSV log files are saved on the agent's
  server. Click the ellipses button (...) to open the Windows Explorer to navigate to a folder
  destination. Click **Test** to test if the path works.
- Period to keep Log files – Log files will be deleted after the period entered as the number of
  days elapses. The default is 10 days. Use the dropdown to specify whether to keep the Log files
  for a set amount of Minutes, Hours, or Days.
- This log file is for Access Analyzer – Enable this option to have Access Analyzer collect this
  monitored host configuration

  **_RECOMMENDED:_** Identify the configuration to be read by Access Analyzer when integration is
  available.

  - While Activity Monitor can have multiple configurations per host, Access Analyzer can only
    read one of them.

- Add header to Log files – Adds headers to TSV files. This is used to feed data into Splunk.

Click **Next**.

![syslogoutput](/img/product_docs/activitymonitor/activitymonitor/admin/monitoredhosts/add/syslogoutput.webp)

**Step 9 –** If Syslog Server is selected on the **Where To Log The Activity** page, the Syslog
Output page can be configured.

- Syslog server in SERVER[:PORT] format – Type the **Syslog server name** with a SERVER:Port format
  in the textbox.
  - The server name can be short name, fully qualified name (FQDN), or IP Address, as long as the
    organization’s environment can resolve the name format used. The Event stream is the activity
    being monitored according to this configuration for the monitored host.
- Syslog Protocol – Identify the **Syslog protocol** to be used for the Event stream. The drop-down
  menu includes:

  - UDP
  - TCP
  - TLS

  The TCP and TLS protocols add the **Message framing** drop-down menu. See the
  [Syslog Tab](/docs/activitymonitor/8.0/data-collection/outputs/syslog.md) topic for additional information.

- The Test button sends a test message to the Syslog server to check the connection. A green check
  mark or red will determine whether the test message has been sent or failed to send. Messages vary
  by Syslog protocol:

  - UDP – Sends a test message and does not verify connection
  - TCP/TLS – Sends test message and verifies connection
  - TLS – Shows error if TLS handshake fails

  See the [Syslog Tab](/docs/activitymonitor/8.0/data-collection/outputs/syslog.md) topic for additional information.

Click **Finish**.

![activitymonitorpanzura](/img/product_docs/activitymonitor/activitymonitor/admin/monitoredhosts/add/activitymonitorpanzura.webp)

The added Panzura host is displayed in the monitored hosts table. Once a host has been added for
monitoring, configure the desired ouptuts. See the [Output for Monitored Hosts](/docs/activitymonitor/8.0/data-collection/outputs/log-files.md) topic
for additional information.

## Host Properties for Panzura

Configuration settings can be edited through the tabs in the host’s Properties window. The
configurable host properties are:

- [Panzura Tab](/docs/activitymonitor/8.0/monitored-systems/storage-systems/panzura.md)
- [Inactivity Alerts Tab](/docs/activitymonitor/8.0/monitored-systems/hosts/windows.md)

See the [Host Properties Window](/docs/activitymonitor/8.0/monitored-systems/index.md) topic for additional information.

# Panzura Tab

After a Panzura host is added to the monitored hosts table, the configuration settings are edited
using the tabs in the Properties window of the host.

![panzuratab](/img/product_docs/activitymonitor/activitymonitor/admin/agents/properties/panzuratab.webp)

The **Panzura** tab allows users to modify settings which were populated with the information
entered when the Panzura host was added.

The configurable options are:

- Panzura Filer – Enter the name of the filer
- Username – Enter the user name for the Panzura account
- Password – Enter the password for the user name
- Protocol – Select from the following options in the drop-down list:

  - Auto Detect
  - HTTPS
  - HTTPS, ignore certificate errors

- Connect – Click to connect using the selected protocol and validate the connection with Panzura

![Trusted Server Certificate popup window](/img/product_docs/activitymonitor/activitymonitor/admin/monitoredhosts/add/trustedservercertificate.webp)-
HTTPS Options – Opens the Trusted server certificate window to customize the certificate
verification during a TLS session

- Import – Click to browse for a trusted server certificate
- Remove – Click to remove the selected trusted server certificate
- Enable hostname verification – Select this checkbox to ensure that the host name the product
  connects and matches the name in the certificate (CN name)
- Click **OK** to close the window and save the modifications.

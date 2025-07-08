---
title: "Nasuni"
description: "Nasuni"
sidebar_position: 80
---

# Nasuni

Understanding File Activity Monitoring

The Activity Monitor can be configured to monitor the following:

- Ability to collect all or specific file activity for specific values or specific combinations of
  values

It provides the ability to feed activity data to SIEM products. The following dashboards have been
specifically created for Activity Monitor event data:

- For IBM® QRadar®, see the
  [Netwrix File Activity Monitor App for QRadar](/docs/activitymonitor/8.0/siem/qradar/overview.md) for additional
  information.
- For Splunk®, see the [File Activity Monitor App for Splunk](/docs/activitymonitor/8.0/siem/splunk/overview.md) for
  additional information.

It also provides the ability to feed activity data to other Netwrix products:

- Netwrix Access Analyzer (formerly Enterprise Auditor)
- Netwrix Threat Prevention
- Netwrix Threat Manager

Prior to adding a Nasuni Edge Appliance host to the Activity Monitor, the prerequisites for the
target environment must be met. See the
[Nasuni Edge Appliance Activity Auditing Configuration](/docs/activitymonitor/8.0/requirements/activityagent/nas-device-configuration/nasuni-activity.md) topic
for additional information.

_Remember,_ the Activity Agent must be deployed to a Windows server that acts as a proxy for
monitoring the target environment.

## Add Nasuni Host

Follow the steps to add a Nasuni Edge Appliance host to be monitored.

**Step 1 –** In Activity Monitor, go to the Monitored Hosts tab and click Add. The Add New Host
window opens.

![Choose Agent page](/img/product_docs/activitymonitor/8.0/admin/monitoredhosts/add/chooseagent.webp)

**Step 2 –** On the Choose Agent page, select the **Agent** to monitor the storage device. Click
**Next**.

![Add Host page with Nasuni selected](/img/product_docs/activitymonitor/8.0/admin/monitoredhosts/add/addhostnasuni.webp)

**Step 3 –** On the Add Host page, select the Nasuni radio button and enter the host name or IP
Address of the Nasuni Edge Appliance in the Nasuni Filer textbox. If desired, add a **Comment**.
Click **Next**.

![Nasuni Options page](/img/product_docs/activitymonitor/8.0/admin/monitoredhosts/add/nasunioptions.webp)

**Step 4 –** On the Nasuni Options page, enter the **API Key Name** and the **API Key Value**. Click
Connect to validate the connection with the Nasuni device.

- Protocol – Select from the following options in the drop-down list:
    - Auto Detect
    - HTTPS
    - HTTPS, ignore certificate errors
- Connect – Click to connect using the selected protocol and validate the connection with NetApp

Click **Next**.

![Trusted Server Certificate popup window](/img/product_docs/activitymonitor/8.0/admin/monitoredhosts/add/trustedservercertificate.webp)

- HTTPS Options – Opens the Trusted server certificate window to customize the certificate
  verification during a TLS session
    - Import – Click to browse for a trusted server certificate
    - Remove – Click to remove the selected trusted server certificate
    - Enable hostname verification – Select this checkbox to ensure that the host name the product
      connects to matches the name in the certificate (CN name)
- Click OK to close the window and save the modifications.

**Step 5 –** On the Configure Operations page, select the **File Operations, Directory Operations**,
and **Link Operations** to be monitored. Additional options include:

**CAUTION:** Enabling the Suppress subsequent Read operations in the same folder option can result
in Read events not being monitored.

- Suppress subsequent Read operations in the same folder – Logs only one Read operation when
  subsequent Read operations occur in the same folder. This option is provided to improve overall
  performance and reduce output log volume.
- Suppress reporting of File Explorer's excessive directory traversal activity – Filters out events
  of excessive directory traversal in File Explorer.
- Suppress Microsoft Office operations on temporary files – Filters out events for Microsoft Office
  temporary files. When Microsoft Office files are saved or edited, many temporary files are
  created. With this option enabled, events for these temporary files are ignored.

Click **Next**.

![Configure Basic Options page for Nasuni](/img/product_docs/activitymonitor/8.0/admin/monitoredhosts/add/configurebasicoptionsnasuni.webp)

**Step 6 –** On the Configure Basic Options page, choose which settings to enable. The “Log files”
are the activity logs created by the activity agent on the proxy host. Select the desired options:

- Report account names – Adds an Account Name column in the generated TSV files
- Add C:\ to the beginning of the reported file paths – Adds ‘C:\” to file paths to be displayed
  like a Windows file path:
    - Display example if checked – C:\Folder\file.txt
    - Display example if unchecked – /Folder/file.text
- Report UNC paths – Adds a **UNC Path** column and a **Rename UNC Path** column in the generated
  TSV files
    - This option corresponds to the REPORT_UNC_PATH parameter in the INI file. It is disabled by
      default. The UNC Path is in the following format:
        - For CIFS activity – \\[HOST]\[SHARE]\[PATH]
        - Example CIFS activity – \\ExampleHost\TestShare\DocTeam\Temp.txt
        - For NFS activity – [HOST]:/[VOLUME]/[PATH]
        - Example NFS activity – ExampleHost:/ExampleVolume/DocTeam/Temp.txt
    - When the option is enabled, the added columns are populated when a file is accessed remotely
      through the UNC Path. These columns have also been added as Syslog macros.
- Report operations with millisecond precision – Changes the timestamps of events being recorded in
  the TSV log file for better ordering of events if multiple events occur within the same second

Click **Next**.

![Where to log the activity page](/img/product_docs/activitymonitor/8.0/admin/monitoredhosts/add/wheretologgeneric.webp)

**Step 7 –** On the Where To Log The Activity page, select whether to send the activity to either a
**Log File)** or **Syslog Server**. Click **Next**.

![File Output Page](/img/product_docs/activitymonitor/8.0/admin/monitoredhosts/add/fileoutputpage.webp)

**Step 8 –** If **Log File** is selected on the **Where To Log The Activity** page, the **File
Output** page can be configured.

- Specify output file path – Specify the file path where log files are saved. Click the ellipses
  button (**...**) to open the Windows Explorer to navigate to a folder destination. Click **Test**
  to test if the path works.
- Period to keep Log files – Log files will be deleted after the period entered number of days
  entered. The default is 10 days. Use the dropdown to specify whether to keep the Log files for a
  set amount of Minutes, Hours, or Days.
- This log file is for Access Analyzer – Enable this option to have Access Analyzer collect this
  monitored host configuration

    **_RECOMMENDED:_** Identify the configuration to be read by Access Analyzer  when integration is
    available.

    - While Activity Monitor can have multiple configurations per host, Access Analyzer can only
      read one of them.

- Add header to Log files – Adds headers to TSV files. This is used to feed data into Splunk.

Click **Next**.

![Syslog Output page](/img/product_docs/activitymonitor/8.0/admin/monitoredhosts/add/syslogoutputpage.webp)

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

    The TCP and TLS protocols add the Message framing drop-down menu. See the
    [Syslog Tab](/docs/activitymonitor/8.0/admin/outputs/syslog/syslog.md) topic for additional information.

- The Test button sends a test message to the Syslog server to check the connection. A green check
  mark or red will determine whether the test message has been sent or failed to send. Messages vary
  by Syslog protocol:

    - UDP – Sends a test message and does not verify connection
    - TCP/TLS – Sends test message and verifies connection
    - TLS – Shows error if TLS handshake fails

    See the [Syslog Tab](/docs/activitymonitor/8.0/admin/outputs/syslog/syslog.md) topic for additional information.

Click **Finish**.

![Activity Monitor with Nasuni host added](/img/product_docs/activitymonitor/8.0/admin/monitoredhosts/add/activitymonitornasuni.webp)

The added Nasuni host is displayed in the monitored hosts table. Once a host has been added for
monitoring, configure the desired ouptuts. See the [Output for Monitored Hosts](/docs/activitymonitor/8.0/admin/monitoredhosts/output/output.md) topic
for additional information.

## Host Properties for Nasuni

Configuration settings can be edited through the tabs in the host’s Properties window. The
configurable host properties are:

- [Nasuni Tab](/docs/activitymonitor/8.0/admin/monitoredhosts/properties/nasuni.md)
- [Unix IDs Tab](/docs/activitymonitor/8.0/admin/monitoredhosts/properties/unixids.md)
- [Inactivity Alerts Tab](/docs/activitymonitor/8.0/admin/monitoredhosts/properties/inactivityalerts.md)

See the [Host Properties Window](/docs/activitymonitor/8.0/admin/monitoredhosts/properties/overview.md) topic for additional information.

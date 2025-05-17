---
sidebar_position: 2671
title: Hitachi
---

# Hitachi

Understanding File Activity Monitoring

The Activity Monitor can be configured to monitor the following:

* Ability to collect all or specific file activity for specific values or specific combinations of values

It provides the ability to feed activity data to SIEM products. The following dashboards have been specifically created for Activity Monitor event data:

* For IBM® QRadar®, see the [Netwrix File Activity Monitor App for QRadar](../../../SIEM/QRadar/Overview "Netwrix File Activity Monitor App for QRadar") for additional information.
* For Splunk®, see the [File Activity Monitor App for Splunk](../../../SIEM/Splunk/Overview "File Activity Monitor App for Splunk") for additional information.

It also provides the ability to feed activity data to other Netwrix products:

* Netwrix Access Analyzer (formerly Enterprise Auditor)
* Netwrix Threat Prevention
* Netwrix Threat Manager

Prior to adding a Hitachi host to the Activity Monitor, the prerequisites for the target environment must be met. See the [Hitachi Activity Auditing Configuration](../../../../Config/Hitachi/Activity "Hitachi Activity Auditing Configuration") topic for additional information.

*Remember,* the Activity Agent must be deployed to a Windows server that acts as a proxy for monitoring the target environment.

## Add Hitachi NAS Host

Follow the steps to add a Hitachi host to be monitored.

**Step 1 –** In Activity Monitor, go to the Monitored Hosts tab and click Add. The Add New Host window opens.

![Choose Agent page](../../../../../../../static/images/ActivityMonitor_8.0/Content/Resources/Images/ActivityMonitor/AddHost/ChooseAgent.png)

**Step 2 –** On the Choose Agent page, select the Agent to monitor the storage device. Click **Next**.

![Add Host page with Hitachi NAS selected](../../../../../../../static/images/ActivityMonitor_8.0/Content/Resources/Images/ActivityMonitor/AddHost/HitachiHost/AddHostHitachi.png)

**Step 3 –** On the Add Host page, select the Hitachi NAS radio button and enter the **EVS or file system name** for the device. If desired, add a **Comment**. Click **Next**.

![Hitachi NAS Options page](../../../../../../../static/images/ActivityMonitor_8.0/Content/Resources/Images/ActivityMonitor/AddHost/HitachiHost/HitachiNASOptions.png)

**Step 4 –** On the Hitachi NAS Options page, enter the **Logs path (UNC)** and the **Active Log file name**. Then enter the credentials to access the HNAS Log files. Click Connect to validate the connection with the Hitachi device. Click **Next**.

![Configure Operations page for Hitachi NAS](../../../../../../../static/images/ActivityMonitor_8.0/Content/Resources/Images/ActivityMonitor/AddHost/HitachiHost/ConfigureOperationsHitachi.png)

**Step 5 –** On the Configure Operations page, select the **File Operations** and **Directory Operations** to be monitored. Click **Next**.

![Configure Basic Options page for Hitachi NAS](../../../../../../../static/images/ActivityMonitor_8.0/Content/Resources/Images/ActivityMonitor/AddHost/HitachiHost/ConfigureBasicOptionsHitachi.png)

**Step 6 –** On the Configure Basic Options page, choose which settings to enable. The “Log files” are the activity logs created by the activity agent on the proxy host. Select the desired options:

* Report UNC paths – Adds a UNC Path column and a Rename UNC Path column in the generated TSV files
  * This option corresponds to the REPORT\_UNC\_PATH parameter in the INI file. It is disabled by default. The UNC Path is in the following format:
    * For CIFS activity – \\[HOST]\[SHARE]\[PATH]
    * Example CIFS activity – \\ExampleHost\TestShare\DocTeam\Temp.txt
    * For NFS activity – [HOST]:/[VOLUME]/[PATH]
    * Example NFS activity – ExampleHost:/ExampleVolume/DocTeam/Temp.txt
  * When the option is enabled, the added columns are populated when a file is accessed remotely through the UNC Path. If a file is accessed locally, these columns are empty. These columns have also been added as Syslog macros.
* Report operations with millisecond precision – Changes the timestamps of events being recorded in the TSV log file for better ordering of events if multiple events occur within the same second

Click **Next**.

![Where To Log The Activity](../../../../../../../static/images/ActivityMonitor_8.0/Content/Resources/Images/ActivityMonitor/AddHost/HitachiHost/WhereToLogTheActivity.png "Where To Log The Activity")

**Step 7 –** On the Where To Log The Activity page, select whether to send the activity to either a **Log File)** or **Syslog Server**. Click **Next**.

![File Output Page](../../../../../../../static/images/ActivityMonitor_8.0/Content/Resources/Images/ActivityMonitor/AddHost/HitachiHost/FileOutputPage.png "File Output Page")

**Step 8 –** If **Log File** is selected on the **Where To Log The Activity** page, the **File Output** page can be configured.

* Specify output file path – Specify the file path where log files are saved. Click the ellipses button (**...**) to open the Windows Explorer to navigate to a folder destination. Click **Test** to test if the path works.
* Period to keep Log files – Log files will be deleted after the period entered number of days entered. The default is 10 days. Use the dropdown to specify whether to keep the Log files for a set amount of Minutes, Hours, or Days.
* This log file is for Access Analyzer – Enable this option to have Netwrix Access Analyzer (formerly Enterprise Auditor) collect this monitored host configuration

  ***RECOMMENDED:*** Identify the configuration to be read by Netwrix Access Analyzer (formerly Enterprise Auditor) when integration is available.

  * While Activity Monitor can have multiple configurations per host, Netwrix Access Analyzer (formerly Enterprise Auditor) can only read one of them.
* Add header to Log files – Adds headers to TSV files. This is used to feed data into Splunk.

Click **Next**.

![](../../../../../../../static/images/ActivityMonitor_8.0/Content/Resources/Images/ActivityMonitor/AddHost/HitachiHost/SyslogOutput.png)

**Step 9 –** If Syslog Server is selected on the **Where To Log The Activity** page, the Syslog Output page can be configured.

* Syslog server in SERVER[:PORT] format – Type the **Syslog server name** with a SERVER:Port format in the textbox.
  * The server name can be short name, fully qualified name (FQDN), or IP Address, as long as the organization’s environment can resolve the name format used. The Event stream is the activity being monitored according to this configuration for the monitored host.
* Syslog Protocol – Identify the **Syslog protocol** to be used for the Event stream. The drop-down menu includes:
  * UDP
  * TCP
  * TLS

  The TCP and TLS protocols add the Message framing drop-down menu. See the [Syslog Tab](../../Outputs/Syslog "Syslog Tab") topic for additional information.
* The Test button sends a test message to the Syslog server to check the connection. A green check mark or red will determine whether the test message has been sent or failed to send. Messages vary by Syslog protocol:
  * UDP – Sends a test message and does not verify connection
  * TCP/TLS – Sends test message and verifies connection
  * TLS – Shows error if TLS handshake fails

  See the [Syslog Tab](../../Outputs/Syslog "Syslog Tab") topic for additional information.

Click **Finish**.

![Activity Monitor with Hitachi Host added](../../../../../../../static/images/ActivityMonitor_8.0/Content/Resources/Images/ActivityMonitor/AddHost/HitachiHost/ActivityMonitorHitachi.png)

The added Hitachi host is displayed in the monitored hosts table. Once a host has been added for monitoring, configure the desired ouptuts. See the [Output for Monitored Hosts](../Output "Output for Monitored Hosts") topic for additional information.

## Host Properties for Hitachi

Configuration settings can be edited through the tabs in the host’s Properties window. The configurable host properties are:

* [Hitachi NAS Tab](../Properties/HitachiNAS "Hitachi NAS Tab")
* [Inactivity Alerts Tab](../Properties/InactivityAlerts "Inactivity Alerts Tab")

See the [Host Properties Window](../Properties/Overview "Host Properties Window") topic for additional information.
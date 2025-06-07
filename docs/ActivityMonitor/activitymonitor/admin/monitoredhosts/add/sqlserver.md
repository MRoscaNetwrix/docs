# SQL Server

Understanding SQL Server Activity Monitoring

The Activity Monitor provides the ability to feed activity data to other Netwrix products:

- Netwrix Access Analyzer (formerly Enterprise Auditor)

Prior to adding a SQL Server host to the Activity Monitor, the prerequisites for the target environment must be met. See the [SQL Server Activity Auditing Configuration](/docs/product_docs/activitymonitor/config/sqlserver/activity.md) topic for additional information.

_Remember,_ the Activity Agent must be deployed to a Windows server that acts as a proxy for monitoring the target environment.

## Add MS SQL Server Host

Follow the steps to add a SQL Server host to be monitored.

__Step 1 –__ In Activity Monitor, go to the Monitored Hosts tab and click Add. The Add New Host window opens.

![chooseagent](/static/img/product_docs/activitymonitor/activitymonitor/admin/monitoredhosts/add/chooseagent.png)

__Step 2 –__ On the Choose Agent page, select the __Agent__ to monitor the storage device, then click __Next__.

![addhost](/static/img/product_docs/activitymonitor/activitymonitor/admin/monitoredhosts/add/addhost.png)

__Step 3 –__ On the __Add Host__ page, select __MS SQL Server__ and enter the __Server name or address__ for the SQL Server host., then click __Next__.

![mssqlserveroptionspage](/static/img/product_docs/activitymonitor/activitymonitor/admin/monitoredhosts/add/mssqlserveroptionspage.png)

__Step 4 –__ On the MS SQL Server Options page, configure the following options:

- Enable Audit automatically — Check the box to enable automatic auditing if it is ever disabled
- Open instruction — Opens the __How to create a SQL Login for Monitoring__ page. See the SQL Server Database section of the [SQL Server Activity Auditing Configuration](/docs/product_docs/activitymonitor/config/sqlserver/activity.md) topic for additional information.
- User name — Enter the user name for the credentials for the SQL Server
- User password — Enter the password for the credentials for the SQL Server

Click __Connect__ to test the settings, then click __Next__.

![configureoperations](/static/img/product_docs/activitymonitor/activitymonitor/admin/monitoredhosts/add/configureoperations.png)

__Step 5 –__ On the Configure Operations page, select which SQL Server events to monitor, then click __Next__.

![SQL Server Objects Page](/static/img/product_docs/activitymonitor/activitymonitor/admin/monitoredhosts/add/sqlserverobjects.png)

__Step 6 –__ On the SQL Server Objects page, click __Refresh__. Select the SQL Server objects to be monitored. Click __Next__.

![sqlserverlogontriggerpage](/static/img/product_docs/activitymonitor/activitymonitor/admin/monitoredhosts/add/sqlserverlogontriggerpage.png)

__Step 7 –__ On the SQL Server Logon Trigger page, copy and paste the SQL script into a New Query in the SQL database. Execute the query to create a logon trigger. Netwrix Activity Monitor will monitor SQL logon events and obtain IP addresses for connections. The script is:

```
CREATE TRIGGER SBAudit_LOGON_Trigger ON ALL SERVER FOR LOGON AS BEGIN declare @str varchar(max)=cast(EVENTDATA() as varchar(max));raiserror(@str,1,1);END
```

![SQL Server Logon Success](/static/img/product_docs/activitymonitor/activitymonitor/admin/monitoredhosts/add/sqlserverlogontriggersuccess.png)

> Click __Check Status__ to see if the trigger is configured properly, then click __Next__.

![configurebasicoptions](/static/img/product_docs/activitymonitor/activitymonitor/admin/monitoredhosts/add/configurebasicoptions.png)

__Step 8 –__ On the Configure Basic Options page,

- Period to keep Log files - Activity logs are deleted after the number of days entered. Default is set to 10 days.

  ___RECOMMENDED:___ Keep a minimum of 10 days of activity logs. Raw activity logs should be retained to meet an organization’s audit requirements.

Click __Next__.

![Where To Log The Activity page](/static/img/product_docs/activitymonitor/activitymonitor/admin/monitoredhosts/add/wheretologgeneric.png)

__Step 9 –__ On the Where To Log The Activity page, select whether to send the activity to either a __Log File (TSV)__ or __Syslog Server__, then click __Next__.

![fileoutput](/static/img/product_docs/activitymonitor/activitymonitor/admin/monitoredhosts/add/fileoutput.png)

__Step 10 –__ If __Log File__ is selected on the __Where To Log The Activity__ page, the __File Output__ page can be configured.

- Specify output file path – Specify the file path where log files are saved. Click the ellipses button (__...__) to open the Windows Explorer to navigate to a folder destination. Click __Test__ to test if the path works.
- Period to keep Log files – Log files will be deleted after the period entered number of days entered. The default is 10 days. Use the dropdown to specify whether to keep the Log files for a set amount of Minutes, Hours, or Days.
- This log file is for Access Analyzer – Enable this option to have Access Analyzer collect this monitored host configuration

  ___RECOMMENDED:___ Identify the configuration to be read by Access Analyzer when integration is available.

  - While Activity Monitor can have multiple configurations per host, Access Analyzer can only read one of them.

![syslogoutput](/static/img/product_docs/activitymonitor/activitymonitor/admin/monitoredhosts/add/syslogoutput.png)

__Step 11 –__ If Syslog Server is selected on the __Where To Log The Activity__ page, the Syslog Output page can be configured.

- Syslog server in SERVER[:PORT] format – Type the __Syslog server name__ with a SERVER:Port format in the textbox.
  - The server name can be short name, fully qualified name (FQDN), or IP Address, as long as the organization’s environment can resolve the name format used. The Event stream is the activity being monitored according to this configuration for the monitored host.
- Syslog Protocol – Identify the __Syslog protocol__ to be used for the Event stream. The drop-down menu includes:
  - UDP
  - TCP
  - TLS

  The TCP and TLS protocols add the Message framing drop-down menu. See the [Syslog Tab](/docs/product_docs/activitymonitor/activitymonitor/admin/outputs/syslog.md) topic for additional information.
- The Test button sends a test message to the Syslog server to check the connection. A green check mark or red will determine whether the test message has been sent or failed to send. Messages vary by Syslog protocol:
  - UDP – Sends a test message and does not verify connection
  - TCP/TLS – Sends test message and verifies connection
  - TLS – Shows error if TLS handshake fails

  See the [Syslog Tab](/docs/product_docs/activitymonitor/activitymonitor/admin/outputs/syslog.md) topic for additional information.

Click __Finish__.

![activitymonitorsqlserverhost](/static/img/product_docs/activitymonitor/activitymonitor/admin/monitoredhosts/add/activitymonitorsqlserverhost.png)

The added SQL Server host is displayed in the monitored hosts table. Once a host has been added for monitoring, configure the desired ouptuts. See the [Output for Monitored Hosts](/docs/product_docs/activitymonitor/activitymonitor/admin/monitoredhosts/output.md) topic for additional information.

## Host Properties for SQL Server

Configuration settings can be edited through the tabs in the host’s Properties window. The configurable host properties are:

- [MS SQL Server Tab](/docs/product_docs/activitymonitor/activitymonitor/admin/monitoredhosts/properties/mssqlserver.md)
- [Logon Trigger Tab](/docs/product_docs/activitymonitor/activitymonitor/admin/monitoredhosts/properties/logontrigger.md)
- [Tweak Options Tab](/docs/product_docs/activitymonitor/activitymonitor/admin/monitoredhosts/properties/tweakoptions.md)
- [Inactivity Alerts Tab](/docs/product_docs/activitymonitor/activitymonitor/admin/monitoredhosts/properties/inactivityalerts.md)

See the [Host Properties Window](/docs/product_docs/activitymonitor/activitymonitor/admin/monitoredhosts/properties/overview.md) topic for additional information.

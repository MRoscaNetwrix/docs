# Getting Started

Once Netwrix Activity Monitor is installed, the following workflow enables organizations to quickly
and easily get started with activity monitoring.

## Requirements

The Activity Monitor console needs to be installed on a server. After that agents are deployed to
the target environment and configured to monitor activity. It is necessary to prepare the target
environment and configure the credentials used by the agents. Each supported environment has
different requirements. See the following topics for additional information:

- Console server
  [Requirements ](/docs/activitymonitor/7.1/requirements/overview.md)
- [Activity Agent Server Requirements](/docs/activitymonitor/7.1/requirements/activityagent.md)
  for monitoring:

    - Exchange Online
    - Microsoft Entra ID
    - NAS devices
    - SharePoint farms
    - SharePoint Online
    - SQL Servers
    - Windows File servers

- [AD Agent Server Requirements](/docs/activitymonitor/7.1/requirements/adagent.md)
  for monitoring Active Directory
- [Linux Agent Server Requirements](/docs/activitymonitor/7.1/requirements/linuxagent.md)
  for monitoring Linux file servers

## Install & Deploy Agents

Once the prerequisites are accomplished, you are ready to install the application and deploy agents.
See the following topics for additional information:

- [Install Application](/docs/activitymonitor/7.1/install/application.md)
- [Agent Information](/docs/activitymonitor/7.1/install/agents.md)
- [Import License Key](/docs/activitymonitor/7.1/install/importlicensekey.md)

## Configure Monitoring

After the agents have been deployed, you can configure the monitoring of the target environment. For
Windows File Servers, this can be done at the same time as the agent is deployed, but for all other
target environments it is done after the agent is deployed. You will configure what will be
monitored as well as where the collected data will go (outputs). See the following topics for
additional information:

- [Monitored Domains Tab](/docs/activitymonitor/7.1/admin/monitoreddomains/overview.md)
  for Active Directory monitoring
- [Monitored Hosts Tab](/docs/activitymonitor/7.1/admin/monitoredhosts/overview.md)
  for all other target environments.

## Search Activity Event Data

You can query the activity logs created by the activity agents from within the console. Using the
search feature, set filters for the query to view monitored events. See the
[Search Feature](/docs/activitymonitor/7.1/admin/search/overview.md) topic
for additional information.

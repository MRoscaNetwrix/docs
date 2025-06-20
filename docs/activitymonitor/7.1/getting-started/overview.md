# Getting Started

Once Netwrix Activity Monitor is installed, the following workflow enables organizations to quickly
and easily get started with activity monitoring.

## Requirements

The Activity Monitor console needs to be installed on a server. After that agents are deployed to
the target environment and configured to monitor activity. It is necessary to prepare the target
environment and configure the credentials used by the agents. Each supported environment has
different requirements. See the following topics for additional information:

- Console server
  [Requirements ](/docs/activitymonitor/7.1/getting-started/requirements.md)
- [Activity Agent Server Requirements](/docs/activitymonitor/7.1/getting-started/requirements.md)
  for monitoring:

  - Exchange Online
  - Microsoft Entra ID
  - NAS devices
  - SharePoint farms
  - SharePoint Online
  - SQL Servers
  - Windows File servers

- [AD Agent Server Requirements](/docs/activitymonitor/7.1/getting-started/requirements.md)
  for monitoring Active Directory
- [Linux Agent Server Requirements](/docs/activitymonitor/7.1/getting-started/requirements.md)
  for monitoring Linux file servers

## Install & Deploy Agents

Once the prerequisites are accomplished, you are ready to install the application and deploy agents.
See the following topics for additional information:

- [Install Application](/docs/activitymonitor/7.1/installation/application.md)
- [Agent Information](/docs/activitymonitor/7.1/installation/agents.md)
- [Import License Key](/docs/activitymonitor/7.1/installation/application.md)

## Configure Monitoring

After the agents have been deployed, you can configure the monitoring of the target environment. For
Windows File Servers, this can be done at the same time as the agent is deployed, but for all other
target environments it is done after the agent is deployed. You will configure what will be
monitored as well as where the collected data will go (outputs). See the following topics for
additional information:

- [Monitored Domains Tab](/docs/activitymonitor/7.1/administration/monitored-resources/domains.md)
  for Active Directory monitoring
- [Monitored Hosts Tab](/docs/activitymonitor/7.1/administration/monitored-resources/hosts.md)
  for all other target environments.

## Search Activity Event Data

You can query the activity logs created by the activity agents from within the console. Using the
search feature, set filters for the query to view monitored events. See the
[Search Feature](/docs/activitymonitor/7.1/administration/search-and-query/overview.md) topic
for additional information.

# Netwrix Activity Monitor v7.1 Documentation

The Netwrix Activity Monitor deploys agents to target environments to provide real-time monitoring
of activity. It can be configured to provide the event data to other Netwrix products for reporting
and alerting purposes. The Activity Monitor also provides operational efficiencies and visibility
into a wide spectrum of human and machine data interactions with a standardized format that is used
to gain deeper visibility into activity associated with the access, use, and modification of data.

See the [Getting Started](/docs/activitymonitor/7.1/getting-started/overview.md)
topic for additional information.

New Product Name!

With the v7.0 release, Stealthbits Activity Monitor has been renamed Netwrix Activity Monitor.

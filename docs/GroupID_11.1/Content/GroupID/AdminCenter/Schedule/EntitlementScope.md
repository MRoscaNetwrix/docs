---
sidebar_position: 7245
title: Entitlement Scope Schedule
---

# Entitlement Scope Schedule

An Entitlement Scope schedule is automatically created for an identity store when:

* A server is added for permission analysis on the Entitlement page in an Active Directory identity store. See the [Manage File Servers](../Entitlement/AD/Manage "Manage File Servers") for additional information on adding a server.

  Or
* A SharePoint site is added for permission analysis on the Entitlement page in a Microsoft Entra ID identity store. See the [Manage SharePoint Sites](../Entitlement/EntraID/Manage "Manage SharePoint Sites") topic for additional information on adding a SharePoint site.

Using the Directory Manager portal, users can update the permissions on files and folders residing on file servers (for Active Directory) and the document libraries in SharePoint sites (for Microsoft Entra ID). These changes to permissions are instantly committed to the respective
file server or site; however, they are displayed in the Directory Manager portal after the Entitlement Scope schedule runs.

By default, the schedule runs daily to replicate the permissions from file servers or sites to Elasticsearch. Permissions are replicated for the target folder, site, or document library and its sub-trees, till the nth level. Changes made to permissions
outside of Directory Manager are beyond the scope of this schedule.

Permissions replicated by the Entitlement Scope schedule are also replicated by the [GroupID Entitlement Schedule](Entitlement "GroupID Entitlement Schedule"), as the latter replicates permissions from scratch. However, the default triggering frequency for the Directory Manager Entitlement schedule (i.e., weekly) necessitates a separate Entitlement Scope schedule.

The Entitlement Scope schedule runs in the context of the following accounts:

* For file servers, the schedule runs in the context of the service account defined for the identity store. In case you specify a different account for a file server, the schedule runs in the context of the changed account. See the [Connect to a File Server Using a Different Account](../Entitlement/AD/Manage#connect "Connect to a File Server Using a Different Account") topic for additional information.
* For a SharePoint site, the schedule runs in the context of the account you specified to connect to the SharePoint admin site. In case you specify a different account for a site, the schedule runs in the context of the changed account. See the [Connect to a Site Using a Different Account](../Entitlement/EntraID/Manage#Connect "Connect to a Site Using a Different Account") topic for additional information.

You cannot create or delete an Entitlement Scope schedule; only edit the existing schedule.

## Update the Entitlement Scope Schedule

Follow the steps to update the Entitlement Scope schedule.

Step 1 – In Admin Center, click **Identity Stores** in the left pane.

Step 2 – On the Identity Stores page, click the ellipsis button for an identity store and select **Edit**.

Step 3 – Click **Schedules** under Settings in the left pane.

Step 4 – On the Schedules page, click the plus sign next to Entitlement Scope. Then click the ellipsis button for the schedule and select **Edit**.

Step 5 – On the Edit Schedule page, the Schedule Name and Name Preview boxes display the name of the schedule as read-only. The name format is *Entitlement\_\_Scope*.

Step 6 – In the **Scheduler Service Name** drop-down list, select a Scheduler service that would be responsible for triggering this schedule. The number of services displayed in the list depend on the number of nodes in all Elasticsearch clusters in the environment, as each node has its own Scheduler service. See the [Scheduler Service](../Service/SchedulerService "Scheduler Service") topic for additional information.

Please note the following while selecting a Scheduler service:

* The Scheduler service for the Directory Manager instance on which you are creating the schedule is selected by default. However, you can select the Scheduler service of another instance as well.

* The Scheduler service can be changed even after creating the schedule. Upon the next run, the schedule will be triggered by the newly-selected Scheduler service.

* If the selected Scheduler service fails to trigger the schedule, then no other Scheduler service can be selected automatically.

* If a schedule is run manually on the Admin Center, then the Scheduler service of that instance will be used.

Step 7 – The Triggers area displays the default triggering frequency for the schedule.

* To change a trigger, click **Edit** for it.
* To add a new trigger, click **Add Trigger**.

Step 8 – Follow step 11 in
the [Create a Group Usage Service Schedule](GroupUsageService#Create "Create a Group Usage Service Schedule") topic to manage triggers.

Step 9 – After making the changes, click **Update Schedule**.

Step 10 – On the Schedules page, click **Save**.  
For general schedule info, see the [View the Schedules in an Identity Store](Manage#view "View the Schedules in an Identity Store ")topic for additional information.
# Manage Settings for a Remote IIS Deployment

You can manage various settings for a portal instance deployed in remote IIS.

What do you want to do?

## Start or Stop an Instance

To start or stop a deployment instance, see the [Start or Stop an Instance](nativeiis.md#start-or-stop-an-instance) topic.

## View the Deployment Settings for an Instance

When creating a portal’s deployment instance in remote IIS, you have to provide info related to the [Microsoft IIS Administration API](https://learn.microsoft.com/en-us/iis-administration/), such as:

- The API URL that Directory Manager uses for communicating with the remote IIS server
- The access token that Directory Manager uses to access the API
- The credentials used to connect to the API

You also have to provide an IIS application name, select a site to host the portal instance, and specify the Data service and Security service the instance should use.

Once the instance is created, you can view these settings but you cannot modify them.

To view deployment settings:

1. n Admin Center, select __Applications__ in the left pane.  
   On the __GroupID Portal__ tab, a portal card displays its info, including all its instances. You can differentiate between a standard Directory Manager portal and a SSPR portal from the portal logo, as each portal type has its own logo.
2. Click the ellipsis button for a portal and select __Settings__.
3. Click __Deployments__ under __Server Settings__; the __Deployment Settings__ page is displayed. Click the __Remote IIS__ tab.
4. On the __Remote IIS__ tab, the __Select Application Deployment__ drop-down list displays all portal instances deployed in remote IIS. Select an instance to view its settings.
5. On the __Deployment Configurations__ tab, you can view the API URL, access token, and credentials. You can also view the name of the portal application in remote IIS, the site where it is hosted, the URL to launch the instance, and the Data service and Security service the instance uses. Refer to steps 7-12 in the [Create a Portal in Remote IIS](../create.md#create-a-portal-in-remote-iis) topic for
   a description of these fields.

## Set File Logging and Windows Logging for an Instance

To set file logging and Windows logging levels for a deployment instance, see the [Manage Log Settings](log.md) topic.

## Delete an Instance

To delete a portal’s deployment instance, see the [Delete a Deployment Instance for a Portal](../delete.md#delete-a-deployment-instance-for-a-portal) topic.

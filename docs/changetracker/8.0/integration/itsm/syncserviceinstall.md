---
title: "Sync Service Installation"
description: "Sync Service Installation"
sidebar_position: 10
---

# Sync Service Installation

The Sync Service is installed as a Windows service. Currently only a single instance of the service
is supported. Run the installer executable, following the installer wizard steps in turn.

## Requirements

- Windows Server 2022
- .NET Core 8
- Change Tracker 8

## Select Components

Under the “ITSM Integration” option, select one ITSM system to integrate with. For brevity this
document describes the steps for a ServiceNow setup, but the steps vary little between ITSMs.

![selectitsm](/img/product_docs/changetracker/8.0/integration/itsm/selectitsm.webp)

## Change Tracker Hub Connection

Enter the required configuration values:

![itsmurl](/img/product_docs/changetracker/8.0/integration/itsm/itsmurl.webp)

- In the “Hub Server URL” field, specify the URL for your Change Tracker REST API endpoint, e.g.
  https://changetracker-server/api
- In the “Sync service username” and “Sync service password” fields, enter the credentials for the
  Change Tracker user account which the service should use to connect to Change Tracker; it is
  recommended that a user account be created specifically for this purpose. Note: Change Tracker
  includes an “ITSM” role which is preconfigured with the necessary permissions.

## Authentication

Select which type of authorization to use:

![authenticationtype](/img/product_docs/changetracker/8.0/integration/itsm/authenticationtype.webp)

- Basic (provide Username / Password of a ServiceNow user account only). Use when OAuth
  authorization is not available. The encoded credentials are sent in the headers of every HTTP
  request.
- OAuth2 Resource Owner Password Flow (provide Username / Password of a ServiceNow user account, and
  Client ID / Client Secret of a ServiceNow OAuth application). Use when using an OAuth application
  registration native to ServiceNow.
- OAuth2 Client Credentials Flow (provide Client ID / Client Secret of an OAuth application). Use if
  required by an OAuth application not registered with ServiceNow e.g. Apigee.

## ITSM URLs

Enter the require configuration values:

![servicenowconnection](/img/product_docs/changetracker/8.0/integration/itsm/servicenowconnection.webp)

- In the “ServiceNow ITSM Server URL” field, specify the URL for your ServiceNow REST API endpoint,
  e.g. https://service-now-server/api
- In the “ServiceNow OAuth2 Token URL” field (not applicable if using Basic Authentication), specify
  the URL for your OAuth2 token endpoint, e.g. https://service-now-server/ oauth_token.do

## ITSM Account

A ServiceNow account must be created specifically for the Sync Service to connect with. The Sync
Service must be configured to use the same time zone as this ServiceNow account. Because UTC is not
an option for a user's time zone in ServiceNow, the Sync Service defaults to GMT. The only
requirement here is for the time zones to match, so the easiest approach is to use GMT for the
ServiceNow user, but it is possible to configure the Sync Service to use a different time zone by
setting the serviceNow.timeZone element in the Sync Service configuration file (see the
administration page for instructions).

![servicenowcredentials](/img/product_docs/changetracker/8.0/integration/itsm/servicenowcredentials.webp)

- In the “ServiceNow ITSM username” and “ServiceNow ITSM password” fields (not applicable if using
  OAuth2 Client Credentials), enter the credentials for the ServiceNow user account which the
  service should use to connect to ServiceNow.
- In the “ServiceNow OAuth2 Client ID” and “ServiceNow OAuth2 Client Secret” fields (not applicable
  if using Basic Authentication), enter the Client ID and Client Secret associated with the OAuth
  application registration.

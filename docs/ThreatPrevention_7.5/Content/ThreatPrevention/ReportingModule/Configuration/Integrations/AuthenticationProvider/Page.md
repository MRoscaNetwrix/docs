---
sidebar_position: 6748
title: Authentication Provider Page
---

# Authentication Provider Page

The Authentication Provider page provides configuration settings for third-party authentication providers using RADIUS, OpenID, and SAML integrations.

Use the gear icon in the upper right corner of the console to open the Configuration menu. Then select **Integrations** to open the Integrations interface.

![Integrations interface on the Authentication Provider page](../../../../../../../../static/images/ThreatPrevention_7.5/Content/Resources/Images/ThreatPrevention/Reporting/Configuration/Integrations/AuthenticationProvider/Page.png "Integrations interface on the Authentication Provider page")

Click **Authentication Provider** in the navigation pane to view a list of already configured authentication providers, if any.

The table displays the provider name, as supplied during configuration, and an icon indicating if the integration is enabled. To view provider details or make modifications, select a provider from the table or select it from the Credential Profile drop-down in the navigation pane.

## Add an Authentication Provider

Follow the steps to add an authentication provider.

**Step 1 –** On the Integrations interface, click Add New Integration in the navigation pane. The Add New Integration window opens.

![Add New Integration window with Authentication Provider type selected](../../../../../../../../static/images/ThreatPrevention_7.5/Content/Resources/Images/ThreatManager/Admin/Configuration/Integrations/AddNew/AuthenticationProvider.png "Add New Integration window with Authentication Provider type selected")

**Step 2 –** In the Type drop-down list, select Authentication Provider.

**Step 3 –** Provide a unique name and description for the authentication provider.

**Step 4 –** Click Add. The Add New Integration window closes.

The authentication provider is listed in the Integrations navigation pane and the configuration window for the provider opens. You must configure the provider for use with a supported authentication provider type, i.e., OpenID, RADIUS, or SAML.

## Supported Types of Authentication Providers

On the Integrations interface, select an authentication provider under the Authentication Provider node in the navigation pane or from the table to configure, view, or modify its details.

![Integrations interface displaying the details for an Authentication Provider with the type drop-down menu open](../../../../../../../../static/images/ThreatPrevention_7.5/Content/Resources/Images/ThreatPrevention/Reporting/Configuration/Integrations/AuthenticationProvider/Type.png "Integrations interface displaying the details for an Authentication Provider with the type drop-down menu open")

The following authentication provider types are supported; you can configure an authentication provider for any of these:

* RADIUS – See the [RADIUS Authentication Provider](RADIUS "RADIUS Authentication Provider") topic for additional information.
* OpenID – See the [OpenID Authentication Provider](OpenID "OpenID Authentication Provider") topic for additional information.
* SAML – See the [SAML Authentication Provider](SAML "SAML Authentication Provider") topic for additional information.
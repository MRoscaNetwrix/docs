---
sidebar_position: 2680
title: Nasuni Tab
---

# Nasuni Tab

After a Nasuni host is added to the monitored hosts table, the configuration settings are edited using the tabs in the Properties window of the host.

![Nasuni Host Properties - Nasuni Tab](../../../../../../../static/images/ActivityMonitor_8.0/Content/Resources/Images/ActivityMonitor/AddHost/NasuniHost/NasuniTab.png)

The **Nasuni** tab allows users to modify settings which were populated with the information entered when the Nasuni host was added.

The configurable options are:

* Nasuni Filer – Enter the name of the filer
* Username – Enter the user name for the Nasuni account
* Password – Enter the password for the user name
* Protocol – Select from the following options in the drop-down list:

  * Auto Detect
  * HTTPS
  * HTTPS, ignore certificate errors
* Connect – Click to connect using the selected protocol and validate the connection with Nasuni

![Trusted Server Certificate popup window](../../../../../../../static/images/ActivityMonitor_8.0/Content/Resources/Images/ActivityMonitor/AddHost/TrustedServerCertificate.png "Trusted Server Certificate popup window")* HTTPS Options – Opens the Trusted server certificate window to customize the certificate verification during a TLS session

  * Import – Click to browse for a trusted server certificate
  * Remove – Click to remove the selected trusted server certificate
  * Enable hostname verification – Select this checkbox to ensure that the host name the product connects and matches the name in the certificate (CN name)
  * Click **OK** to close the window and save the modifications.
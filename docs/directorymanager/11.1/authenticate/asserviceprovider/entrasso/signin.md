---
title: "Sign In Using Microsoft Entra ID SSO"
description: "Sign In Using Microsoft Entra ID SSO"
sidebar_position: 30
---

# Sign In Using Microsoft Entra ID SSO

We configured Microsoft Entra ID SSO with a Directory Manager client, that is the Directory Manager
portal _Wizard_ in our example. For single sign-on using Microsoft Entra ID SSO, we can choose any
of the following ways:

- SP-initiated single sign-on - when the SSO operation is initiated from the SP end, i.e., from the
  Directory Manager portal, Wizard.
- IdP-initiated single sign-on - when the SSO operation is initiated from the IdP end, i.e., from
  the Microsoft Entra ID SSO application.

### SP-Initiated Single Sign-On

Step 1 – Launch the Directory Manager portal _Wizard_.  
On the Login page, notice the Microsoft Entra ID SSO button. You can login using your Directory
Manager credentials or click this button to log in.  
The availability of the user name and password fields depends on whether you disabled Directory
Manager Authentication or not (see step 10 in the
[Configure the Provider in Directory Manager](configureproviderindirectorymanager.md#configure-the-provider-in-directory-manager)
topic).

Step 2 – Click the button or image for Microsoft Entra ID SSO; the Microsoft Sign In page is
displayed.

Step 3 – Enter your credentials and click **Sign In**. You will be routed to the main page of the
Directory Manager portal _Wizard_.  
Only users defined for our app in Microsoft Entra Admin Center can log in by entering their user
names and passwords. See step 11 in the
[Configure Directory Manager in Microsoft Entra ID](configureinentra.md#configure-directory-manager-in-microsoft-entra-id)
topic.

With single sign-on, you can now launch any Directory Manager client without having to sign in
again.

### IdP-Initiated Single Sign-On

Step 1 – Launch the Microsoft My Apps portal using the following URL and sign in.  
https://myapps.microsoft.com

Step 2 – Click the Directory Manager app that we created to work with the _Wizard_ portal for single
sign-on; it will redirect you to your portal.

title: Email Notifications Configuration
sidebar_label: Notifications
description: Configure email notifications for backup job completion and other Recovery for Active Directory events with SMTP settings and templates.

# Notifications Page

The Notifications page allows the configuration of notifications, which is required for sending an
email when a collection (backup) job is completed. Only a user with the administrator role can
configure notifications.

Click **Configuration** in the left pane. Then click the **Notification tab** on the Configuration
page to open the Notification page.

![Notifications Page](/img/product_docs/1secure/admin/notifications.webp)

Follow the steps to configure notifications.

**Step 1 –** Select the **Enable** check box to configure email notifications.

**Step 2 –** In the SMTP Settings section, configure the SMTP server. If the SMTP server does not
require authentication, the Account name and Account password fields can be left blank.

- SMTP Server – The server and port information
- Account Name – Name of the account to use for accessing the mail server
- Account Password – Password for the account

**Step 3 –** Select an encryption protocol to encode the email notifications from the Encryption
method drop-down menu.

**Step 4 –** In the Send Email As section, configure the email address and display name to use for
sending email notifications.

- Email address – Create an email address to be used, for example: noreply@companyname.com
- Display name – Name to be displayed on the email notifications

**Step 5 –** Click the **Test** button to verify the notifications are configured correctly.

**Step 6 –** Click the **Save** button to save the configurations.

Notifications have been configured in the system.

**NOTE:** The recipients of the notification can be added from the Domains page. See the
[Add a Domain](/docs/recoveryforactivedirectory/2.6/configuration/domain-configuration.md#add-a-domain) topic for additional information.

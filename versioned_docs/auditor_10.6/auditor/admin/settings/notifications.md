# Notifications

SMTP settings are configured when you create the first monitoring plan in the New monitoring plan wizard.

You can update notification settings at any time in the __Settings > Notifications__. Review the following for additional information:

- [Modify SMTP Settings](#Modify-SMTP-Settings)
- [Follow the steps to o send summary emails and notifications about critical events](#Follow-the-steps-to-o-send-summary-emails-and-notifications-about-critical-events)

Modify SMTP Settings

Navigate to Default SMTP settings to review settings used to deliver email notifications, reports, etc., and click Modify to adjust them if necessary.

| Option | Description |
| --- | --- |
| SMTP server | Enter your SMTP server address. It can be your company's Exchange server or any public mail server (e.g., Gmail, Yahoo). |
| Port number | Specify your SMTP server port number. |
| Sender address | Enter the address that will appear in the From field.  ___RECOMMENDED:___  click __Send Test Email__. The system will send a test message to the specified email address and inform you if any problems are detected. |
| SMTP authentication | Select this checkbox if your mail server requires the SMTP authentication. |
| User name | Enter a user name for the SMTP authentication. |
| Password | Enter a password for SMTP authentication. |
| Use Secure Sockets Layer encrypted connection (SSL) | Select this checkbox if your SMTP server requires SSL to be enabled. |
| Use implicit SSL | Select this checkbox if the implicit SSL mode is used, which means that an SSL connection is established before any meaningful data is sent. |
| Enforce certificate validation to ensure security | Select this checkbox if you want to verify security certificate on every email transmission. The option is not available for auditing User Activity as well Netwrix Auditor tools. |
| Display the following From address in email notifications | Enter the address that will appear in the "_From_" field in email notifications.  This option does not affect notifications sent to users' managers and administrators. Before configuring the "_From_" field for user email notifications, make sure that your Exchange supports this option. |

You can configure Activity Summary frequency, format and delivery time for each monitoring plan individually. See [Fine-Tune Your Plan and Edit Settings](/versioned_docs/auditor_10.6/auditor/admin/monitoringplans/finetune.md) for more information.

After that, you can specify the recipient who will receive product activity and health summary emails.

Follow the steps to o send summary emails and notifications about critical events

__Step 1 –__ Navigate to the Summary email recipient and click Modify.

__Step 2 –__ Specify recipient address:

- To send to a single recipient, enter personal mailbox address.
- To send to multiple recipients, make sure they are added to a distribution group, and enter the group address. Entering multiple individual addresses is not supported.

To learn more about product health, you can also navigate to the Health status tile in the main window. It will take you to the Health Status dashboard that contains information on the product activity and system health state. See the [Health Status Dashboard](/versioned_docs/auditor_10.6/auditor/admin/healthstatus/dashboard/overview.md) topic for additional information.

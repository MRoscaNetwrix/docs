# Email Tab

Alert notification via email sends messages through an SMTP gateway. Alerts are designed to send
email notifications to individuals or groups.

Follow the steps to configure the Email tab of the System Alerting window.

**Step 1 –** Click **Configuration** > **Alerts** on the menu. The Netwrix Threat Prevention System
Alerting window opens. The Email tab is displayed by default.

![Netwrix Threat Prevention System Alerting window](/img/versioned_docs/threatprevention_7.4/threatprevention/admin/configuration/systemalerting/systemalerting.webp)

**Step 2 –** Configure the following prior to enabling email alerting:

- [Configure SMTP Host Information](#configure-smtp-host-information)
- [Create Message Profiles](#create-message-profiles)

**Step 3 –** Once configured, click **Events** on the **Email** tab. Decide what events receive
notifications and assign one or more message profiles to the event.

**Step 4 –** Click the button next to Disabled to toggle the setting to **Enabled**.

**Step 5 –** Select an event category (Security, Operations, Configuration, Analytics, Policies) in
the left pane.

**Step 6 –** Check the checkbox for the event/incident/policy for which you want to trigger email
notifications.

**Step 7 –** Click the Select Profile, please option for an event/incident/policy and select a
Message Profile from the drop-down menu to assign it to the event/incident/policy.

- For policies, multiple profiles can be assigned by either checking the desired profile(s) or the
  Select All option. Click **OK** in the drop-down menu to confirm the selection.

You can assign a profile to as many events as required.

**Step 8 –** For Analytics, choose whether or not to enable Ongoing Attack Alerts. When checked,
Threat Prevention sends periodic reminders of an ongoing attack if it continues after the initial
notification has been sent.

**Step 9 –** Click **OK** to save the settings.

Threat Prevention now sends email notifications for the selected events/incident/policies to the
recipients of the selected Message Profiles.

### Configure SMTP Host Information

Follow the steps to configure the SMTP host information for email alerting.

_Remember,_ this is a one-time setting to enable email alerts from the Administration Console.

![System Alerting window - Email tab - Configure SMTP Host and Message Profile](/img/versioned_docs/threatprevention_7.4/threatprevention/admin/configuration/systemalerting/smtphost.webp)

**Step 1 –** Click **Configuration** > **Alerts** on the menu. The Netwrix Threat Prevention System
Alerting window opens.

**Step 2 –** On the Email tab, click **Configure**.

**Step 3 –** In the Server section, provide the SMTP Host as either the IP address or the hostname
of the SMTP gateway. Example: 192.168.189.56 or SIM1.netwrix.com

**Step 4 –** In the **Port** box, provide the appropriate port number.

**Step 5 –** Check the **Enable SSL** checkbox to use SSL communications for email.

**Step 6 –** In the **From** box, enter the email address to be used as the sender for the email.
Example: Threat Prevention@Netwrix.com

**Step 7 –** If the SMTP gateway requires authentication, check the **Requires Authentication**
checkbox and provide a username and password in the boxes that appear.

**Step 8 –** Click **OK** to save the settings.

### Create Message Profiles

Message Profiles are associated with events for email alerting. Follow the steps to create a Message
Profile.

**NOTE:** When the Message Profile is modified for an alert, all policies referencing the alert use
the updated information.

![System Alerting window - Email tab - Configure SMTP Host and Message Profile](/img/versioned_docs/threatprevention_7.4/threatprevention/admin/configuration/systemalerting/smtphost.webp)

**Step 1 –** Click **Configuration** > **Alerts** on the menu. The Netwrix Threat Prevention System
Alerting window opens.

**Step 2 –** On the Email tab, click **Configure**.

**Step 3 –** In the Message Profiles area, click the **Add** (+) button to create a Message Profile.
The default profile name (New Email Notification) is displayed.

**_RECOMMENDED:_** Provide a unique and descriptive name for this new email notification profile.

**Step 4 –** Choose between **Plain Text** and **HTML** email options. The Email Template window
displays when selecting either radio button.

![Email Template window](/img/versioned_docs/threatprevention_7.4/threatprevention/admin/configuration/systemalerting/emailtemplate.webp)

Changing the message template provides the option to load the default message template. Choose
between:

- Yes – Loads the default message template for the selected format. This overwrites the current
  message template.
- No – Leads the current message body

**Step 5 –** In the To box, provide an email address for each recipient of the email alert. This can
be individuals, distribution lists, or a combination. To send alerts to multiple recipients,
separate the addresses with either a comma (,) or a semi-colon (;). Example: IT@netwrix.com;
ITdl@netwrix.com

**Step 6 –** Click the Send Test Email link to send a test email. It sends an unformatted sample
message to all recipients. Threat Prevention informs you if the message is successfully sent, but is
not able to tell if it was received.

**Step 7 –** In the Subject box, keep the default subject line for the email or provide one that is
more suitable for the alerts these recipients receive.

**Step 8 –** The Body box contains the default message, which includes all event data types
available for notification. To customize it for the specific alerts, simply remove the Event Data
Fields not desired. Customization can also include reformatting the message as desired. The default
message is:

- Plain Text – An event has occurred in which you are on the notification list.
- HTML – The following Event has occurred at %TIME_STAMP% for which you requested notification

The available Event Data Fields and their associated tokens are:

| Event Data Field             | Token                          |
| ---------------------------- | ------------------------------ |
| Time Stamp                   | %TIME_STAMP%                   |
| Event Source Type            | %EVENT_SOURCE_TYPE%            |
| Domain Name                  | %EVENT_SOURCE_NAME%            |
| Policy Name                  | %SETTING_NAME%                 |
| Event Name                   | %EVENT_NAME%                   |
| Event Name Translated        | %EVENTNAMETRANSLATED%          |
| Originating Server           | % ORIGINATING_SERVER%          |
| Originating Server IP        | %ORIGINATING_SERVERIP%         |
| Target Host                  | %TARGETHOST%                   |
| Target Host IP               | %TARGETHOSTIP%                 |
| Class Name                   | %CLASS_NAME%                   |
| DN                           | %DN%                           |
| Affected Object SID          | %AFFECTED_OBJECT_SID%          |
| Affected Object Account Name | %AFFECTED_OBJECT_ACCOUNT_NAME% |
| Operation Successful         | %SUCCESS%                      |
| Operation Status             | %STATUS%                       |
| Blocked Event                | %BLOCKED_EVENT%                |
| Perpetrator                  | %PERPETRATOR%                  |
| Perpetrator Name             | %PERPETRATOR_NAME%             |
| Perpetrator Sid              | %PERPETRATOR_SID%              |
| Originating Client           | %ORIGINATING_CLIENT%           |
| Originating Client Host      | %ORIGINATINGCLIENTHOST%        |
| Originating Client IP        | %ORIGINATINGCLIENTIP%          |
| Originating Client Protocol  | %ORIGINATINGCLIENTPROTOCOL%    |
| Originating Client MAC       | %ORIGINATINGCLIENTMAC%         |
| Events Count                 | %EVENTS_COUNT%                 |
| Attribute Values             | %ATTRIBUTE_VALUE%              |
| Old Attribute Values         | %OLD_ATTRIBUTE_VALUE%          |
| Attribute Operations         | %OPERATION%                    |

**CAUTION:** The tokens used within the message Body, the information between and including the %
symbols (e.g. %TIME_STAMP%), must be present to retrieve that event data from the database. Tokens
can be removed, but partial tokens do not retrieve data from the database.

**Step 9 –** Click **OK** to save the settings.

Now that at least one Message Profile has been created, it can be assigned to an event either
through the System Altering window’s Email tab or assigned to a policy on the
[Actions Tab](/versioned_docs/threatprevention_7.4/threatprevention/admin/policies/actions/overview.md)
of the policy configuration or the
[Actions Tab](/versioned_docs/threatprevention_7.4/threatprevention/admin/templates/actions.md) of
the template configuration.

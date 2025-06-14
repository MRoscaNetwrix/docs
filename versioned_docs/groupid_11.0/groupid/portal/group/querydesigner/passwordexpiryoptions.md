# Query Designer - Password Expiry Options tab

The __Password Expiry Options__ tab is only available for password expiry groups. You can create a password expiry group by selecting the __Password Expiry__ group option on the Welcome page of the __Create Group__ wizard.

A password expiry group is a Smart Group whose membership contains users whose identity store account passwords are approaching their expiry dates. Members of this group are notified by email to reset their passwords. On doing so, they are automatically
removed from group membership.

On the __Password Expiry Options__ tab of the Query Designer, you can define the password expiry policy for the group. Based on this policy and the users' PWDLASTSET attribute, GroupID creates this group with users whose passwords will
soon expire.

When the group is updated, GroupID will add/remove users from the group and send email notifications to all members.

You can also include disabled users and users whose password never expire to the password expiry group.

## Domain Expiration Policy

Specify the maximum password age. The default age is 42 days. This setting does not affect your domain security settings on the directory server.

## Expiration Range Policy

This policy defines when the user is added in the password expiry group. For example, take a domain security policy configured with a maximum password age of 30 days. Setting the expiration range policy to 10 days includes users who have passwords aged
20 days or older in the password expiry group.

### Include disabled users

Select this check box to include disabled user accounts in the new group.

### Include users whose password never expires

Select this check box to include users with the __Password never expires__ setting enabled, in group membership.

## Send email after update

Select this check box to send a password expiry warning email to group members each time group membership is updated either manually or through a scheduled job.

This email contains a URL that redirects users to a Password Center portal for changing their identity store account passwords. (The administrator specifies this URL while configuring an SMTP server for the identity store.)

The __Send email after update__ options is enabled after the group is created.

Warning emails are not sent to group members (users) whose passwords are set to 'never expire'. Such users are included in group membership when you select the __Include users whose password never expires__ check box or add such users
to the __Include__ list on the [Query Designer - Include/Exclude tab](/versioned_docs/groupid_11.0/groupid/portal/group/querydesigner/includeexclude.md).

For warning emails to be sent, you must have an SMTP server configured for the identity store.

## Preview

Use this button to preview results obtained with the current settings on all tabs of the __Query Designer__ dialog box. This is a check to ensure the accuracy of data before changes are committed to the directory. On clicking it, results are displayed on the following two tabs at the bottom of the dialog box:

- Directory tab: displays the results for all the options set on all the tabs of the Query Designer dialog box.
- Advanced tab: displays the results from the selected external data source when you click the Execute button on the Advanced tab of the dialog box.

## Display preferences

The attributes of the objects displayed on the __Directory__ and __Advanced__ tabs are set using the context (right-click) menu of each column header on the tab. Options are:

| Column header's context menu option | Description |
| --- | --- |
| Size All Columns to Fit | Set the column size of each column to fit its content. |
| `<Attribute Name>` | The names of the attributes currently displayed on the tab. Clear the check box for an attribute to remove it from the __Directory__ tab. |
| __More__ | Select additional attributes to display on the tab. After adding attributes, re-launch the __Directory__ tab to refresh the list of the attributes displayed. |

In addition to the column header display options, the __Directory__ tab also provides object display options that are available when you right-click an object. Options are:

| Object's Context Menu Option | Description |
| --- | --- |
| Add to Exclude | Add the object to the Exclude list so that it cannot be added to the group's membership. |
| Export | Export the selected object's information to a comma-separated value (csv) or XML file. The export action exports only the attributes displayed on the tab. |
| Export All | Export the information of all objects on the __Directory__ tab to a comma-separated value (csv) or XML file. The export action exports only the attributes displayed on the tab. |

__Preview__

Enables you to preview the results returned with the criteria specified on all tabs of the Query Designer dialog box. This is a check to ensure the accuracy of data before changes are committed to the directory.

__OK__

Saves settings and closes the dialog box.

__Cancel__

Discards settings and closes the dialog box.

__LDAP Query__

View the provider query in the LDAP Query box.

__See Also__

- [Query Designer](/versioned_docs/groupid_11.0/groupid/portal/group/querydesigner/overview.md)

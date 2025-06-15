# Database Details Page

The Database Details page displays information for the selected database resource. This page is
opened from any linked resource within the various interfaces.

![Database Details page](/img/versioned_docs/privilegesecure_4.1/privilegesecure/accessmanagement/admin/policy/page/details/databasedetailspage.png)

The Database Details page shows the following information:

- Name — Displays the name of the resource
- Trashcan icon — Removes the selected resource from being managed by the application. A
  confirmation window will display.
- Platform — Displays the type of platform, which defines the resource
- Server — The instance name for the server
- IP Address — Displays the IP address for the resource
- Port — The port for the server
- Domain — Displays the fully qualified domain name (FQDN)

    **NOTE:** The domain is used as the default domain for database activities.

- Service Account — Displays the service account associated with the resource. See the
  [Service Accounts Page](/versioned_docs/privilegesecure_4.1/privilegesecure/accessmanagement/admin/configuration/page/serviceaccounts.md)
  topic for additional information.
- Scan Now button — Scans the domain for users, groups, members, and computers. The Cancel button,
  which is only visible when scanning can be used to stop the resource scan. This scan can also be
  scheduled from the
  [Platforms Page](/versioned_docs/privilegesecure_4.1/privilegesecure/accessmanagement/admin/policy/page/platforms/overview.md).

    - Status — During synchronization, the button displays as spinning

If any of these settings are modified, Save and Cancel buttons are displayed. Click **Save** to
commit the modifications. Click **Cancel** to discard the modifications.

 The database details page has the following tabs:

- Users – Displays database login accounts that are not domain users or local computer users
- Groups – Displays login accounts that are domain users or local computer accounts
- Databases – Displays a list of discovered databases See the
  [Databases Tab](/versioned_docs/privilegesecure_4.1/privilegesecure/accessmanagement/admin/policy/tab/resources/databases.md)
  topic for additional information.
- Roles – Displays roles and who has those roles on the database and at the server level
- Sessions – Displays previous sessions that have used this resource as a target
- Access Policies – Displays a list of access policies that this resource belongs to
- History – Displays previous sessions with events that are related to this resource

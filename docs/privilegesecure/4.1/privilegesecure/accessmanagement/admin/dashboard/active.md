# Active Dashboard

The Active sessions dashboard shows all currently active sessions. Create an Activity Session to
grant temporary privileges and gain access to the resources defined by a previously created Access
Policy. See the
[Access Policy Page](/versioned_docs/privilegesecure_4.1/privilegesecure/accessmanagement/admin/policy/page/accesspolicy.md)
topic for additional information.

![Active Dashboard page](/img/versioned_docs/privilegesecure_4.1/privilegesecure/accessmanagement/admin/dashboard/active.webp)

The dashboard has the following features:

- Search — Searches the table or list for matches to the search string. When matches are found, the
  table or list is filtered to the matching results.
- Filter — Provides options to filter results based on a chosen criterion:

    - All Active tab — Shows all sessions for all users
    - Mine tab — Shows sessions for the logged in user
    - Recording data — Filter by keystroke data and, when enabled, RDP Windows event activity. See
      the
      [Install Remote Desktop Monitor Service on Target RDP Hosts](/versioned_docs/privilegesecure_4.1/privilegesecure/accessmanagement/install/rdpmonitor.md)
      topic for additional information.

- Create Session — Open the Activity Request window. See the
  [Create Activity Session](/versioned_docs/privilegesecure_4.1/privilegesecure/accessmanagement/enduser/dashboard/createsession.md)
  topic for additional information.
- End Session — Cancel the selected session(s)
- View Logs — Opens the Session Logs window to view the action log for the selected session. See the
  [Session Logs Window](/versioned_docs/privilegesecure_4.1/privilegesecure/accessmanagement/admin/dashboard/window/sessionlogs.md)
  topic for additional information.
- Lock Activity — Opens the Lock Session window to prevent the user from interacting with the host
  but keeps the session active. See the
  [Lock Session](/versioned_docs/privilegesecure_4.1/privilegesecure/accessmanagement/admin/dashboard/window/locksession.md)
  topic for additional information.
- Unlock Activity — Unlocks a session to allow the user to interact with the host
- Refresh — Reload the information displayed
- Stop — Stop the selected session
- Delete — Deletes the completed activity session

**NOTE:** Sessions can be locked. See the
[Lock Session](/versioned_docs/privilegesecure_4.1/privilegesecure/accessmanagement/admin/dashboard/window/locksession.md)
topic for additional information.

The table has the following columns:

- Checkbox — Check to select one or more items
- Expand icon — Click the expand (>) icon to show additional information for the session:

    - The live session viewer allows an admin to watch a remote session that is in progress for
      another user. See the
      [Live Session Viewer Window](/versioned_docs/privilegesecure_4.1/privilegesecure/accessmanagement/admin/dashboard/window/liveviewer.md)
      topic for additional information.
    - If the user has logged into the remote session more than once, multiple session recordings
      will display. If a recording of the session is available, the replay viewer allows an admin to
      watch a replay of the remote session. See the
      [Replay Viewer Window](/versioned_docs/privilegesecure_4.1/privilegesecure/accessmanagement/admin/dashboard/window/replayviewer.md)
      topic for additional information.

- Status — Shows status information for the session:

    - Provisioning — Pre-Session stage of the Activity is processing and assigning permissions to
      the login account
    - Waiting for Approval — The session requires approval to begin. See the Approvals Dashboard
      topic for additional information.
    - Available — The activity session is ready. Click the icon to begin the session, or log in
      through a client. See the Start Activity Session topic for additional information.
    - Failed — Pre-Session stage of the Activity has encountered an error
    - Logged In — User is successfully logged in to the Resource either directly or via the Proxy.
      Direct log-in is detected by polling the Resource at regular intervals and may not update
      immediately.
    - Canceling — The session is either expired or was canceled manually by the user or an Privilege
      Secure administrator.
    - Locked — The session has been locked by an Privilege Secure administrator. See the
      [Lock Session](/versioned_docs/privilegesecure_4.1/privilegesecure/accessmanagement/admin/dashboard/window/locksession.md)
      topic for additional information.

- Requested — Date and time of when the session was created
- Requested By — User who requested the session. Click the link to view additional details. See the
  [User, Group, & Application Details Page](/versioned_docs/privilegesecure_4.1/privilegesecure/accessmanagement/admin/policy/page/details/usergroupapplication.md)
  topic for additional information.
- Host — Resource that the user will run the activity on. Click the link to view additional
  details.The details vary based on the type of resource. See the following topics for additional
  information:

    - [Host Details Page](/versioned_docs/privilegesecure_4.1/privilegesecure/accessmanagement/admin/policy/page/details/host.md)
    - [Domain Details Page](/versioned_docs/privilegesecure_4.1/privilegesecure/accessmanagement/admin/policy/page/details/domain.md)
    - [Website Details Page](/versioned_docs/privilegesecure_4.1/privilegesecure/accessmanagement/admin/policy/page/details/website.md)
    - [Microsoft Entra ID Details Page](/versioned_docs/privilegesecure_4.1/privilegesecure/accessmanagement/admin/policy/page/details/entraid.md)
    - [Secret Vault Details Page](/versioned_docs/privilegesecure_4.1/privilegesecure/accessmanagement/admin/policy/page/details/secretvault.md)
    - [Database Details Page](/versioned_docs/privilegesecure_4.1/privilegesecure/accessmanagement/admin/policy/page/details/databases.md)

- Login Account — Displays the account used to log onto the resource
- Activity — Displays the name of the activity. Click the link to view additional details. See the
  [Activities Page](/versioned_docs/privilegesecure_4.1/privilegesecure/accessmanagement/admin/policy/page/activities.md)
  topic for additional information.
- Start — Indicates when the activity started. This refers to when the activity's actions were
  executed and not when the user was logged on to the resource.
- End — Indicates when the session is scheduled to end the activity, which is determined by the
  start time plus the maximum session duration set by the access policy Connection Profile

The table columns can be resized and sorted in ascending or descending order.

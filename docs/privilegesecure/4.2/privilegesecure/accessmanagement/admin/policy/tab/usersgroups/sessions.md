# Sessions Tab

The Sessions tab shows information about the sessions of the selected user, group, or application.

![Sessions Tab for Application Users](/img/product_docs/privilegesecure/privilegesecure/accessmanagement/admin/policy/tab/usersgroups/usersessionstab.webp)

The Sessions tab has the following features:

- Search — Searches the table or list for matches to the search string. When matches are found, the
  table or list is filtered to the matching results.
- End Session — Cancel the selected session(s)
- View Logs — Opens the Session Logs window to view the action log for the selected session. See the
  [Session Logs Window](/docs/privilegesecure/4.2/privilegesecure/accessmanagement/admin/dashboard/window/sessionlogs.md) topic for additional information.
- Refresh — Reload the information displayed

The table has the following columns:

- Requested — Date and time of when the session was created
- User — Displays the account used to log onto the resource
- Host — Resource that the user will run the activity on. The details vary based on the type of
  resource. See the [Resources Page](/docs/privilegesecure/4.2/privilegesecure/accessmanagement/admin/policy/page/resources.md) topic for additional information.
- Start — Indicates when the activity started. This refers to when the activity’s actions were
  executed and not when the user was logged on to the resource.
- End — Indicates when the session is scheduled to end the activity, which is determined by the
  start time plus the maximum session duration set by the access policy Connection Profile
- Status — Shows status information for the session:

    - Provisioning — Pre-Session stage of the Activity is processing and assigning permissions to
      the login account
    - Complete — Activity either reached the end of its scheduled end time or was canceled early by
      the requestor
    - Waiting for Approval — The session requires approval to begin. See the Approvals Dashboard
      topic for additional information.
    - Available — The activity session is ready. Click the icon to begin the session, or log in
      through a client. See the Start Activity Session topic for additional information.
    - Failed — Pre-Session stage of the Activity has encountered an error
    - Approval Failed — Approval request has encountered an error
    - Logged In — User is successfully logged in to the Resource either directly or via the Proxy.
      Direct log-in is detected by polling the Resource at regular intervals and may not update
      immediately.
    - Canceling — The session is either expired or was canceled manually by the user or an Privilege
      Secure administrator.
    - Locked — The session has been locked by an Privilege Secure administrator. See the
      [Lock Session](/docs/privilegesecure/4.2/privilegesecure/accessmanagement/admin/dashboard/window/locksession.md) topic for additional information.

- Activity — Displays the name of the activity. Click the link to view additional details. See the
  [Activities Page](/docs/privilegesecure/4.2/privilegesecure/accessmanagement/admin/policy/page/activities.md) topic for additional information.

The table columns can be resized and sorted in ascending or descending order.

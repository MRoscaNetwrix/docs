---
title: Active Dashboard
sidebar_label: active sessions
description: Reviewer role documentation including audit capabilities, access certification, session monitoring, and approval workflows.
---

# Active Dashboard

The Active sessions dashboard shows all currently active sessions. Create an Activity Session to
grant temporary privileges and gain access to the resources defined by a previously created Access
Policy.

![Active Dashboard](/img/versioned_docs/privilegesecure_4.1/privilegesecure/accessmanagement/revieweruser/dashboard/reviweractivedashboard.webp)

The Active Sessions table has the following features:

- Search — Searches the table or list for matches to the search string. When matches are found, the
  table or list is filtered to the matching results.
- Create Session — Open the Activity Request window. See the
  [Create My Activity Session](/docs/privilegesecure/4.1/reviewer-guide/accessing-resources/create-session.md)
  topic for additional information.
- End Session — Cancel the selected session(s)
- View Logs — Opens the Session Logs window to view the action log for the selected session. See the
  [Session Logs Window](/docs/privilegesecure/4.1/reviewer-guide/accessing-resources/session-logs.md)
  topic for additional information.
- Refresh — Reload the information displayed

The table has the following columns:

- Checkbox — Check to select one or more items
- Expand icon — Click the expand () icon to show additional information for the session
- Status — Shows status information for the session:

  - Provisioning — Pre-Session stage of the Activity is processing and assigning permissions to
    the login account
  - Waiting for Approval — The session requires approval to begin. See the
    [Approvals Dashboard](/docs/privilegesecure/4.1/reviewer-guide/dashboard/approvals.md)
    topic for additional information.
  - Available — The activity session is ready. Click the icon to begin the session, or log in
    through a client. See the
    [Start Activity Session](/docs/privilegesecure/4.1/reviewer-guide/accessing-resources/start-session.md)
    topic for additional information.
  - Failed — Pre-Session stage of the Activity has encountered an error
  - Logged In — User is successfully logged in to the Resource either directly or via the Proxy.
    Direct log-in is detected by polling the Resource at regular intervals and may not update
    immediately.
  - Canceling — The session is either expired or was canceled manually by the user or an Privilege
    Secure administrator.
  - Locked — The session has been locked by an Privilege Secure administrator

- Requested — Date and time of when the session was created
- Host — Resource that the user will run the activity on
- Login Account — Displays the account used to log onto the resource
- Activity — Displays the name of the activity.
- Start — Indicates when the activity started. This refers to when the activity’s actions were
  executed and not when the user was logged on to the resource.
- End — Indicates when the session is scheduled to end the activity, which is determined by the
  start time plus the maximum session duration set by the access policy Connection Profile

The table columns can be resized and sorted in ascending or descending order.

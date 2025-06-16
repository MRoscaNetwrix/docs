# Default Role Details Page

The Role Management page is accessible from the Navigation pane under Users & Group. It provides
details on all available roles for Privilege Secure users. There are default roles, and custom roles
can be created.

![rolemanagementpage](../../../../../../../../../static/img/product_docs/privilegesecure/privilegesecure/accessmanagement/admin/policy/page/rolemanagementpage.webp)

When a default role (Administrator, User, or Reviewer) is selected, the selected role details
display at the top of the main pane with the following features:

- Name — Name of the access policy
- Search — Searches the table or list for matches to the search string. When matches are found, the
  table or list is filtered to the matching results.
- Filter — Provides options to filter results based on a chosen criterion: User, Group, Application,
  Collection, and Local User
- Add User — The Add options change based on the selected role:

    - Administrator — Opens the Add Administrators window. See the
      [Add Administrators Window](../../window/usersgroups/addadministrators.md) topic for
      additional information.
    - Users — Opens a list of available user types to add

        - New Domain Users — Opens the Add Users and Groups window. See the
          [Add Users & Groups Window](../../window/usersgroups/addusersandgroups.md) topic for
          additional information.
        - New Application User — Opens the Add Application page. See the
          [Add Application](../../add/application.md) for additional information.
        - New Local User — Opens the Add Local User page. See
          [Add Local User](../../add/localuser.md) topic for additional information.

    - Reviewers — Opens the Add Reviewers window. See the
      [Add Reviewers Window](../../window/usersgroups/addreviewers.md) topic for additional
      information.

- Remove — Removes console access from the selected account
- Refresh — Reload the information displayed

The table has the following columns:

- Checkbox — Check to select one or more items
- Type — Icon indicates the type of object
- Name — Displays the name of the account. Click the link to view additional details. See the
  [User, Group, & Application Details Page](usergroupapplication.md) topic for additional
  information.
- User Name — Displays the sAMAccountName for the account
- Email — Displays the associated email address, if available
- Last Login — Date timestamp for the last time the user logged into the application

The table columns can be resized and sorted in ascending or descending order.

## Default Role Permissions

The default roles provide users with the following permissions:

- Administrators — Grants access to all Privilege Secure Console configuration options
- Users — Creates sessions based on assigned access policy. This role is automatically assigned when
  a user is onboarded.
- Reviewers — Grants ability to review access entitlement. See the
  [Access Certification Page](../../../auditreporting/page/accesscertification.md) topic for
  additional information.

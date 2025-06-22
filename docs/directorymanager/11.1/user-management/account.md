# Account page

(of Create User and Create Mailbox wizards)

Use this page to specify basic account info, such as the user's first name, last name, login ID and
the UPN suffix.

Step 1 – Click **Browse** next to the Container box to select a container to create the user in.

This field would be read-only if the administrator has predefined a container for creating new
users.

Step 2 – Enter the user's First Name, Initials, and Last Name in the respective boxes.

Step 3 – The wizard uses the provided information to populate the Full Name, Display Name, User
logon name, and User logon name (pre-windows 2000) boxes. You can modify this information, if
required.

- The pre-Windows 2000 user logon name cannot exceed 24 characters. This name is used for logging on
  to computers running Windows 95, Windows 98, or Windows NT.

- The logon name is the user ID the user will use to log into the identity store.

Step 4 – The UPN Suffix box displays the UPN suffix for the user account. This is the name of the
domain the connected identity store is running on. An example of a UPN suffix can be 'mydomain.com'.

When a domain user account is created, the complete domain account comprises of a user logon name
followed by '@' and then the domain name.

Step 5 – Click **Next**.

# Account page

(of Microsoft Entra ID User and Mailbox wizards)

Use this page to specify basic account info, such as the user's first name, last name, login ID and
the UPN suffix.

Step 1 – Click **Browse** next to the Container box to select a container to create the user in.

Step 2 – Enter the user's first name and last name in the respective boxes.

Step 3 – The wizard uses the provided information to populate the Display Name and User logon name
boxes. You can modify this information, if required.

The logon name is the user ID the user will use to log into the identity store.

Step 4 – The UPN Suffix box displays the UPN suffix for the user account. This is the name of the
domain the identity store is running on. An example of a UPN suffix can be 'mydomain.com'.

When a domain user account is created, the complete domain account comprises of a user logon name
followed by '@' and then the domain name.

Step 5 – Click **Next**.

# User properties - Account tab

This tab enables administrators to manage the account status and expiry policy of a user.

Account Expires

Set the account expiry policy for the user.

- Never – To set this user account to never expire. This is the default option for new users.
- End Of – To set this user account to expire on a specified date. Use the calendar selector to
  enter the expiry date for the user account.

Account is disabled

Select this check box to disable the user account, so that the user cannot log-on with it.

Account is locked out

This check box will be selected when this user account is locked, for example, due to failed logon
attempts. Clear this check box to unlock the account.

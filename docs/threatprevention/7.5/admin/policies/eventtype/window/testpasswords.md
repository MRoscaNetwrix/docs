---
title: Test Passwords Window
sidebar_label: Test Passwords Window
description: The Test Password window enables users to test the password complexity requirements set in the Password Rules Filter against a pending password.
---

# Test Passwords Window

The Test Password window enables users to test the password complexity requirements set in the
[Password Rules Filter](/docs/threatprevention/7.5/admin/policies/eventtype/passwordenforcement.md#password-rules-filter) against a pending password.
This window does not change a user’s password but allows pending user passwords to be tested in the
domain.

![Test Passwords Window](/img/product_docs/threatprevention/threatprevention/admin/policies/eventtype/window/testpasswords.webp)

This window has the following options:

- _(Optional)_ Username – Provide the username of the user
- Password – Enter the password that will be tested
- Available Agents – Lists the available Agents in the domain and their version in a dropdown menu
- Test on Selected Agent – Checks password complexity requirements against the Agent selected in the
  Available Agents dropdown menu
- Results – Displays whether the tested password failed or passed the complexity requirements set on
  the Password Rules filter

Password Test Result - Passed

![passwordtestpassed](/img/product_docs/threatprevention/threatprevention/admin/policies/eventtype/window/passwordtestpassed.webp)

Password Test Result - Does Not Pass

![passwordtestfailed](/img/product_docs/threatprevention/threatprevention/admin/policies/eventtype/window/passwordtestfailed.webp)

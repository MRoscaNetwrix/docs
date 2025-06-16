# Prevent Weak Passwords Use Case

Any Threat Prevention license can use the Password Enforcement Event type to prevent the creation of
weak passwords in your environment.

**NOTE:** The Threat Prevention Enterprise Password Enforcement solution includes an EPE User
Feedback module. See the
[ Enterprise Password Enforcer](/versioned_docs/threatprevention_7.4/threatprevention/solutions/epe.md)
topic for additional information.

Follow the steps to configure a policy to block the creation of weak passwords.

![EPE Settings window](/img/versioned_docs/threatprevention_7.4/threatprevention/admin/configuration/epesettings.webp)

**NOTE:** It is a best practice to create and enable a monitoring policy prior to creating and
enabling a blocking policy. See the
[Monitor Weak Passwords Use Case](/versioned_docs/threatprevention_7.4/threatprevention/admin/policies/eventtype/usecase/monitorweakpasswords.md)
topic for additional information.

**Step 1 –** (Must be completed by an administrator) Configure the global EPE settings for your
environment.

- Click **Configuration** > **EPE Settings** on the menu to open the EPE Settings window.
- Download the latest copy of the HaveIBeenPwned dictionary file. See the
  [Download and Configure the Have I Been Pwnd Hash List](/versioned_docs/threatprevention_7.4/threatprevention/admin/configuration/epesettings.md#download-and-configure-the-have-i-been-pwnd-hash-list)
  topic for additional information.
- Determine whether you want to deploy the dictionary to each domain controller or keep it locally
  on the Enterprise Manager server. See the
  [Considerations When Deploying the HIBP Database](/versioned_docs/threatprevention_7.4/threatprevention/admin/configuration/epesettings.md#considerations-when-deploying-the-hibp-database)
  topic for additional information.
- Modify the global password rules to customize the password dictionary, word list dictionary and
  character substitution map. See the
  [Rules](/versioned_docs/threatprevention_7.4/threatprevention/admin/configuration/epesettings.md#rules)
  topic for additional information.

**Step 2 –** Create a new policy with the Password Enforcement Event Type.

![New Prevent Weak Passwords Policy - General tab](/img/versioned_docs/threatprevention_7.4/threatprevention/admin/policies/eventtype/usecase/newblockepepolicy.webp)

- Right-click on the **Policies > Auditing** folder and select **New > Policy**.
- On the General tab, provide a unique descriptive name, e.g. Prevent Weak Passwords, and
  description, e.g. This policy blocks the creation of weak passwords according to the global
  EPE settings.
- On the Event Type tab, click the **Add** (+) button and select Password Enforcement on the
  [Event Selection Window](/versioned_docs/threatprevention_7.4/threatprevention/admin/policies/eventtype/overview.md#event-selection-window).

![Policy - Event Type tab with the Password Enforcement event selected](/img/versioned_docs/threatprevention_7.4/threatprevention/admin/policies/eventtype/usecase/passwordrulesblock.webp)

**Step 3 –** Configure the event filters.

- Password Rules tab:

    - Mode – Set to Blocking
    - Pwned DB – Check the Block if password hash is in Pwned DB box
    - Character Substitution – Check the Block if exact match substituted password box
    - Username in Password – Check all options in this category and modify values as desired
    - Repeating Patterns – Check the Block if password contains repeating pattern box and set length
      value as desired
    - Sequential Characters – Check the Block if contains sequential characters box and set size
      value as desired
    - Keyboard Layout Sequence – Check the Block if contains characters in keyboard layout sequence
      box and set size value as desired
    - Configure additional settings as desired

- Optionally scope the policy further by applying Domain/Servers, AD Account, AD Perpetrator, and/or
  Hosts (from) filters.

**Step 4 –** Return to the General tab and enable the policy by clicking the Disabled toggle button.

**Step 5 –** Click **Save**.

The policy is now preventing the creation of weak passwords in your environment. There are three
methods for viewing prevented weak password events:

- Recent Events tab of the blocking policy
- Investigate node of the Administration Console
- Investigations interface of the Netwrix Threat Manager Reporting Module

## View Events in Recent Events Tab

On the Recent Events tab of the blocking policy, set the Show options as desired and click the
Refresh button to view blocked events. See the
[Recent Events Tab](/versioned_docs/threatprevention_7.4/threatprevention/admin/policies/recentevents/overview.md)
topic for additional information.

![Recent Events Tab for weak password prevent](/img/versioned_docs/threatprevention_7.4/threatprevention/admin/policies/eventtype/usecase/recenteventsprevent.webp)

## View Events in Investigate Interface

![Investigate Interface](/img/versioned_docs/threatprevention_7.4/threatprevention/admin/policies/eventtype/usecase/invesitgatenodeblock.webp)

On the Investigate window of the Administration Console, use the following filter options to view
blocked weak password events:

- Policy filter – Select only the policy that is blocking weak passwords
- Other filter – Select the Event Name option and enter "password rejected" in the text box.

Click the Refresh button to view blocked events. See the
[Investigate Interface](/versioned_docs/threatprevention_7.4/threatprevention/admin/investigate/overview.md)
topic for additional information.

## View Events in Investigations Interface

On the Investigations interface of the Netwrix Threat Manager Reporting Module, create a new
investigation with the following filter:

- Attribute = Policy
- Operator = Equals
- Filter = [name of blocking policy]

See the
[Investigations Interface](/versioned_docs/threatprevention_7.4/threatprevention/reportingmodule/investigations/overview.md)
topic for additional information.

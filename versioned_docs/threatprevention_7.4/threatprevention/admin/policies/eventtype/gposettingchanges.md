# GPO Setting Changes Event Type

The GPO Setting Changes event type generates events based on rules for specified (or all) GPOs, to
report what setting(s) in a GPO are modified.

The event filters for the GPO Setting Changes event type are:

- AD Group Policy Object Changes
- AD Perpetrator
- Advanced Filter

![Policy window - GPO Setting Changes Event Type](/img/versioned_docs/threatprevention_7.4/threatprevention/admin/policies/eventtype/gposettingchanges.webp)

Each filter tab acts like an "AND" statement for the filter. Any filter tab left blank is treated
like an "ALL" for that filter set.

## AD Group Policy Object Changes Filter

Use the AD Group Policy Object Changes filter to set the scope of the policy to monitor specific
GPOs.

![Policy window - AD Group Policy Object Changes filter](/img/versioned_docs/threatprevention_7.4/threatprevention/admin/policies/eventtype/adgrouppolicyobjectchanges.webp)

In the Operations section, select the **All** checkbox to include all operations or select specific
operations:

- Create
- Delete
- Modify

In the Group Policy Objects section, scope to specific GPOs:

- Watch All Group Policy Objects – Includes all GPOs
- List – Scopes to the specified GPOs

    - The **Add** (+) button opens the
      [Select Active Directory Group Policy Objects Window](/versioned_docs/threatprevention_7.4/threatprevention/admin/policies/eventtype/window/selectactivedirectory/grouppolicyobjects.md).
    - The Remove (x) button deletes the selected item(s) from that box.

## AD Perpetrator Filter

Use the AD Perpetrator filter for monitoring to set the scope of the policy to only monitor specific
security principals committing changes or to exclude specific security principals committing changes
from being monitored.

![Event Type - AD Perpetrator Monitoring filter](/img/versioned_docs/threatprevention_7.4/threatprevention/admin/policies/eventtype/adperpetratormonitoring.webp)

Use the buttons in the Include Perpetrators, Include Collections, Exclude Perpetrators, and Exclude
Collections areas to edit the lists.

- The Perpetrators Add (+) button opens the
  [Select Active Directory Perpetrators Window](/versioned_docs/threatprevention_7.4/threatprevention/admin/policies/eventtype/window/selectactivedirectory/perpetrators.md).
- The Collection button opens the
  [List of Collections Window](/versioned_docs/threatprevention_7.4/threatprevention/admin/configuration/collectionmanager/listcollections.md)
  to the appropriate Collection category.
- The Remove (x) button deletes the selected item(s) from that box.

**NOTE:** To enable a Dynamic Policy, use the Collection button to select the desired Dynamic
Collection. See the
[Dynamic Collections](/versioned_docs/threatprevention_7.4/threatprevention/admin/configuration/collectionmanager/dynamic.md)
topic for additional information.

Sub Tree

![Sub-Tree option in event type filters](/img/versioned_docs/threatprevention_7.4/threatprevention/admin/policies/eventtype/subtree.webp)

When contexts are added, a Sub-Tree checkbox displays. Check it to apply the filter to the parent
and all child contexts. Uncheck it to apply the filter to the listed context only.

## Advanced Filter

Use the Advanced Filter to include or exclude attribute conditions for GPO setting changes.

![Policy window - Advanced Filter](/img/versioned_docs/threatprevention_7.4/threatprevention/admin/policies/eventtype/advanced.webp)

Filter statements can be added to the Include condition and Exclude condition boxes. The filter uses
pre-defined logical and comparison operators to create filter criteria for the scan. Conditions can
be singular or grouped by a logical operator.

Logical Operator

The logical operator displays as left aligned red text. To apply more filters to the set or start a
new group of filters, click the **Add** (+) icon. To change the logical operator, click on it to
open a menu with the following options:

- And
- Or
- Not And
- Not Or
- Add Condition
- Add Group
- Cleat All

On clicking the **Add** (+) icon, a new row is inserted that displays a column (attribute), a
comparison operator, and a Value box.

Column Selection

The selected column is displayed in blue text. Click on it to open a menu with all available columns
from the GPO Setting Changes Recent Events data grid.

Comparison Operator

The comparison operator is displayed in green text. To change it, click on it to open a menu with
options that associate with the data in the GPO Setting Changes Recent Events data grid.

Filter Criteria

Specify a filter criteria into the `<enter a value>` textbox.

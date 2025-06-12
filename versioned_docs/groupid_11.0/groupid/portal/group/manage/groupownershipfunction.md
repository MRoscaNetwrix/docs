# Group Ownership Functions

The GroupID portal enables you to perform ownership related functions such as change primary owner of a group, specify additional owner(s) of a group, import/export additional owner and so on.

When a new group is created; by default, the group creator is set as its primary owner. However, you can change the primary owner or even remove it, leaving the group orphan.

You cannot remove a group’s primary owner if the Group Owners policy for your role does not allow it.

## Additional owners

You can also specify temporary and permanent additional owners for a group. These can be users, contacts and even security groups. In case of a group, all its members will be considered as additional owners.

You can change the ownership type of an additional owner from temporary to permanent and vice versa.

Additional owners have the same privileges as the primary owner to manage the group. Group expiry, deletion, and renewal notifications are sent to the additional owners along with the primary owner. However, you can exclude some or all additional owners
from receiving email notifications.

By default, there is no restriction on the number of additional owners a group can have. However, if the administrator has specified a maximum and minimum value for additional owners in the Group Owners policy for your role in the identity store, you cannot create a group or save modifications to it unless it has the specified number of additional owners.

## Exchange 2013/2016/2019 additional owners

Microsoft Exchange 2013/2016/2019 offers the co-managed by feature that enables you to specify Exchange additional owners for a group, provided that Exchange 2013/2016/2019 is configured as the messaging provider for the identity store. Exchange additional owners are stored in the _msExchangecoManagedby_ attribute.

GroupID sends group expiry, deletion, and renewal notifications to all Exchange additional owners along with the group’s primary owner and additional owners.

NOTE: For email notifications to be sent, an SMTP server must be configured for the connected identity store.

NOTE: Only users, contacts and security groups can be set as the primary and additional owners of a group. Moreover, only mail-enabled users can be set as Exchange additional owners.

NOTE: Note the following for a Microsoft Entra ID based identity store:

- Only users can be set as primary owners.
- Microsoft Entra ID supports multiple primary owners for a group.
- At least one primary owner is mandatory.
- Exchange additional owners are not supported.

What do you want to do?

- [Change a group's primary owner](#change-a-groups-primary-owner)
- [Set additional owners for a group](#set-additional-owners-for-a-group)
- [Import additional owners for a group](#import-additional-owners-for-a-group)
- [Export additional owners](#export-additional-owners)
- [Change an additional owner’s ownership type](#change-an-additional-owners-ownership-type)
- [Set Exchange additional owners](#set-exchange-additional-owners)

## Change a group's primary owner

1. In GroupID portal, click __Groups__ in the left navigation pane, select __My Groups__.

   The Groups page is displayed with the __My Groups__ tab in view.
2. Select the required group and click __Properties__ on the toolbar.
3. The group's properties page is displayed.
4. On the [Group properties - Owner tab](/versioned_docs/groupid_11.0/groupid/portal/group/properties/owner.md), the __Owner__ box displays the group's primary owner.

   To change the primary owner, click __Browse__ to launch the [Find Dialog Box](/versioned_docs/groupid_11.0/groupid/portal/search/find.md), where you can search and select another owner.
5. Save the changes.

## Set additional owners for a group

You can add and remove additional owners for a group.

Additional owners have the same privileges as the primary owner to manage the group.

NOTE: Only users, contacts and security groups can be set as the additional owners of a group.  
 If you specify a group, all its members are considered additional owners.

NOTE: The contact object type is not supported in a Microsoft Entra ID based identity store.

If the administrator has specified the Group Owner policy for the identity store, it may have an impact on the number of additional
owners the group can have.

1. In GroupID portal, click __Groups__ in the left navigation pane, select __My Groups__.

   The Groups page is displayed with the __My Groups__ tab in view.
2. Select the required group and click __Properties__ on the toolbar.
3. The group's [Group Properties](/versioned_docs/groupid_11.0/groupid/portal/group/properties/overview.md) page is displayed.
4. On the [Group properties - Owner tab](/versioned_docs/groupid_11.0/groupid/portal/group/properties/owner.md), click __Add__ in the __Additional Owners__ area.
5. Enter a search string to locate the object to add as an additional owner, or click __Advanced__ to use the [Find Dialog Box](/versioned_docs/groupid_11.0/groupid/portal/search/find.md) for performing a search.
6. By default, all group-related notifications (such as group expiry, deletion, and renewal notifications) are sent to the primary owner and all additional owners. To exclude an additional owner from receiving notifications, select the __Do not notify__ check box.

   NOTE: When a Smart Group Update job runs on a group, the notification behavior is as follows:

   Even with the __Do not Notify__ check box selected, the additional owner will receive the notifications if the administrator has included its email address for job-specific notifications.
7. Save the changes.

## Import additional owners for a group

1. In GroupID portal, click __Groups__ in the left navigation pane, select __My Groups__.

   The Groups page is displayed with the __My Groups__ tab in view.

   Or

   [Directory Search](/versioned_docs/groupid_11.0/groupid/portal/search/search.md) a group to import its additional owners from an external file.
2. Select the required from the list. and click __Properties__ on the toolbar.

   The group's [Group Properties](/versioned_docs/groupid_11.0/groupid/portal/group/properties/overview.md) page is displayed.
3. On the [Group properties - Owner tab](/versioned_docs/groupid_11.0/groupid/portal/group/properties/owner.md), click __Import__ to launch the __Import Additional Owners__ wizard.
4. See [Import Additional Owners](/versioned_docs/groupid_11.0/groupid/portal/group/properties/importadditionalowners.md) for further information and instructions.
5. Save the changes.

## Export additional owners

You can export additional owners of a group to an external file.

1. In GroupID portal, click __Groups__ in the left navigation pane, select __My Groups__.

   The Groups page is displayed with the __My Groups__ tab in view.

   Or

   [Directory Search](/versioned_docs/groupid_11.0/groupid/portal/search/search.md) a group to export its additional owners to an external file.
2. Select the group and click __Properties__ on the toolbar.

   The group's [Group Properties](/versioned_docs/groupid_11.0/groupid/portal/group/properties/overview.md) page is displayed.
3. On the __Owner__ tab, click __Export__ to launch the __Export Additional Owners__ wizard.
4. On the __Attributes__ page:

   1. In the __Attributes__ list, select the required directory attributes and move them to the __Selected Attributes__ list.

      Additional owners' data for the selected attributes is exported in the output file.
   2. Click __Next__.
5. On the __File Type__ page, select the file type to export the data to. Supported file types are:

   - Microsoft Excel (.xls and .xlsx)
   - Comma Separated Value (.csv)
   - Extensible Markup Language (.xml)
   - Text (.txt)
6. Click __Finish__.
7. When the file is successfully generated, you can save it to your machine.

## Change an additional owner’s ownership type

Ownership type indicates whether an object is a temporary or permanent additional owner of a group. You can change the ownership type of an additional owner from temporary to permanent and vice versa.

1. [Directory Search](/versioned_docs/groupid_11.0/groupid/portal/search/search.md) a group to change the ownership type of its additional owner(s).
2. Select this group on the Search Results page and click __Properties__ on the toolbar.
3. On the group's [Group Properties](/versioned_docs/groupid_11.0/groupid/portal/group/properties/overview.md) page, click the __Owner__ tab.
4. To change the ownership type of an additional owner, click anywhere in the respective row to make it editable, and select an option from the __Ownership__ list:

   - __Perpetual__ - To make the object a permanent additional owner of the group.
   - __Temporary Owner__ - To make the object a temporary additional owner of the group for the period you specify in the __Beginning__ and __Ending__ boxes. At the end of the period, the object is removed from the group ownership.
   - __Addition Pending__ - Indicates that the object will be a temporary additional owner of the group for a period in the future. Use the __Beginning__ and __Ending__ boxes to set a period. Before the beginning
     date, the object’s ownership type is displayed as ‘Addition Pending’. On the beginning date, the ownership type changes to ‘Temporary Owner’.

     __Here is an example:__

     You add Smith as a temporary additional owner of Group A on May 15, 2019 for future dates, May 20-30, 2019.

     Smith will be listed with Group A’s additional owners with ‘Addition Pending’ as its ownership type from May 15 to 19, 2019.

     On May 20, Smith will become a temporary additional owner of Group A and its ownership type will change to ‘Temporary Owner’ from May 20 to 30, 2019.

     After May 30, Smith will be removed from Group A as an additional owner.
   - __Removal Pending__ - Indicates that the object will be temporarily removed from group ownership for a period in the future. Use the __Beginning__ and __Ending__ boxes to set a period. Before the beginning
     date, the object’s ownership type is displayed as ‘Removal Pending’. On the beginning date, the ownership type will change to ‘Temporary Removed’.

     __Here is an example:__

     You remove Smith as an additional owner of Group A on May 15, 2019 for future dates, May 20-30, 2019.

     Smith will be displayed as Group A’s additional owner with ‘Removal Pending’ as ownership type from May 15 to 19, 2019.

     On May 20,
     Smith’s ownership type in GroupID will change to ‘Temporary Removed’; lasting till May 30, 2019.

     After May 30, Smith will be added back to Group A as a permanent additional owner.
   - __Temporary Removed__ - Indicates that the object is temporarily removed from group ownership for the period specified in the __Beginning__ and __Ending__ boxes. At the end of the period, the object is added
     back to the group as a permanent additional owner.
5. Save the changes.

The Managed By Life Cycle job updates the temporary ownership of groups by adding and removing temporary additional owners on the specified
dates.

Consider a scenario where the Managed By Life Cycle job is scheduled to run once a week, say Mondays. If an object is to be added as a group’s temporary additional owner for three days - Wednesday till Friday, it will not be added. This happens because
the Managed By Life Cycle job did not run on the particular days for temporary ownership update.

## Set Exchange additional owners

If your portal is connected to an identity store having Exchange Server

2013/2016/2019 deployed; then you can specify Exchange additional owners for a group. Exchange additional owners have the same privileges as the primary owner. GroupID sends
group expiry, deletion, and renewal notifications to all Exchange additional owners along with the group’s primary owner and additional owners.

Microsoft Exchange 2013/2016/2019 offers the co-managed by feature that enables you to specify Exchange additional group owners.

1. In GroupID portal, click __Groups__ in the left navigation pane, select __My Groups__.

   The Groups page is displayed with the __My Groups__ tab in view.
2. Select the required group and click __Properties__ on the toolbar.
3. The group's [Group Properties](/versioned_docs/groupid_11.0/groupid/portal/group/properties/overview.md) page is displayed.
4. On the __Email__ tab, click __Add__ in the __Managed By__ area.
5. Enter a search string to locate the object to add as an Exchange additional owner, or click __Advance__ to use the [Find Dialog Box](/versioned_docs/groupid_11.0/groupid/portal/search/find.md) for performing a search.

   NOTE: Only mail-enabled users can be set as Exchange additional owners.
6. Save the changes on the __Email__ tab.

__See Also__

- [Working with Groups](/versioned_docs/groupid_11.0/groupid/portal/group/manage/workingwithgroups.md)

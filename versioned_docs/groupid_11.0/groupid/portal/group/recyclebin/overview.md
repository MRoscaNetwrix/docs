# Deleted Groups

GroupID Portal handles group deletion as either physical or logical.

## Tombstone Groups

Physically deleted groups have Tombstone as type. Physical group deletion refers to manually deleting groups using the __Delete__ option on the __Actions__ menu or shortcut menu. GroupID moves a physically deleted it to the Recycle
Bin while stripping it of most of its properties. You can delete or restore a group from the Recycle Bin. The restoration process not only restores the group to its original container, but it also reinstates the home container for the group, if deleted.

When restored, a physically deleted group is restored with limited attributes; its membership is not restored.

A Smart Group and Dynasty is restored as a static group with no members and no query.

NOTE: Tombstone groups are not available in Microsoft Entra ID.

## Logical Deletion

Groups that are deleted by the Group Lifecycle job are considered to be logically deleted. The job deletes expired groups X number of days after group expiry, as specified in Group
Lifecycle policy settings.

Upon deletion, logically deleted groups are moved to the Recycle Bin, with all their attributes intact. As a result, a logically deleted group, when restored, returns to its state it had at the time of deletion. The restoration process not only restores
the group to the container from where it was deleted but it also reinstates the home container for the group, if deleted.

You can also manually delete a logically deleted group in the Recycle Bin, making it physically deleted. Simply select the required group and select Delete on the shortcut menu.

## Deletion notifications

When the Group Lifecycle job deletes a group, it notifies the group owners or, if there is no owner, the default approver specified in the Group Lifecycle policy.

What do you want to do?

- [Modify Search Directory](#Modify-Search-Directory)
- [Filter Deleted Groups](#Filter-Deleted-Groups)
- [Delete a group from Recycle Bin](#Delete-a-group-from-Recycle-Bin)
- [Restore a deleted group](#Restore-a-deleted-group)

## Modify Search Directory

You can modify the search results in __Modify Search Directory__. You can select entire directory or a domain to search deleted groups from.

## Filter Deleted Groups

You can add filters while searching for specific deleted groups from Tombstone or Logically Deleted Groups.

1. Click __Add Filter__ to specify a criterion for filtering deleted groups.
2. From the __Select a Filter__ list, select the attribute to filter deleted groups.
3. Two more boxes get displayed next to __Select a Filter__ box upon selecting a filter.

   - __Select an Operator__ from the first list.
   - Specify a value for the selected operator in the second box.
4. Click __Apply Filter__.

   Deleted Groups that match the specified criterion are displayed.
5. You can add additional filters by clicking __Add Filter__.
6. To undo the filters, click __Reset Filter.__ It will remove all the criteria set before.

## Delete a group from Recycle Bin

1. In GroupID Portal, select __Groups > Deleted Groups__ from the left pane.
2. From the groups list, select one or more groups.
3. Click __Delete__ on the shortcut menu.

The group / groups will be permanently deleted from the recycle bin.

## Restore a deleted group

1. In GroupID Portal, select __Groups > Deleted Groups__ from the left pane.
2. From the groups list, select one or more groups.
3. Click __Restore__ on the shortcut menu.

The group / groups will be restored in the directory.

NOTE: You can only restore a physically deleted group from the Recycle Bin if the service account for the connected identity store has the ‘Reanimate Tombstone’ permissions.

NOTE: While all searches in GroupID are catered through Elasticsearch, the Recycle Bin is an exception, as it fetches data from the directory.

NOTE: The Recycle Bin does not display data for a Microsoft Entra ID based identity store.

__See Also__

- [Create Active Directory Groups](/versioned_docs/groupid_11.0/groupid/portal/group/create/activedirectory/group.md)
- [Create an Active Directory Dynasty](/versioned_docs/groupid_11.0/groupid/portal/group/dynasty/activedirectory/createdynasty.md)
- [Group Properties](/versioned_docs/groupid_11.0/groupid/portal/group/properties/overview.md)
- [Directory Search](/versioned_docs/groupid_11.0/groupid/portal/search/search.md)

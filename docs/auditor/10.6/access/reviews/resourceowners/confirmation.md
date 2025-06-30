# Ownership Confirmation

The reason for assigning owners to resources is to enable those resources to be included in reviews,
or attestations, conducted through the application. In order for this to work, the assigned owner
needs to claim that ownership responsibility. Resources that do not have confirmed owners may fall
through the cracks.

**NOTE:** This does require the Notification settings to be configured for the Access Reviews
application. See the
[Notifications Page](/docs/auditor/10.6/access/reviews/admin/configuration/notifications.md)
topic for additional information.

![Table in Resource Owners interface showing several resources being managed and all confirmation status icons](/img/versioned_docs/auditor_10.6/access/reviews/resourceowners/tablestatus.webp)

The table in the Resource Owners interface includes a Status column. The following icons appear in
this column to indicate the owner confirmation status:

| Icon                                                                                                                        | Meaning   | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| --------------------------------------------------------------------------------------------------------------------------- | --------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| ![Yellow circle with whit question mark](/img/versioned_docs/auditor_10.6/access/reviews/resourceowners/statusnostatus.webp) | No Status | Indicates ownership confirmation has not been requested, and there is no ownership status at this time                                                                                                                                                                                                                                                                                                                                                                                                        |
| ![Blue circle with white clock face](/img/versioned_docs/auditor_10.6/access/reviews/resourceowners/statuswaiting.webp)      | Waiting   | Indicates a request for confirmation has been sent, and you are waiting for a response from the assigned owner. Hover over the icon to view the date timestamp of the request.                                                                                                                                                                                                                                                                                                                                |
| ![Green circle with white checkmark](/img/versioned_docs/auditor_10.6/access/reviews/resourceowners/statusconfirmed.webp)    | Confirmed | Indicates the assigned owner confirmed ownership of the resource. Hover over the icon to view the date timestamp of the confirmation.                                                                                                                                                                                                                                                                                                                                                                         |
| ![Red circle with white X](/img/versioned_docs/auditor_10.6/access/reviews/resourceowners/statusdeclined.webp)               | Declined  | Indicates the assigned owner declined ownership of the resource. These individuals would have been asked to suggest an alternative owner. Check the Notes for the resource to view this information. Hover over the icon to view the date timestamp of the decline. _Remember,_ a resource with declined ownership needs to be updated to assign a new owner. See the [Update Resource Wizard](/docs/auditor/10.6/access/reviews/resourceowners/wizard/update.md) topic for additional information. |

If multiple owners have been assigned, there is a choice for which assigned owner(s) should receive
the confirmation. If multiple owners were sent the request, the column remains as a waiting symbol
until the assigned Primary owner replies.

See the
[Confirm Ownership Wizard](/docs/auditor/10.6/access/reviews/resourceowners/wizard/confirm.md)
topic for additional information.

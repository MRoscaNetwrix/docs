# Custom Notifications

Custom notifications can be configured for specific needs, to be triggered by a workflow, or
periodically via a task.

## Workflow-Triggered Notifications

A notification can be configured to be sent to one or several users right after the execution of a
given activity in a
[workflow](/docs/identitymanager/6.1/integration-guide/workflows/index.md).

> For example, when a user is created in Usercube through a workflow, a notification can be sent to
> the user's manager. A notification can also be sent when someone must process an action for a
> workflow to continue.

The configuration is made through the XML tag
[`NotificationAspect`](/docs/identitymanager/6.1/integration-guide/toolkit/xml-configuration/workflows/aspects/notificationaspect/index.md).

## Periodic Notifications

A notification can be configured to be sent to a given user on a regular basis at specified times,
through the
[`SendNotificationsTask`](/docs/identitymanager/6.1/integration-guide/toolkit/xml-configuration/jobs/tasks/server/sendnotificationstask/index.md)
as part of a job.

> For example, a notification can be sent automatically to remind a manager that someone arrives in
> their team a month before the arrival, and again a week before.

The configuration is made through the XML tag
[`Notification`](/docs/identitymanager/6.1/integration-guide/toolkit/xml-configuration/notifications/notification/index.md).

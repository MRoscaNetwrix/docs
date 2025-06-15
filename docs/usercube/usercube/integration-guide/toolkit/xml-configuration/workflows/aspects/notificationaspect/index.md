# Notification Aspect

Sends a notification email to one or several users.

## Examples

The following example sends a notification email based on the template ```Notification_Directory_Guest.cshtml``` and the subject computed by ```SubjectExpression_L1```, which both use data from ```Workflow_Directory_Guest:Directory_Guest```, and on the styles from ```Notification_Directory_Guest.css```.

```

<NotificationAspect Identifier="Notification_Directory_Guest" ExpressionBinding="Workflow_Directory_Guest:Directory_Guest" RazorFile_L1="./Templates/Notification_Directory_Guest.cshtml" CssFile="./Templates/Notification_Directory_Guest.css" SubjectExpression_L1="C#:guest:return &quot;Validating data for guest: &quot; + guest.FirstName + guest.LastName;">
    <PointCut Activity="Directory_Guest_AdvancedStart:Request" ActivityState="ActionWithRefine-Executed" Mode="After" />    <Recipient Type="Binding" Binding="Directory_Guest:Mail" /></NotificationAspect>

```

The notification will be sent after the ```Request``` activity of the ```Directory_Guest_AdvancedStart``` workflow is executed.  
The notification will be sent to all email addresses defined by ```Directory_Guest:Mail```.

## Properties

| Property | Details |
| --- | --- |
| Identifier   required | __Type__    String   __Description__   Unique identifier of the aspect. |
| Binding   optional | __Type__    String   __Description__   Binding whose difference with ```ExpressionBinding``` defines the property that corresponds to identities' email addresses, when ```Type``` is set to ```Binding```. |
| CssFile   optional | __Type__    String   __Description__   Path to the css file that defines the styles for the email.   __Note:__ the path must be relative to the configuration folder, and the file must be inside it. |
| ExpressionBinding   optional | __Type__    String   __Description__   Binding:   - that defines the variable type used in the potential expressions specified in the aspect;   - whose difference with ```Binding``` defines the property involved in the aspect.   __Note:__ required when handling the property of multi-valued objects, for example records, to make sure to modify the property in all records and not only in one. |
| Priority   default value: 0 | __Type__    Int32   __Description__   Execution priority among all aspects. At a given activity state, the aspect with the highest priority will be triggered first.   __Note:__ the priority can be a negative value. |
| RazorFile_L1   optional | __Type__    String   __Description__   Path to the Razor cshtml file that defines the email's body template in language 1 (up to 16).   __Note:__ the path must be relative to the configuration folder, and the file must be inside it. |
| SubjectExpression_L1   optional | __Type__    String   __Description__   C# expression that defines the email's subject in language 1 (up to 16). The expression's variable type is defined in ```ExpressionBinding```. |

## Child Element: PointCut

A pointcut is a mechanism telling Identity Manager when to execute the linked [Aspects](../index.md).

The position of the pointcut is specified by an activity state and a mode (before or after).

![pointcut Schema](../../../../../../../../../static/img/product_docs/usercube/usercube/integration-guide/toolkit/xml-configuration/workflows/aspects/addchangeaspect/pointcut.webp)

| Property | Details |
| --- | --- |
| Activity   required | __Type__    Int64   __Description__   Identifier of the activity whose specified state triggers the aspect. |
| ActivityState   required | __Type__    Enumeration   __Description__   Identifier of the activity state that triggers the aspect. |
| Mode   default value: 0 | __Type__    PointCutMode   __Description__   Mode defining when exactly the aspect is triggered around the specified workflow's activity state.   ```0``` - __Before__: the aspect will be executed on entry to the specified activity state, regardless of the transition used.   ```1``` - __After__: the aspect will be executed on exit from the specified activity state, regardless of the transition used. |

## Child Element: Recipient

A recipient defines one or several identities who will receive a notification from ```NotificationAspect```.

### Examples

The following example sends a notification email to the actors of the next step of the workflow.

```

<NotificationAspect Identifier="Notification_Directory_User" ExpressionBinding="Workflow_Directory_User:Directory_User" RazorFile_L1="Template/Notification_Directory_User.cshtml" CssFile="Template/Notification_Directory_User.css">  <PointCut Activity="Directory_User_StartInternal:Request" ActivityState="ActionWithRefine-Executed" Mode="After" />
  <Recipient Type="Actor" />
</NotificationAspect>

```

The following example sends a notification email to the performers of the ```Request``` activity of the ```Directory_User_StartInternal``` workflow when the state is ```Executed```.

```

<NotificationAspect Identifier="Notification_Directory_User" ExpressionBinding="Workflow_Directory_User:Directory_User" RazorFile_L1="Template/Notification_Directory_User.cshtml" CssFile="Template/Notification_Directory_User.css">  <PointCut Activity="Directory_User_StartInternal:Request" ActivityState="ActionWithRefine-Executed" Mode="After" />
  <Recipient Type="Performer" Activity="Directory_User_StartInternal:Request" ActivityState="ActionWithRefine-Executed" />
</NotificationAspect>

```

The following example sends a notification email to the email address, stored in ```Mail```, of the user(s) from ```Directory_User``` targeted by the workflow, so here the new user created by the ```Directory_User_StartInternal``` workflow.

```

<NotificationAspect Identifier="Notification_Directory_User" ExpressionBinding="Workflow_Directory_User:Directory_User" RazorFile_L1="Template/Notification_Directory_User.cshtml" CssFile="Template/Notification_Directory_User.css">  <PointCut Activity="Directory_User_StartInternal:Request" ActivityState="ActionWithRefine-Executed" Mode="After" />
  <Recipient Type="Binding" Binding="Directory_User:Mail" />
</NotificationAspect>

```

The following example sends a notification email to all identities whose email addresses are defined as ```{lastName}@company.com```.

```

<NotificationAspect Identifier="Notification_Directory_User" ExpressionBinding="Workflow_Directory_User:Directory_User" RazorFile_L1="Template/Notification_Directory_User.cshtml" CssFile="Template/Notification_Directory_User.css">  <PointCut Activity="Directory_User_StartInternal:Request" ActivityState="ActionWithRefine-Executed" Mode="After" />
  <Recipient Type="Expression" Expression="C#:user:return user.LastName+"@company.com";" />
</NotificationAspect>

```

The following example sends a notification to all identities with a profile that includes the right permission.

```

<NotificationAspect Identifier="Directory_User_New" ExpressionBinding="Workflow_Directory_User:Directory_User" RazorFile_L1="Directory/User/Directory-User-Notification-New.cshtml" CssFile="Notifications.css">  <PointCut Activity="Directory_User_NewInternal:Persist" ActivityState="Persist-Invoked" Mode="After" />  <PointCut Activity="Directory_User_NewExternal:Persist" ActivityState="Persist-Invoked" Mode="After" />
  <Recipient Type="Profile" />
</NotificationAspect>

Knowing that we also have:
<Profile Identifier="Workforce/Notifications/Directory_User_New" DisplayName_L1="Workforce/Notifications/New User" IsComponent="true" /><AccessControlRule Profile="Workforce/Notifications/Directory_User_New" EntityType="Directory_User" Identifier="Composite_Notifications_Directory_User_New*" DisplayName_L1="Composite_Notifications_Directory_User_New*">
  <Entry Permission="/Custom/WorkflowsNotifications/Directory_User_NewInternal/Persist/Invoked" />  <Entry Permission="/Custom/WorkflowsNotifications/Directory_User_NewExternal/Persist/Invoked" />
</AccessControlRule>

```
| Property | Details |
| --- | --- |
| Activity   optional | __Type__    Int64   __Description__   Identifier of the activity whose last performers are to be notified, when ```Type``` is set to ```Performer```.   __Note:__ must be set together with ```ActivityState```. |
| ActivityState   optional | __Type__    Enumeration   __Description__   Identifier of the activity state whose last performers are to be notified, when ```Type``` is set to ```Performer```.   __Note:__ must be set together with ```Activity```. |
| Binding   optional | __Type__    Int64   __Description__   Binding of the property that represents the notification's recipients, when ```Type``` is set to ```Binding```. |
| EmailAddresses   optional | __Type__    String   __Description__   Email addresses of the notification's recipients, when ```Type``` is set to ```Hardcoded```. |
| Expression   optional | __Type__    String   __Description__   C# expression that returns the email addresses of the notification's recipients, as strings or `IEnumerable<string>`, when ```Type``` is set to ```Expression```. The expression's variable type is defined in ```ExpressionBinding``` in the associated ```NotificationAspect```. See the [Expressions](../../../../expressions/index.md) topic for additional information. |
| IsCC   default value: false | __Type__    Boolean   __Description__   ```true``` to send the notification email to the recipient(s) as a carbon copy (CC). |
| Type   required | __Type__    RecipientType   __Description__   Type of recipients for the email notification.   __Actor__: the identities with the permissions to act on the next step of the workflow specified in the pointcut.   __Performer__: the actors of a past workflow step specified in ```Activity``` and ```ActivityState```.   __Binding__: the identities whose email addresses are designated by the property specified in ```Binding```.   __Hardcoded__: the identities whose email addresses are specified explicitly in ```EmailAddresses```.   __Expression__: the identities whose email addresses match the C# expression specified in ```Expression```.   __Profile__: the identities with the permission ```/Custom/WorkflowsNotifications/{workflow_identifier}/```   ```{activity_identifier}/{activityTemplateState_shortIdentifier}```. |

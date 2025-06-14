# For Resource Update (Mono Record)

This section guides you through the procedure for the creation of a workflow to schedule the replacement of the unique record of an existing resource with a new one.

## Declare a Workflow

This [workflow](/versioned_docs/usercube_6.1/usercube/integration-guide/toolkit/xml-configuration/workflows/workflow/index.md) is made of two activities:

1. [```ActionWithRefine```](/versioned_docs/usercube_6.1/usercube/integration-guide/workflows/activity-templates/index.md#actionwithrefine): sends the resource's record update request with a possibility of delegation.
2. [```Persist```](/versioned_docs/usercube_6.1/usercube/integration-guide/workflows/activity-templates/index.md#persist): saves the collected data and triggers provisioning.

The example below creates a workflow to update only the user's name.

```

  <Workflow Identifier="Directory_User_ChangeName" DisplayName_L1="User - Update Name" VariablesType="Workflow_Directory_User">    <Activity Identifier="Request" DisplayName_L1="Request" Template="ActionWithRefine" />    <Activity Identifier="Persist" DisplayName_L1="Commit" Template="Persist" />  </Workflow>

```

For now, our workflow works with an immediate validation and an immediate effect.

## Create Forms

The XML configuration below represents the creation of a [form](/versioned_docs/usercube_6.1/usercube/integration-guide/toolkit/xml-configuration/user-interface/form/index.md) that defines the elements to display in the workflow.

Here we just have the full name field to update the corresponding attributes for a given user:

```

<Form Identifier="Workflow_Directory_User_ChangeName_Base" EntityType="Workflow_Directory_User">  <Control DisplayName_L1="Full Name" OutputType="LayoutRowset" EntityType="Directory_UserRecord">    <Control Binding="LastName" />    <Control Binding="FirstName" />  </Control></Form>

```

## Link the Forms to the Workflow

After creating a workflow with given activities, it is necessary to create the form to be displayed when launching the workflow. It has the type corresponding to a (unique) record's replacement, i.e. ```WorkflowAddAndEndRecordEntityForm``` and it must specify the workflow's context (the entity type of the involved resources, the main property, the activity when the form is called, etc. [see more details](/versioned_docs/usercube_6.1/usercube/integration-guide/toolkit/xml-configuration/user-interface/form/index.md)):

```

<WorkflowAddAndEndRecordEntityForm Identifier="Workflow_Directory_User_ChangeName" EntityType="Workflow_Directory_User" MainProperty="Workflow_Directory_User:Directory_User" RecordProperty="Directory_User:Records" WorkflowRequestType="Self" Activity="Directory_User_ChangeName:Request" HideRoles="true" FormTitle_L1="Change Name"></WorkflowAddAndEndRecordEntityForm>

```

A ```WorkflowAddAndEndRecordEntityForm``` requires the following child elements:

- ```MainControl``` that defines user's data;

```

<WorkflowAddAndEndRecordEntityForm Identifier="Workflow_Directory_User_ChangeName_Base" EntityType="Workflow_Directory_User" MainProperty="Workflow_Directory_User:Directory_User" RecordProperty="Directory_User:Records" WorkflowRequestType="Self" Activity="Directory_User_ChangeName:Request" HideRoles="true" FormTitle_L1="Change Name">
  <MainControl OutputType="LayoutContainer"/>
</WorkflowAddAndEndRecordEntityForm>

```

The ```MainControl``` attribute is here an empty container, because it is a mandatory attribute that is not involved in the changes of this workflow.

- ```RecordControl``` that defines record data, and call the form created previously.

```

<WorkflowAddAndEndRecordEntityForm Identifier="Workflow_Directory_User_ChangeName" EntityType="Workflow_Directory_User" MainProperty="Workflow_Directory_User:Directory_User" RecordProperty="Directory_User:Records" WorkflowRequestType="Self" Activity="Directory_User_ChangeName:Request" HideRoles="true" FormTitle_L1="Change Name" >  <MainControl OutputType="LayoutContainer"/>
  <RecordControl OutputType="TransformImport" EmbeddedForm="Workflow_Directory_User_ChangeName_Base" />
</WorkflowAddAndEndRecordEntityForm>

```

![UI Form](/img/versioned_docs/usercube_6.1/usercube/integration-guide/workflows/how-to/workflow-update-mono/howto_resourceupdatemono_form_v603.png)

```End of transition``` sets the date for the change of records scheduled by this form.

## Assign the Right Permissions

Some profiles must get specific permissions so that the workflow is visible and usable by the right users.
Read about [workflows' permissions](/versioned_docs/usercube_6.1/usercube/integration-guide/workflows/index.md#workflows-permissions).

Below is an example of an access control rule where the ```Administrator``` profile gets the permissions for the whole update request from the previously created workflow:

```

<AccessControlRule Profile="Administrator" EntityType="Workflow_Directory_User" Identifier="Administrator_Workflows_Directory_User_*" DisplayName_L1="Administrator_Workflows_Directory_User_*">  <Entry Permission="/Custom/Workflows/Directory_User_ChangeName/Request/ActionPending" CanExecute="true" />  <Entry Permission="/Custom/Workflows/Directory_User_ChangeName/Request/RefinePending" CanExecute="true" />  <Entry Permission="/Custom/Workflows/Directory_User_ChangeName/Request/Aborted" CanExecute="true" />  <Entry Permission="/Custom/Workflows/Directory_User_ChangeName/Request/Purged" CanExecute="true" /></AccessControlRule>

```

## Create Menu Items in the UI

[Menu items](/versioned_docs/usercube_6.1/usercube/integration-guide/toolkit/xml-configuration/user-interface/menuitem/index.md) must be defined to make the workflow accessible in the UI.

Updating an existing resource, this workflow manages one given resource at a time. Hence an interesting location for this workflow could be the individual view page of users.

![Workflow Menu Items - User's Page](/img/versioned_docs/usercube_6.1/usercube/integration-guide/workflows/how-to/workflow-update-mono/menuitems_userview_v603.png)

To create a menu item here for the new workflow, you can add the following XML configuration to the existing [menu items list](/versioned_docs/usercube_6.1/usercube/integration-guide/ui/how-tos/create-menu-items/index.md#menu-items-list):

```

<MenuItem Identifier="Menu_Directory_User" DisplayName_L1="Menu">  <MenuItem Identifier="Menu_Directory_User_Changes" DisplayName_L1="Actions">    <MenuItem Identifier="Menu_Directory_User_Changes_Update" DisplayName_L1="Section">      ...
      <MenuItem Identifier="Menu_Directory_User_Changes_ChangeName" DisplayName_L1="Update Name" IconCode="Edit" Workflow="Directory_User_ChangeName" />
    </MenuItem>  </MenuItem></MenuItem>

```

## Add Aspects

For each workflow, it is possible to add [aspects](/versioned_docs/usercube_6.1/usercube/integration-guide/workflows/index.md#aspects) according to the workflow's purpose.

## Homonym Detection (Optional)

To perform a homonymy check on a workflow and thus prevent user duplicates, read [how to configure a homonym detection](/versioned_docs/usercube_6.1/usercube/integration-guide/workflows/how-to/configure-homonym-test/index.md).

When using records, the homonym detection displays the list of records and not just the list of users.

## Customize the Display Table (Optional)

To configure a display table different from the default one provided by Usercube, read [how to configure a display table](/versioned_docs/usercube_6.1/usercube/integration-guide/ui/how-tos/custom-display-table/index.md).

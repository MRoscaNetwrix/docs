# Create Menu Items

After creating a workflow as for the EntityTypes, is mandatory to create the MenuItems to create the Navigation to this Workflow.

### Create menu items for a workflow in a resource entity list

To add a link to an entity's workflow displayed under the search bar on the visualization page of the entity's resource list you need to create a menu containing the different workflows and put a link to the entity's searchBar as below.

[See available icons](https://uifabricicons.azurewebsites.net/).

The first MenuItem is the main action displayed on the right.

The other MenuItems are displayed from left to right.

```

  <SearchBar EntityType="Directory_User" Menu="Menu_Search_Directory_User" SearchBarDesignElement="Inline">    <Criterion Binding1="MainRecord.EmployeeId" PlaceHolderText_L1="Employee Id" PlaceHolderText_L2="Matricule" InputType="Auto" ColumnSize="2" />    <Criterion Binding1="MainRecord.LastName" InputType="Auto" ColumnSize="2" />    <Criterion Binding1="MainRecord.FirstName" InputType="Auto" ColumnSize="2" />    <Criterion Binding1="MainRecord.Organization" PlaceHolderText_L1="Department" PlaceHolderText_L2="D�partement" InputType="Auto" ColumnSize="2" />    <Criterion Binding1="PresenceState" InputType="ComboboxMultiSelection" ColumnSize="2" DefaultValue="-101;-102" Operator="Equal" />    <Criterion Binding1="MainRecord.Location" PlaceHolderText_L1="Site" PlaceHolderText_L2="Site" InputType="Auto" ColumnSize="2" IsVisibleInAdvancedView="true" />    <Criterion Binding1="MainRecord.Company" PlaceHolderText_L1="Company" PlaceHolderText_L2="Soci�t�" InputType="Auto" ColumnSize="2" IsVisibleInAdvancedView="true" />    <Criterion Binding1="MainRecord.Title" PlaceHolderText_L1="Title" PlaceHolderText_L2="Fonction" InputType="Auto" ColumnSize="2" IsVisibleInAdvancedView="true" />    <Criterion Binding1="MainRecord.EmployeeType.Category" PlaceHolderText_L1="User Type" PlaceHolderText_L2="Cat�gorie de collaborateur" InputType="Auto" ColumnSize="2" IsVisibleInAdvancedView="true" />  </SearchBar>  <MenuItem Identifier="Menu_Search_Directory_User" DisplayName_L1="Menu">    <MenuItem Identifier="Menu_Search_Directory_User_StartInternal" DisplayName_L1="New Employee" DisplayName_L2="Entr�e d'un interne" IconCode="AddFriend" Workflow="Directory_User_StartInternal" />    <MenuItem Identifier="Menu_Search_Directory_User_StartExternal" DisplayName_L1="New Contractor" DisplayName_L2="Entr�e d'un externe" IconCode="AddFriend" Workflow="Directory_User_StartExternal" />    <MenuItem Identifier="Menu_Search_Directory_User_AdvancedStartInternal" DisplayName_L1="New Multi-Positions User" DisplayName_L2="Entr�e multipostes" IconCode="AddFriend" Workflow="Directory_User_AdvancedStartInternal" />    <MenuItem Identifier="Menu_Search_Directory_User_Helpdesk_Start" DisplayName_L1="New User (helpdesk)" DisplayName_L2="Entr�e (support)" IconCode="AddFriend" Workflow="Helpdesk_Directory_User_Start" />  </MenuItem>

```

This XML element gives the following result:

![Add workflow link in resource list entity](/img/product_docs/usercube/usercube/integration-guide/ui/how-tos/create-menu-items/workflowinentitylist.webp)

### Create menu items for a workflow in a resource view

In the resource view it is also possible to create links to different workflows.

These workflows will manipulate the selected resource in the view.

```

  <ResourceViewRecordEntityForm Identifier="Directory_User_View" EntityType="Directory_User" Menu="Menu_Directory_User" RecordProperty="Directory_User:Records" RecordStartProperty="Directory_UserRecord:ContractStartDate" RecordEndProperty="Directory_UserRecord:ContractEndDate" RecordFilter="All" IsDefaultViewForm="true">    <MainControl OutputType="LayoutContainer"></MainControl>    <RecordControl OutputType="TransformImport" EmbeddedForm="Directory_UserRecord_View" />    <RecordItemControl OutputType="TransformImport" EmbeddedForm="Directory_UserRecord_ViewPosition" />    <RecordUniqueItemControl OutputType="TransformImport" EmbeddedForm="Directory_UserRecord_ViewPosition" />  </ResourceViewRecordEntityForm>  <MenuItem Identifier="Menu_Directory_User" DisplayName_L1="Menu">    <MenuItem Identifier="Menu_Directory_User_Changes" DisplayName_L1="Actions" DisplayName_L2="Actions">      <MenuItem Identifier="Menu_Directory_User_Changes_Add" DisplayName_L1="Section">        <MenuItem Identifier="Menu_Directory_User_Changes_AddRecord" DisplayName_L1="Add a new Position" DisplayName_L2="Ajouter un poste" IconCode="Add" Workflow="Directory_User_AddRecord" />        <MenuItem Identifier="Menu_Directory_User_Changes_AddContract" DisplayName_L1="Add a new Contract" DisplayName_L2="Ajouter un contrat" IconCode="Add" Workflow="Directory_User_AddContract" />      </MenuItem>      <MenuItem Identifier="Menu_Directory_User_Changes_Update" DisplayName_L1="Section">        <MenuItem Identifier="Menu_Directory_User_Changes_ChangePosition" DisplayName_L1="Schedule a Job Change" DisplayName_L2="Mouvement � date" IconCode="Edit" Workflow="Directory_User_ChangePosition" />        <MenuItem Identifier="Menu_Directory_User_Changes_ManageContract" DisplayName_L1="Manage Contract" DisplayName_L2="Gestion du contrat" IconCode="Edit" Workflow="Directory_User_ManageContract" />        <MenuItem Identifier="Menu_Directory_User_Changes_ChangeName" DisplayName_L1="Update Name" DisplayName_L2="Changer le nom" IconCode="Edit" Workflow="Directory_User_ChangeName" />        <MenuItem Identifier="Menu_Directory_User_Changes_ResourcesUpdate" DisplayName_L1="Modify Permissions" DisplayName_L2="Demander des droits" IconCode="Edit" Workflow="Directory_User_ResourcesUpdate" />        <MenuItem Identifier="Menu_Directory_User_Changes_Suspend" DisplayName_L1="Suspend" DisplayName_L2="Suspendre" IconCode="Edit" Workflow="Directory_User_Suspend" />        <MenuItem Identifier="Menu_Directory_User_AdvancedUpdate" DisplayName_L1="Multi-position Update" DisplayName_L2="Modification multipostes" IconCode="Edit" Workflow="Directory_User_AdvancedUpdate" />      </MenuItem>      <MenuItem Identifier="Menu_Directory_User_Changes_Directory_User_End" DisplayName_L1="Schedule the Exit" DisplayName_L2="Planifier le d�part" IconCode="Cancel" Workflow="Directory_User_End" />    </MenuItem>    <MenuItem Identifier="Menu_Directory_User_Helpdesk" DisplayName_L1="Helpdesk" DisplayName_L2="Support" IconCode="Phone">      <MenuItem Identifier="Menu_Directory_User_Helpdesk_Update" DisplayName_L1="Section">        <MenuItem Identifier="Menu_Directory_User_Helpdesk_FixRecord" DisplayName_L1="Repair Data (helpdesk)" DisplayName_L2="Corriger des donn�es (support)" IconCode="Edit" Workflow="Helpdesk_Directory_User_FixRecord" />      </MenuItem>      <MenuItem Identifier="Menu_Directory_User_Helpdesk_Delete" DisplayName_L1="Section">        <MenuItem Identifier="Menu_Directory_User_Helpdesk_Directory_User_Delete" DisplayName_L1="Delete User (helpdesk)" DisplayName_L2="Supprimer (support)" IconCode="Cancel" Workflow="Helpdesk_Directory_User_Delete" />      </MenuItem>    </MenuItem>  </MenuItem>

```

This XML element gives the following result:

![Workflow in resource view](/img/product_docs/usercube/usercube/integration-guide/ui/how-tos/create-menu-items/workflowinresourceview.webp)

![All workflow in resource view*](/img/product_docs/usercube/usercube/integration-guide/ui/how-tos/create-menu-items/allworkflowinresourceview.webp)

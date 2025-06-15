# Connector

Connectors provide the means by which Identity Manager communicates with managed platforms, applications and systems. They describe how the data from these systems are mapped to the [Entity Model](../../../../entity-model/index.md).

A connector in most case represents an application model. It is composed of entities and associations.

> For example we can define an HR connector, with the following entities: Person, Department, Function, Location, etc. and with the following associations: Person-Department, Person-Site, Person-Manager(Person), etc.

A connector is used to synchronize each of its entities and associations in Identity Manager's physical model. A connector is defined with:

- [
  Entity Type
  ](../../metadata/entitytype/index.md);
- [
  Entity Association
  ](../../metadata/entityassociation/index.md);
- [
  Entity Type Mapping
  ](../entitytypemapping/index.md) and [
  Entity Association Mapping
  ](../entityassociationmapping/index.md) to link the entity types and associations to the corresponding files and columns containing the exported data from the managed system.

## Examples

The following example creates a ```HR``` connector on the agent called ```Local``` previously declared by an [
Agent
](../agent/index.md) element.

We create the right [
Connection
](../connection/index.md) to use the connector as a [
CSV
](../../../../connectors/references-connectors/csv/index.md)aiming to export HR CSV files into new CSV files in Identity Manager's format.

The [
Entity Type
](../../metadata/entitytype/index.md) model the resources as ```HR_Person``` or ```HR_Organization```, defining properties.

The [
Entity Type Mapping
](../entitytypemapping/index.md) link the entity types to the source files.

The [
Entity Association
](../../metadata/entityassociation/index.md) creates a link between the two entity types.

The [
Entity Association Mapping
](../entityassociationmapping/index.md) links the association to the source files.

```

  <Connector Identifier="HR" DisplayName_L1="HR" Agent="Local" />  <Connection Connector="HR" DisplayName_L1="HR Organization" Package="Usercube.CSV.Complete@0000001" Identifier="HROrganizations"/>  <Connection Connector="HR" DisplayName_L1="HR Person" Package="Usercube.CSV.Complete@0000001" Identifier="HRPeople"/>  <EntityType Identifier="HR_Person" DisplayName_L1="HR - User">    <Property Identifier="Managed_organizations" DisplayName_L1="Managed organizations" Type="Int64" />    <Property Identifier="Assistant_of_organizations" DisplayName_L1="Assistant of organizations" Type="Int64" />    <Property Identifier="Employee_Id" DisplayName_L1="Employee Id" IsKey="true" TargetColumnIndex="0" Type="String" />    <Property Identifier="First_name" DisplayName_L1="First name" TargetColumnIndex="7" Type="String" />    <Property Identifier="Last_name" DisplayName_L1="Last name" TargetColumnIndex="8" Type="String" />    <Property Identifier="Birth_date" DisplayName_L1="Birth date" TargetColumnIndex="9" Type="String" />    <Property Identifier="Birth_name" DisplayName_L1="Birth name" TargetColumnIndex="13" Type="String" />    <Property Identifier="Personal_title" DisplayName_L1="Personal title" TargetColumnIndex="12" Type="String" />    <Property Identifier="Start_date" DisplayName_L1="Start date" TargetColumnIndex="10" Type="String" />    <Property Identifier="End_date" DisplayName_L1="End date" TargetColumnIndex="14" Type="String" />    <Property Identifier="VIP" DisplayName_L1="VIP" TargetColumnIndex="15" Type="String" />    <Property Identifier="Leave" DisplayName_L1="Leave" TargetColumnIndex="16" Type="String" />    <Property Identifier="Title_name" DisplayName_L1="Title name" TargetColumnIndex="1" Type="String" />    <Property Identifier="Location_name" DisplayName_L1="Site name" TargetColumnIndex="4" Type="String" />    <Property Identifier="Organization_name" DisplayName_L1="Organization name" TargetColumnIndex="2" Type="String" />    <Property Identifier="Organization" DisplayName_L1="Organization" TargetColumnIndex="131" Type="Int64" />  </EntityType>   <EntityType Identifier="HR_Organization" DisplayName_L1="HR - Department">    <Property Identifier="Identifier" DisplayName_L1="Code" IsKey="true" TargetColumnIndex="0" Type="String" />    <Property Identifier="Name" DisplayName_L1="Name" TargetColumnIndex="1" Type="String" />    <Property Identifier="Name_fr" DisplayName_L1="Name (fr)" TargetColumnIndex="3" Type="String" />    <Property Identifier="Name_de" DisplayName_L1="Name (de)" TargetColumnIndex="4" Type="String" />    <Property Identifier="Phone_number" DisplayName_L1="Phone number" TargetColumnIndex="5" Type="String" />    <Property Identifier="Fax_number" DisplayName_L1="Fax number" TargetColumnIndex="6" Type="String" />    <Property Identifier="Organization_type" DisplayName_L1="Organization type" TargetColumnIndex="7" Type="String" />    <Property Identifier="Location" DisplayName_L1="Site" TargetColumnIndex="8" Type="String" />    <Property Identifier="Parent_organization" DisplayName_L1="Parent organization" TargetColumnIndex="129" Type="Int64" />    <Property Identifier="Manager" DisplayName_L1="Manager" TargetColumnIndex="128" Type="Int64" />    <Property Identifier="Assistant" DisplayName_L1="Assistant" TargetColumnIndex="130" Type="Int64" />    <Property Identifier="Persons" DisplayName_L1="Persons" Type="Int64" />  </EntityType>  <EntityTypeMapping Identifier="HR_Person" Connector="HR" ConnectionTable="hr_people">    <Property Identifier="Employee_Id" ConnectionColumn="Employee Id" IsPrimaryKey="true" />    <Property Identifier="First_name" ConnectionColumn="First name" />    <Property Identifier="Last_name" ConnectionColumn="Last name" />    <Property Identifier="Birth_date" ConnectionColumn="Birth date" />    <Property Identifier="Birth_name" ConnectionColumn="Birth name" />    <Property Identifier="Personal_title" ConnectionColumn="Personal title" />    <Property Identifier="Start_date" ConnectionColumn="Start date" />    <Property Identifier="End_date" ConnectionColumn="End date" />    <Property Identifier="VIP" ConnectionColumn="VIP" />    <Property Identifier="Leave" ConnectionColumn="Leave" />    <Property Identifier="Title_name" ConnectionColumn="Title name" />    <Property Identifier="Location_name" ConnectionColumn="Location name" />    <Property Identifier="Organization_name" ConnectionColumn="Organization name" />  </EntityTypeMapping>  <EntityTypeMapping Identifier="HR_Organization" Connector="HR" ConnectionTable="hr_organizations">    <Property Identifier="Identifier" ConnectionColumn="Identifier" IsPrimaryKey="true" />    <Property Identifier="Name" ConnectionColumn="Name" />    <Property Identifier="Name_fr" ConnectionColumn="Name (fr)" />    <Property Identifier="Name_de" ConnectionColumn="Name (de)" />    <Property Identifier="Phone_number" ConnectionColumn="Phone number" />    <Property Identifier="Fax_number" ConnectionColumn="Fax number" />    <Property Identifier="Organization_type" ConnectionColumn="Organization type" />    <Property Identifier="Location" ConnectionColumn="Location" />  </EntityTypeMapping>  <EntityAssociation Identifier="HR_Person_Organization" DisplayName_L1="Organization" IsProperty1Collection="true" Property1="HR_Organization:Persons" Property2="HR_Person:Organization" />  <EntityAssociationMapping Identifier="HR_Person_Organization" Column1="Organization" Column2="Employee Id" Connector="HR" ConnectionTable="hr_people" EntityPropertyMapping1="HR_Organization:Identifier" EntityPropertyMapping2="HR_Person:Employee_Id" />

```

## Properties

| Property | Details |
| --- | --- |
| Agent   optional | __Type__    Int64   __Description__   Identifier of the agent where the connector's tasks are launched. |
| CompleteJob   default value: 0 | __Type__    JobIntegrationRule   __Description__   Indicates how the connector should be used in the complete job (scaffolding):   ```0``` - Used   ```1``` - NotUsed   ```2``` - OnlySynchronization   ```3``` - OnlyProvisioning   Warning: The job scaffolding has priority over the connector's decision.   For example, if your job scaffolding specifies that the Microsoft Entra ID is ```NotUsed``` for the complete job, setting that connector to ```Used``` for the complete job will not activate it. You should not only add the ```Used``` to the connector but also remove the ```NotUsed``` from the configuration of the job scaffolding. |
| DisplayName_L1   required | __Type__    String   __Description__   Connector DisplayName. |
| Identifier   required | __Type__    String   __Description__   Connector Identifier. |
| IncrementalJob   default value: 0 | __Type__    JobIntegrationRule   __Description__   Indicates how the connector should be used in the incremental job (scaffolding):   ```0``` - Used   ```1``` - NotUsed   ```2``` - OnlySynchronization   ```3``` - OnlyProvisioning   Warning: The job scaffolding has priority over the connector's decision.   For example, if your job scaffolding specifies that the Microsoft Entra ID is ```NotUsed``` for the incremental job, setting that connector to ```Used``` for the incremental job will not activate it. You should not only add the ```Used``` to the connector but also remove the ```NotUsed``` from the configuration of the job scaffolding. |
| IsDeactivated   default value: false | __Type__    Boolean   __Description__   Indicates that the export and the provisioning are deactivated for this connector. |
| MaximumDeletedLines   default value: 100 | __Type__    Int32   __Description__   Deleted lines threshold. Sets the maximum number of resources that can be removed from the connector when running the synchronization job. |
| MaximumInsertedLines   default value: 100 | __Type__    Int32   __Description__   Inserted lines threshold. Sets the maximum number of resources that can be added into the connector when running the synchronization job. |
| MaximumLinkDeletedLines   default value: 1000 | __Type__    Int32   __Description__   Deleted association links threshold. Sets the maximum number of navigation properties that can be removed from the connector when running the synchronization job. |
| MaximumLinkInsertedLines   default value: 1000 | __Type__    Int32   __Description__   Inserted association links threshold. Sets the maximum number of navigation properties that can be added into the connector when running the synchronization job. |
| MaximumUpdatedLines   default value: 100 | __Type__    Int32   __Description__   Updated lines threshold. Sets the maximum number of resources that can be modified within the connector when running the synchronization job. |
| MaxLinkPercentageDeletedLines   default value: 5 | __Type__    Int32   __Description__   Deleted association links threshold in percent. |
| MaxLinkPercentageInsertedLines   default value: 5 | __Type__    Int32   __Description__   Inserted association links threshold in percent. |
| MaxPercentageDeletedLines   default value: 5 | __Type__    Int32   __Description__   Deleted lines threshold in percent. |
| MaxPercentageInsertedLines   default value: 5 | __Type__    Int32   __Description__   Inserted lines threshold in percent. |
| MaxPercentageUpdatedLines   default value: 5 | __Type__    Int32   __Description__   Updated lines threshold in percent. |

# ReportQuery

Allows the user to define queries to generate a report in a CSV file. When creating a new ReportQuery it is recommended to also create the linked [MenuItem](/versioned_docs/usercube_6.1/usercube/integration-guide/toolkit/xml-configuration/user-interface/menuitem/index.md).

## Examples

```

  <ReportQuery Identifier="SingleRoles" ReturnedEntityType="SingleRole" Query="select Identifier, DisplayName" DisplayName_L1="Single Roles" />  <ReportQuery Identifier="ResourceTypes" ReturnedEntityType="ResourceType" Query="select Identifier, DisplayName" DisplayName_L1="Resource Types" />  <ReportQuery Identifier="PersonRecords" ReturnedEntityType="PersonRecord" Query="join Person Person join PersonalTitle PersonalTitle join EmployeeType EmployeeType select InternalDisplayName, PersonalTitle.DisplayName, LastName, FirstName, DisplayedCR, Login, DisplayedFonction, DisplayedEDS, EmployeeType.DisplayName, EmployeeType.Category" DisplayName_L1="Users" />

    <ReportQuery Identifier="SGS_Report" ReturnedEntityType="SGS_User" Query="join UserMetier metier join UserDepartement dpt join ResourceAssignedResourceTypes art join art.Owner of type Person person join person.Records personRecord join personRecord.EmployeeType employeeType join personRecord.Organization eds join personRecord.Fonction fonction join personRecord.Company cr select IDUser,NomPrenomUserSgs, metier.IDMetier, dpt.IDDepartement, person.Identifier, personRecord.FirstName, personRecord.LastName,employeeType.DisplayName,eds.DisplayName,fonction.DisplayName,cr.DisplayName" DisplayName_L1="SGS Accounts" />

    <ReportQuery Identifier="AD_Report" ReturnedEntityType="AD_Entry" Query="join memberOf memberof join ResourceAssignedResourceTypes art join art.Owner of type Person person join person.Records personRecord join personRecord.EmployeeType employeeType join personRecord.Organization eds join personRecord.Fonction fonction join personRecord.Company cr select sAMAccountName,memberof.dn, person.Identifier, personRecord.FirstName, personRecord.LastName, employeeType.DisplayName, eds.DisplayName, fonction.DisplayName,cr.DisplayName" DisplayName_L1="AD Entries" />

```

## Properties

| Property | Details |
| --- | --- |
| DisplayName_L1   required | __Type__    String   __Description__   Display name of the report query in language 1 (up to 16). |
| Identifier   required | __Type__    String   __Description__   Report query Identifier. |
| Query   required | __Type__    String   __Description__   The report query written following Usercube EBNF Grammar rules. |
| ReturnedEntityType   required | __Type__    Int64   __Description__   Returned Entity Type ID. The entity type can be seen as the FROM of a sql query. |

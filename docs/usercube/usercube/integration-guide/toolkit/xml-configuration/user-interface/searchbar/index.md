# Search Bar

The SearchBar is an element of the user interface that allows you to search from a list of properties of an EntityType.

## Examples

Code attributes enclosed with `<>` need to be replaced with a custom value before entering the script in the command line.

```
<SearchBar EntityType="Directory_User" Menu="Menu_Search_Directory_User" SearchBarDesignElement="Inline">    <Criterion Binding1="MainRecord.EmployeeId" PlaceHolderText_L1="Employee Id"  InputType="Auto" ColumnSize="2" />    <Criterion Binding1="MainRecord.LastName" InputType="Auto" ColumnSize="2" />    <Criterion Binding1="MainRecord.FirstName" InputType="Auto" ColumnSize="2" />    <Criterion Binding1="MainRecord.Organization" PlaceHolderText_L1="Department"  InputType="Auto" ColumnSize="2" /></SearchBar>
```

## Properties

| Property | Type | Description |
| --- | --- | --- |
| EntityType   required | Int64 | References the linked entity type. |
| Menu   optional | Int64 | References the linked Menu. Each Menu Item of this Menu is a link to an entity's workflow displayed under the search bar on the visualization page of the entity's resource list. |
| SearchBarDesignElement   required | Enumeration | Defines the type of the searchBar (Block,Inline). |
| SearchedBinding   optional | Int64 | Defines the binding on which the search will be applied. |
| SearchedEntityType   required | Int64 | Defines the entity type on which the search will be applied. |

## Child Element: Criterion

A SearchBarCriteria defines a search criterion on a given property. See the [Search Bar](#Search-Bar) topic for additional information.

### Properties

| Property | Type | Description |
| --- | --- | --- |
| ColumnSize   required | Int32 | Size of the insertion or selection element of the property. |
| DefaultValue   optional | String | Basic filter on the properties on the value or values entered in parameters. |
| DisplayName\_L1   optional | String | Display name of the criteria in language 1 (up to 16). |
| InputType   required | Enumeration | Type of the research property, supports only a predefined set of values listed below:   - Attachment - Auto - Checkbox - Combobox - ComboboxMultiSelection - Date - Hidden - Image - Inherited - Picker - Text - TextArea   See the [Form](/docs/usercube/usercube/integration-guide/toolkit/xml-configuration/user-interface/form/index.md) topic for additional information. |
| IsVisibleInAdvancedView   default value: false | Boolean | True to make the property visible in the advanced search but not in the main search properties. |
| Operator   default value: 0 | QueryComparisonOperator | Defines how to do the research. All possible values:   - Auto — The SearchOperator is calculated by the engine according to the type of element   - NotEqual — finds the elements that are not equal to the desired value   - Equal — finds the elements that are strictly equal to the desired value   - Contain — finds the elements that contain the desired value   - StartWith — finds the elements that start with the desired value   - EndWith — finds the elements that end with the desired value   - NotContain — finds the elements that do not contain the desired value   - NotStartWith — finds the elements that do not start with the desired value   - NotEndWith — finds the elements that do not end with the desired value   - GreaterThan — finds the elements that are greater than the desired value   - LessThan — finds the elements that are less than the desired value   - GreaterThanOrEqual — finds the elements that are greater than or equal to the desired value   - LessThanOrEqual — finds the elements that are less than or equal to the desired value   - Flexible\* — The Flexible search operators transform the desired value according to the FlexibleComparisonExpression defined in Property then search.  The flexible operators are:    - FlexibleEqual    - FlexibleContain    - FlexibleStartWith    - FlexibleEndWith |
| OptimizedBinding1   optional | Int64 | Represents the first optimized binding definition.   An optimized binding allows searches to be faster displayed. If it is filled in, it takes priority over the binding located in the search bar criterion column. |
| PlaceHolderText\_L1   optional | String | Overloads the DisplayName of the search property with this string. |
| ToolTipText\_L1   optional | String | Text displayed in the tool tip. |

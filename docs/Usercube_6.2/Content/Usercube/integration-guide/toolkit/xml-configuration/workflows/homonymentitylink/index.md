---
sidebar_position: 825
title: Homonym Entity Link
---

# Homonym Entity Link

This entity is used to configure the homonym workflow.

## Examples

```


```
In this example the homonym is linked to a [Form](../../user-interface/form/index "Form") and it will be applied for the [Binding](../../metadata/binding/index) included in the Control where the homonym is located. Read more about how to configure [Workflow Homonym](../../../../workflows/workflowhomonym/index).

```
                                                

```
## Properties

| Property | Details |
| --- | --- |
| FormEntityType required | **Type**  Int64  **Description** In a [Form](../../user-interface/form/index), an [Entity Type](../../metadata/entitytype/index "Entity Type") is defined and the [Binding](../../metadata/binding/index) of this Form will be loaded from this EntityType. The FormEntityType property represents this EntityType. |
| Identifier required | **Type**  String  **Description** Unique identifier of the HomonymEntityLink. |

## Child Element: Filter

Defines combination of property comparison to use to find homonyms.

### Properties

| Property | Details |
| --- | --- |
| ComparisonProperty1 optional | **Type**  Int64  **Description** Defines the property used to compare with the form control `Property`. It should not be defined if it the same as the property in the attribute `Property`. Going from 1 to 5. |
| Expression1 optional | **Type**  String  **Description** Defines the C# expression to apply on the homonymy form controls. The result of the expression evaluation will be compared with the corresponding `ComparisonProperty` using the defined `Operator`. If the `ComparisonProperty` is a computed property, no need to define the expression if it is the same as the one for the computed property. It will be automatically used when finding homonyms. Going from 1 to 5. See the [C# utility functions](../../../expressions/csharp-utility-functions/index "C# utility functions") topic for additional information. |
| Operator1 default value: 2 | **Type**  QueryComparisonOperator  **Description** Defines the operator to use to compare between the `ComparisonProperty` and the `Property` or the `Expression` evaluation result. By default the `Equal` operator is used. Going from 1 to 5. All possible values:  `0` - Auto: The `Operator` is calculated by the engine according to the type of element. `1` - NotEqual: finds the elements that are not equal to the desired value. `2` - Equal: finds the elements that are strictly equal to the desired value. `3` - Contain: finds the elements that contain the desired value. `4` - StartWith: finds the elements that start with the desired value. `5` - EndWith: finds the elements that end with the desired value. `6` - NotContain: finds the elements that do not contain the desired value. `7` - NotStartWith: finds the elements that do not start with the desired value. `8` - NotEndWith: finds the elements that do not end with the desired value. `9` - GreaterThan: finds the elements that are greater than the desired value. `10` - LessThan: finds the elements that are less than the desired value. `11` - GreaterThanOrEqual: finds the elements that are greater than or equal to the desired value. `12` - LessThanOrEqual: finds the elements that are less than or equal to the desired value. `*`- Flexible: The `Flexible` operators transform the desired value according to the `FlexibleComparisonExpression` defined in the `EntityProperty` then search. The flexible operators are: `13` - FlexibleEqual `14` - FlexibleContain `15` - FlexibleStartWith `16` - FlexibleEndWith |
| Property1 optional | **Type**  Int64  **Description** Defines the form control property to use to compare with `ComparisonOperator` using the defined `Operator`. Going from 1 to 5. |
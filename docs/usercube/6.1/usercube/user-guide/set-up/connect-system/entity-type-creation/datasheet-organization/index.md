# Organize Resources' Datasheets

How to change the default display of the resource data from this entity type, by creating display
groups.

## Overview

Here you will learn how to change how a resource's data is organized in the UI, by creating display
groups.

If you do not add display groups, Usercube displays the data of this entity type's resources in
alphabetic order.

> For example, for an HR user without any display groups:
>
> ![Without Display Groups](/img/versioned_docs/usercube_6.1/usercube/user-guide/set-up/connect-system/entity-type-creation/datasheet-organization/entitytypecreation_displaygroups_without_v603.webp)

## Organize Resources' Datasheets

Organize resources' datasheets by proceeding as follows:

1. Start by creating the entity type with its
   [scalar properties](/versioned_docs/usercube_6.1/usercube/user-guide/set-up/connect-system/entity-type-creation/scalar-property-definition/index.md)
   and
   [keys](/versioned_docs/usercube_6.1/usercube/user-guide/set-up/connect-system/entity-type-creation/key-selection/index.md).
2. Ensure that the created properties are saved by clicking on **Save & Close** > **Save** at the
   top right corner.
3. On the entity type's definition page, click on the **Display** tab.

    ![Display Groups](/img/versioned_docs/usercube_6.1/usercube/user-guide/set-up/connect-system/entity-type-creation/datasheet-organization/entitytypecreation_displaygroups_v603.webp)

4. Click on the arrow to see the entity type's properties listed in the alphabetical order, and drag
   and drop the properties to customize the order.

    > For example:
    >
    > ![Display Example](/img/versioned_docs/usercube_6.1/usercube/user-guide/set-up/connect-system/entity-type-creation/datasheet-organization/entitytypecreation_displaygroups_example1_v603.webp)

5. When needing to group properties together, click on **Add Display Group**, fill in the fields and
   select from the pop-up window the properties to be grouped.

    ![Display Group Fields](/img/versioned_docs/usercube_6.1/usercube/user-guide/set-up/connect-system/entity-type-creation/datasheet-organization/entitytypecreation_displaygroups_fields_v603.webp)

    - `Identifier`: must be unique among display groups, without any whitespace, and be
      C#-compatible.
      [See Microsoft lexical structure](https://learn.microsoft.com/en-us/dotnet/csharp/language-reference/language-specification/lexical-structure#see-microsoft-lexical-structure).
    - `Name`: will be displayed in the UI to indicate the property group.
        > For example:
        >
        > ![Display Example](/img/versioned_docs/usercube_6.1/usercube/user-guide/set-up/connect-system/entity-type-creation/datasheet-organization/entitytypecreation_displaygroups_example2_v603.webp)
        >
        > The entity type's resources would look like:
        >
        > ![Display Example](/img/versioned_docs/usercube_6.1/usercube/user-guide/set-up/connect-system/entity-type-creation/datasheet-organization/entitytypecreation_displaygroups_example2results_v603.webp)

6. Click on **Save & Close**.

    Changes in display groups won't take effect until the next
    [`Update-EntityPropertyExpressionsTask`](/versioned_docs/usercube_6.1/usercube/integration-guide/toolkit/xml-configuration/jobs/tasks/server/updateentitypropertyexpressionstask/index.md)
    runs.

## Reload

Every time an entity type mapping is modified and saved, a green pop-up appears saying that you
should reload the schema to implement the changes. You do not need to click on the button every
time. It is essential though to reload after the final changes are made.

![Reload](/img/versioned_docs/usercube_6.1/usercube/user-guide/set-up/connect-system/entity-type-creation/key-selection/entitytypecreation_reload_v522.webp)

The **Reload** button mostly enables your changes to appear in the menu items, which configure the
left menu links on the UI's home page.

You can find the **Reload** button either on the green warning, or on the connector's dashboard.

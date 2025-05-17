---
sidebar_position: 643
title: Create the Entity Type
---

# Create the Entity Type

How to create the technical container of an [Entity Type](../../../../../integration-guide/toolkit/xml-configuration/metadata/entitytype/index).

## Overview

Here, you will learn how to create an [Entity Type](../../../../../integration-guide/toolkit/xml-configuration/metadata/entitytype/index): the shell that harbors the (scalar and navigation) properties which describe a given set of resources related to one managed system.

## Create the Entity Type

Create the entity type by proceeding as follows:

1. Access the connector's page by clicking on the **Connectors** button on the home page in the **Configuration** section, then on the relevant connector.

   ![Home page - Connectors](../../../../../../../../../static/images/Usercube_SaaS/Content/Resources/Images/Home_connectors_V602.png)
2. On the connector's page, in the **Entity Types** frame, click on the addition button.

   ![Addition Icon](../../../../../../../../../static/images/Usercube_SaaS/Content/Resources/Images/iconAdd_V602.svg)
3. Fill in the information fields.

   ![Entity type creation](../../../../../../../../../static/images/Usercube_SaaS/Content/Resources/Images/EntityTypeCreation_entityTypeCreation_V602.png)

   * `Identifier`: must be unique among entity types, without any whitespace, and be C#-compatible. [See Microsoft lexical structure](https://learn.microsoft.com/en-us/dotnet/csharp/language-reference/language-specification/lexical-structure#643-identifiers). NETWRIX recommends using `_` in the singular.
   * `Name`: will be displayed in the UI to identify the entity type.
   * `Icon`: can be chosen from [Microsoft's list](https://uifabricicons.azurewebsites.net/) and will be displayed with the entity type in the left menu of the home page.
   * `Auto Complete in Pickers`: can be set once properties are created (and saved) so that, when using a searchbar for selected properties, Identity Manager suggests existing entries.
4. In the entity type's **Properties** section, choose a source so that the connection provides the source's data structure.

   ![Properties' source](../../../../../../../../../static/images/Usercube_SaaS/Content/Resources/Images/EntityTypeCreation_propertiesSource_V522.png)

   > Let's use the example of an AD connector. We create an entity type `AD - Entry` to gather the valuable information from the AD, i.e. all the AD entries (groups and accounts) which we want to classify, with the properties that are useful for assignment management.
   >
   > The AD connector uses as a source `Connection Active Directory - entries`. Its structure was retrieved when we refreshed the schemas of the `Active Directory` [Create a Connection](../../connection-creation/index), thus retrieving the attributes from the Active Directory and storing them temporarily on the agent side, inside CSV files.

## Next Steps

To continue,[Define Scalar Properties](../scalar-property-definition/index)for this entity type.

## Troubleshooting

If there are no connection tables available in the **Source** dropdown list of an entity type, then:

![Properties' source](../../../../../../../../../static/images/Usercube_SaaS/Content/Resources/Images/EntityTypeCreation_propertiesSource_V522.png)

Ensure that there are existing connections:

* if this is the case, then click on **Refresh all schemas** on the connector page, and verify that there is no error. See the [Create a Connection](../../connection-creation/index) topic for additional information.
* if not, then you must create at least one connection.

If there is a message stating to refresh the connection's schema, then:

![No Connection Table Error](../../../../../../../../../static/images/Usercube_SaaS/Content/Resources/Images/EntityTypeCreation_troubleshootingSchema_V603.png)

Start by making sure that the connection's schema is refreshed by clicking on **Refresh all schemas** on the connector page, and verify that there is no error.

If the message is still displayed, then it means that the previously selected connection table no longer exists in the managed system. In this case, either the table's name simply changed, or the table is not relevant anymore. Then you should find a relevant table in the **Source** dropdown list.
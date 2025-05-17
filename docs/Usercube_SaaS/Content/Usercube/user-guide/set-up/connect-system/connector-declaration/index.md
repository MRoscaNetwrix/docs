---
sidebar_position: 636
title: Create the Connector
---

# Create the Connector

How to declare the technical container of a [Connector](../../../../integration-guide/toolkit/xml-configuration/connectors/connector/index).

## Overview

Here, you will learn how to create a connector: the shell that harbors entity types and connections related to a single managed system.

:::note
Keep in mind that a Identity Manager installation can have more than one agent. Connectors should be created with a specific agent in mind since the agent needs to physically connect to the managed system's data. Fortunately, you don't need to worry about that right now, since you are starting with the agent provided with Identity Manager's SaaS environment. See the
Architecture
topic for additional information.
:::

## Participants and Artifacts

For a given managed system, integrators may need the help of the application owner who knows the purpose of the application.

| Input | Output |
| --- | --- |
| - | Empty connector |

## Create a Connector Container

Create a connector container by proceeding as follows:

1. On the home page in the **Configuration** section, click on the **Connectors** button.

   ![Home page - Connectors](../../../../../../../../static/images/Usercube_SaaS/Content/Resources/Images/Home_connectors_V602.png)

   You will see all existing connectors.
2. Click on the addition icon and fill in the information fields.

   ![Addition Icon](../../../../../../../../static/images/Usercube_SaaS/Content/Resources/Images/iconAdd_V602.svg)

   ![Connector creation](../../../../../../../../static/images/Usercube_SaaS/Content/Resources/Images/ConnectorCreation_declaration_V602.png)

   * `Identifier`: must be unique among connectors, without any whitespace, start with a letter, and contain only letters, numbers, `.` and/or `-`.
   * `Name`: will be displayed in the UI to identify the connector.
   * `Agent`: agent that the connector is supposed to use.

     Netwrix Identity Manager (formerly Usercube)recommends choosing the provided SaaS agent.
   * `Complete Job`: [Jobs](../../../../integration-guide/tasks-jobs/jobs/index) scheduled to perform a set of tasks, including completesynchronization and/or provisioning for all the connectors, for which you selected the corresponding checkbox.
   * `Incremental Job`: [Jobs](../../../../integration-guide/tasks-jobs/jobs/index) scheduled to perform frequently a set of tasks, including incrementalsynchronization and/or provisioning for all the connectors, for which you selected the corresponding checkbox.
3. Click on **+ Create** to get on the connector's overview page:

   ![Connector page](../../../../../../../../static/images/Usercube_SaaS/Content/Resources/Images/ConnectorCreation_connectorPage_V602.png)

## Verify the Connector Declaration

In order to verify the process, check that the connector has been added to the connectors list with the right name and identifier.

![Test Connector](../../../../../../../../static/images/Usercube_SaaS/Content/Resources/Images/ConnectorCreation_test_V602.png)
---
sidebar_position: 647
title: Create a Category
---

# Create a Category

How to structure roles into categories. See the [Category](../../../../integration-guide/toolkit/xml-configuration/provisioning/category/index "Category") topic for additional information.

## Overview

A category is usually created to:

* reflect the validation process, i.e. represent groups of roles that follow the same validation process with the same validator(s);
* help users find intuitively the entitlement that they are looking for.

> For example, creating one category per application often fulfills both requirements.

There is usually one validator per category.

There can be several category levels. For example, integrators can choose to create one category per department, then one per position, and finally one per application. They usually gather roles by application. Here are a few examples of categories: `AD`, `HR` , `SAP`, `IT Administration`, `Test Environments`, etc. Some of these "application categories" are gathered into larger categories by theme as long as their role owner is identical.

## Participants and Artifacts

For a given managed system, integrators may need the help of the application owners who know the application's users, entitlements and data model.

| Input | Output |
| --- | --- |
| Role Catalog (optional) | Categories |

See the [Create Roles in the Role Catalog](../index) topic for additional information.

## Create a Category

Categories are not mandatory to create roles, but they are highly recommended to organize single roles.

Create a category by proceeding as follows:

1. On the home page in the **Configuration** section, click on **Access Roles** to access the roles page.

   ![Home Page - Access Roles](../../../../../../../../static/images/Usercube_SaaS/Content/Resources/Images/Home_roles_V602.png)
2. All existing categories are shown in the menus on the left. To create a new category, click on **+**.

   ![Add a New Category](../../../../../../../../static/images/Usercube_SaaS/Content/Resources/Images/SingleRolesCatalog_newCategory_V602.png)
3. Fill in the fields.

   ![Create a Category](../../../../../../../../static/images/Usercube_SaaS/Content/Resources/Images/SingleRolesCatalog_createCategory_V602.png)

   * `Identifier`: must be unique among categories and without any whitespace.
   * `Name`: will be displayed in the UI to identify the created category.
   * `Collapsed in the role tree`: option that enables a collapsed view of the category in the role tree.
   * `Parent category`: optional link to an existing category that would contain the created category.
4. Click on **Create** and see the category added in the menus.

   :::warning
When creating a category, you must be cautious about the associated validators that are not yet defined.
   :::

## Verify Category Creation

In order to verify the process, check on the **Access Roles** screen that the category is created with the right parameters.

![Verify Category](../../../../../../../../static/images/Usercube_SaaS/Content/Resources/Images/CategoryCreation_test_V602.png)
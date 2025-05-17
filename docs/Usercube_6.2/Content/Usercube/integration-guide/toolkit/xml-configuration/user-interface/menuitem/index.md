---
sidebar_position: 819
title: Menu Item
---

# Menu Item

A menu item displays grouped navigation actions.

## Examples

```
            

```
## Properties

| Property | Details |
| --- | --- |
| DisplayName\_L1 optional | **Type**  String  **Description** Display name of the menu item in language 1 (up to 16). |
| EntityType optional | **Type**  Int64  **Description** Represents the linked entity type. |
| IconCode optional | **Type**  String  **Description** Code of one of [Microsoft's fabric icons](https://uifabricicons.azurewebsites.net/) to be displayed with the menu item.  **Note:** on Microsoft page, see the icons' codes by moving the mouse over the icons, or using the detailed view. |
| Identifier required | **Type**  String  **Description** Unique identifier of the item. |
| IsExpandedByDefault default value: true | **Type**  Boolean  **Description** Is an expanded by default menu item. |
| IsSelfForm default value: false | **Type**  Boolean  **Description** Is a self form menu item. |
| ParentMenuItem optional | **Type**  Int64  **Description** Defines the parent menu item. Five ParentMenuItem are hard coded: - Dashboard: Allow to display MenuItem in dashboard (Home page) - Nav: Allow to display MenuItem in navigation section (the left part in dashboard) - UserMenu: Allow to display MenuItem in links list on click on user account in the top right corner - Reports: Define all the reports downloadable in the application - Top: Allow to display MenuItem in top bar of the application, between "Home" and "My tasks" |
| ReportQuery optional | **Type**  Int64  **Description** Represents the linked report query. |
| URI optional | **Type**  String  **Description** Represents the menu URI. |
| Workflow optional | **Type**  Int64  **Description** Represents the linked workflow. |
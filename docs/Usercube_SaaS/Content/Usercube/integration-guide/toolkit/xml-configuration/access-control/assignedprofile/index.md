---
sidebar_position: 122
title: Assigned Profile
---

# Assigned Profile

An assigned profile allows or denies to a user a scope of responsibility in Identity Manager.

Each assigned profile gives one profile and one profile context to a user. A user can have up to 10 assigned profiles.

For a given user, all the assigned profiles are matched against all the configured access control rules to compute the user's permissions in Identity Manager.

An assigned profile can be assigned explicitly to someone, or generated automatically based on users' data via profile rules.

## Properties

| Property | Details |
| --- | --- |
| AccessState default value: 0 | **Type**  AccessState  **Description** Access state ("None"=0, "Requested"=4, "PendingApproval"=8, "PendingApproval1"=9, "PendingApproval2"=10, "Approved"=16, "Declined"=17 and "PolicyApproved"=18). |
| Context required | **Type**  Int64  **Description** Identifier of the context. |
| Email optional | **Type**  String  **Description** If specified, email address used for notification instead of the user's address. |
| EndDate default value: 20790606 | **Type**  DateTime  **Description** Assignment end date. |
| IsDenied default value: false | **Type**  Boolean  **Description** Profile denied to the user. |
| Profile required | **Type**  Int64  **Description** Identifier of the profile. |
| StartDate default value: 19000101 | **Type**  DateTime  **Description** Assignment start date. |
| User required | **Type**  Int64  **Description** Identifier of the user. |
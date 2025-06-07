# Assignment Dates

Entitlements can be assigned to users manually or automatically, but not on any time period. See the [Entitlement Assignment](/docs/product_docs/usercube/usercube/integration-guide/role-assignment/assignments-of-entitlements/index.md) topic for additional information.

## For Manual Assignments

During the manual assignment of an entitlement, i.e. role or resource type, to a user, the start and end dates of the entitlement must follow simple rules:

- the start date cannot be earlier than the earliest start date in all records of the user;
- the end date cannot be later than the latest end date in all records of the user.

This means that requesting an entitlement without any start/end dates will actually assign the entitlement from the records' earliest start date to the latest end date.

An entitlement cannot be requested with a start date earlier than today's date. But when requesting a role with an end date later than the records' latest end date, then the role will be assigned with its end date equal to the records' latest end date.

## For Automatic Assignments

The start and end dates of any automatic assignment are based on the dates from the [
Context Rule
](/docs/product_docs/usercube/usercube/integration-guide/toolkit/xml-configuration/provisioning/contextrule/index.md)defined for the identities.

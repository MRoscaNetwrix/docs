# Data Sources

You can create data sources in Directory Manager for the following providers, which include directories, databases, and files:

- MS Excel
- MS Access
- Oracle
- SQL Server
- Text/CSV (can only be used as a source in a Synchronize job)
- ODBC
- SCIM

## Where are Data Sources Used?

Data sources are used in the Directory Manager portal in the following ways:

As source and destination in Synchronize jobs

Synchronize jobs enable you to provision objects, deprovision objects, and sync data from one data source to another. See the [Synchronize](/docs/groupid/groupid/portal/synchronize/overview.md) topic for additional information.

As external data source for query-based searches

A Query Designer is used to perform targeted searches in the directory. While creating a search query, you can combine a data source with the directory to search for specific objects. See the [Query Based Advanced Search](/docs/groupid/groupid/portal/search/querysearch.md) topic for additional information.

As external data source for membership queries

A Query Designer enables you to specify membership queries for Smart Groups and Dynasties. When you specify a data source in the Query Designer, Directory Manager reads records from it and fetches similar objects from the directory to add to a group's membership. See the [Query Designer - Database tab](/docs/groupid/groupid/portal/group/querydesigner/database.md) topic for additional information.

As external data source for query-based searches

Another Query Designer is used to perform targeted searches in the directory. While creating a search query, you can combine a data source with the directory to search for specific objects. See the [Query Based Advanced Search](/docs/groupid/groupid/portal/search/querysearch.md) topic for additional information.

# Manage a Data Source

GroupID enables you to create data sources for various data providers. You can also update and delete these data sources.

What do you want to do?

- [Search a Data Source for a Specific Provider](#search-a-data-source-for-a-specific-provider)
- [Update a Data Source](#update-a-data-source)
- [Delete a Data Source](#delete-a-data-source)

## Search a Data Source for a Specific Provider

You can search for a data source built on a particular provider by its name.

__To search a data source:__

1. In Admin Center, click __Data Sources__ in the left pane.
2. On the __Data Sources__ page, click the tab for a provider to search for a data source built on it.
3. Enter a search string in the search box and press _Enter_. Data sources that contain the string in their names are displayed.

## Update a Data Source

You can update the details provided for a data source, such as its display name, the service account credentials to connect to it, and any other info you provided while creating it.

__To update the info:__

1. In Admin Center, click __Data Sources__ in the left pane.
2. On the __Data Sources__ page, click the tab for the provider the data source is built on.
3. Click __Edit__ for a data source. The __Update Data Source__ page is displayed, that differs by provider. Refer to the
   steps for creating the respective data source to modify the info. See the [Create a Data Source](/versioned_docs/groupid_11.0/groupid/admincenter/datasource/create.md) topic for additional information.
4. Click __Update Data Source__.

## Delete a Data Source

You can delete a data source to prevent users from using it as source and destination in Synchronize jobs.

NOTE: Deleting a data source corrupts all Synchronize jobs, membership queries, and search queries using that data source.

__To delete a data source:__

1. In Admin Center, click __Data Sources__ in the left pane.
2. On the __Data Sources__ page, click the tab for the provider for which you want to delete a data source.
3. Click __Delete__ for a data source to delete it.

# Manage Search Requests

The **Searches** interface may contain multiple requests. This section contains information on how
to work with searches to address specific tasks.

**NOTE:** To manage the search requests, users require sufficient access rights that are assigned by
the **Super User** (DSAR Administrator). See
[DSAR Roles](/versioned_docs/dataclassification_5.6.2/ndc/dsar/dsar_roles.md) for details on the
available roles, their rights and permissions.

## Customize View

You can filter your requests by status. Select one of the following under Display Status:

- Active – shows all requests with "_Processed_" status (default view).
- Completed – shows all completed requests. Review the
  [View Search Query Results](/versioned_docs/dataclassification_5.6.2/ndc/dsar/dsar_view_search_results.md)
  section for instructions on how to complete your request.
- Canceled – shows all canceled requests. [See Cancel Search for more information.](#cancel-search)
- All – shows all search requests.

In addition to status, a DSAR Manager can filter search requests by owner. Select one of the
following under Owner:

- All – shows search requests submitted by anyone.
- Me – shows all requests submitted by current user.

In addition to filtering capabilities, you can sort search request by any column, e.g., _Percentage
Complete_, _Updated Date_, etc.

## Cancel Search

If a search request is pending, you can cancel it — this will prevent the search terms from being
included in the search when it runs.

To cancel a search request, do the following:

1. In administrative web console, navigate to Data Analysis → DSAR.
2. Locate the Searches tab.
3. Select queued search and click Cancel on the right.

## Template Search

You can use previous searches as a template i.e., clone the parameters of a previous search in order
to minimize the time required to initiate a similar (or identical) search.

To template search request, do the following:

1. In administrative web console, navigate to Data Analysis→DSAR.
2. Locate the Searches tab.
3. Select search and click Template on the right.

A new search window will appear, pre-populated with exactly the same criteria as above.

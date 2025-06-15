# AD_TimeSync Job

The 0.__Collection > AD_TimeSync__ Job collects TimeSync information from the registry for each domain controller within the domain.

## Query for the AD_TimeSync Job

The AD_TimeSync Job uses the Registry Data Collector for the following query:

__CAUTION:__ Do not modify this query. The query is preconfigured for this job.

![Query Selection](/img/product_docs/accessanalyzer/enterpriseauditor/solutions/activedirectory/domains/collection/timesyncquery.webp)

The queries for this job are:

- Timesync Info – Targets one domain controller per domain known to Access Analyzer to determine TimeSync information from the registry
  - See the [Registry Data Collector](/docs/accessanalyzer/enterpriseauditor/admin/datacollector/registry.md) topic for additional information.

# Upgrade to the Latest Version

Netwrix recommends that you upgrade from the older versions of Netwrix Data Classification to the latest version available in order to take advantage of the new features.

## Upgrade Prerequisites

Before you start the upgrade, it is strongly recommended to take the following steps:

__Step 1 –__ Make sure you have .NET Framework 4.7.2 installed on the computer where Netwrix Data Classification resides. If not, download it from Microsoft website: [Download .NET Framework 4.7.2](https://dotnet.microsoft.com/download/dotnet-framework/net472).

__Step 2 –__ Back up NDC SQL database. It is recommended to do the following:

- Start Microsoft SQL Server Management Studio and connect to SQL Server instance hosting this database.
- In the Object Explorer, right-click the database and select __Tasks__ > __Back Up__.
- Wait for the process to complete.

__Step 3 –__ Back up the Index files. It is recommended to do the following:

- On the computer where Netwrix Data Classification is installed, start the Netwrix Data Classification Service Viewer tool. Select __Stop__ next to each service.
- Locate the folder containing index files (default location is _C:\Program Files\ConceptSearching\ConceptDB_) and back it up.

__Step 4 –__ Confirm that the NDC services and IIS Application pool are running as the same service account on all NDC servers. That account also needs to be a domain account.

## Upgrade Process

Seamless upgrade to Netwrix Data Classification 5.7 is supported for versions 5.5 and newer.

To upgrade your deployment, after taking the preparatory steps described above, run the product setup and follow the wizard steps. When finished, all solution components will be up and running.

If you need to upgrade from an earlier version, you should perform a staged upgrade, first upgrade to version 5.5, then perform a second upgrade to version 5.7.

## After the Upgrade

During the seamless upgrade from previous versions, Netwrix Data Classification preserves its configuration, so you will be able to classify your data right after finishing the upgrade. However, there are several steps you may need to take after upgrading.

Follow the steps to update taxonomies manually.

__Step 1 –__ In administrative web console, navigate to __Taxonomies__ > __Global Settings__.Settings.

__Step 2 –__ Click __Update__ in the right corner next to each taxonomy.

![update_taxonomy](/img/product_docs/dataclassification/ndc/requirements/update_taxonomy.webp)

The upgrade is now complete.

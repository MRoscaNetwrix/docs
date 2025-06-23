---
title: filesystem collection 2 fsac bulk import
sidebar_label: 2 fsac bulk import
description: Solution guide for filesystem collection 2 fsac bulk import including implementation steps, configuration, and best practices.
---

# 2-FSAC Bulk Import Job

The 2-FSAC Bulk Import job is designed to import collected access information from the targeted file
servers.

## Query for the 2-FSAC Bulk Import Job

The Bulk Import query uses the FSAA Data Collector and has been preconfigured to use the File system
activity Bulk import category.

![Query for the 2-FSAC Bulk Import Job](/img/product_docs/accessanalyzer/solutions/filesystem/collection/fsacbulkimportquery.webp)

- Bulk Import – Imports data into SQL Server

  - Typically this query is not modified. See the
    [FileSystemAccess Data Collector](/docs/accessanalyzer/12.0/data-collection/fsaa/overview.md) topic for
    information on when this query should be modified.

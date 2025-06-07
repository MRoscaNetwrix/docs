# SPAA: Additional Scoping

The Additional Scoping page is where the scan can be limited by depth of the scan. It is a wizard page for the categories of:

- Scan SharePoint Access
- Scan For Sensitive Content

__CAUTION:__ Users should not change scans in a way that would result in less data being returned on a subsequent scan (i.e. scanning fewer web applications, scanning fewer site collections, or a shallower depth scan). Those resources not included in a subsequent scan are marked as deleted in the Tier 2 database and subsequently removed from the Tier 1 database.

![Additional Scoping page](/static/img/product_docs/accessanalyzer/accessanalyzer/enterpriseauditor/admin/datacollector/box/additionalscoping.png)

If checked, set the __Limit scanned depth to: [number] level(s)__ option to the desired depth. If this option is not checked then the entire farm is scanned. If the scoping depth is set to __0__ then only root site collections are scanned. Each increment to the depth adds an additional level of depth from that point.

Check the __Perform differential scan__ box to enable the job to run a differential scan. Differential scanning is enabled by default. When this option is enabled, SPAA scan will only parse files for content/SDD if it has been modified since the last scan.

__NOTE:__ This option only applies to Tag collection and Sensitive data collection. Files will be still be scanned for permissions regardless of whether this option is checked or not.

# Sensitive Content Summary Report

The Sensitive Content Summary report at the instance level provides a count of collections where criteria matches were found on the selected instance. This report includes a Details table.

![Sensitive Content Summary report at the instance level](/static/img/product_docs/accessinformationcenter/access/informationcenter/resourceaudit/postgresql/instance/instancesensitivecontentsummary.png)

This report is comprised of the following columns:

- Server Name – MongoDB host name or cluster name
- Criteria Name – Type of potentially sensitive criteria matches found
- Criteria Type – Pattern for pattern based matches (System Criteria), and subject type based on Subject Profile matches (for example, Customer, Employee, and so on)
- Count – Number of collections with criteria matches

There is one table at the bottom displaying Details on the collections where the selected criterion matches were found:

- Source — For System Criteria this shows the criteria name (for example, Credit Cards). For Subject Profiles criteria it shows the individual identities (for example, Jon Doe).
- Path – Location of the collection where the criteria matches were found
- Sub File – Column name of where the sensitive data resides
- Count – Number of criteria matches found within each collection
- Attributes – Comma separated list of Attributes found for the identity

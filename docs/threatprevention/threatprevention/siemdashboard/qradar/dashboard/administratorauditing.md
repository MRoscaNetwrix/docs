# Administrator Auditing Dashboard

The Administrator Auditing dashboard is specifically fed by a Threat Prevention policy named Domain Admin Activity. See the [SIEM Folder Templates](/docs/threatprevention/threatprevention/admin/templates/folder/siem.md) topic for information on this policy template. If this policy template is not enabled and actively monitoring, then this dashboard will be blank.

The Administrator Auditing dashboard contains the following cards:

![Administrator Auditing Dashboard](/img/product_docs/threatprevention/threatprevention/siemdashboard/qradar/dashboard/administratorauditing.png)

- Top Clint IPs – Displays up to the top five (5) client IP addresses related to events that have been recorded in the specified timeframe
- Events – Breakdown of changes that have been recorded in the specified timeframe by successful/failed/blocked status. See the [Graph Card Features](/docs/threatprevention/threatprevention/siemdashboard/qradar/navigate.md#graph-card-features) topic for additional information.
- Most Active Administrators – Displays up to the top five (5) usernames related to change events that have been recorded in the specified timeframe
- All Administrator Activity – Tabular format of all events that have been recorded in the specified timeframe. See the [Table Card Features](/docs/threatprevention/threatprevention/siemdashboard/qradar/navigate.md#table-card-features) topic for additional information.
- Administrator Offenses – Tabular format of all offenses related to Administrators. See the [Table Card Features](/docs/threatprevention/threatprevention/siemdashboard/qradar/navigate.md#table-card-features) topic for additional information.
- Administrator Group Changes – Tabular format of all group changes to the Domain, Schema, and Enterprise Admin groups that have been recorded in the specified timeframe. See the [Table Card Features](/docs/threatprevention/threatprevention/siemdashboard/qradar/navigate.md#table-card-features) topic for additional information.

The time interval is identified in the upper-right corner with the _Start_ and _End_ boxes. This is set by default to the past three (3) hours. To search within a different interval, either manually type the desired date and time or use the calendar buttons to set the desired date and time interval. Then click __Search__ to refresh the card data.

When a search using a time interval longer than twelve (12) hours is instigated, the database query is broken into multiple mini-queries. This will result in a visible reset of the dashboard display at the end of each mini-query until all data for the selected time interval has been retrieved.

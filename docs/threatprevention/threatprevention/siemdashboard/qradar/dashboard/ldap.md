# LDAP Dashboard

The Lightweight Directory Access Protocol (LDAP) dashboard contains the following cards:

![LDAP Dashboard](/img/product_docs/activitymonitor/activitymonitor/admin/monitoreddomains/admonitoringconfiguration/ldap.png)

- Top Users – Displays up to the top five (5) users related to LDAP events that have been recorded in the specified timeframe. See the [Graph Card Features](/docs/threatprevention/threatprevention/siemdashboard/qradar/navigate.md#Graph-Card-Features) topic for additional information.
- Top Source Hosts – Displays up to the top five (5) client IP addresses related to LDAP events that have been recorded in the specified timeframe. See the [Graph Card Features](/docs/threatprevention/threatprevention/siemdashboard/qradar/navigate.md#Graph-Card-Features) topic for additional information.
- LDAP Query Details – Tabular format of all non-trivial LDAP events that have been recorded in the specified timeframe. See the [Table Card Features](/docs/threatprevention/threatprevention/siemdashboard/qradar/navigate.md#Table-Card-Features) topic for additional information.

The time interval is identified in the upper-right corner with the _Start_ and _End_ boxes. This is set by default to the past three (3) hours. To search within a different interval, either manually type the desired date and time or use the calendar buttons to set the desired date and time interval. Then click __Search__ to refresh the card data.

When a search using a time interval longer than twelve (12) hours is instigated, the database query is broken into multiple mini-queries. This will result in a visible reset of the dashboard display at the end of each mini-query until all data for the selected time interval has been retrieved.

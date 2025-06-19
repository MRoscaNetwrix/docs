# User Behavior and Blind Spot Analysis Reports

The User Behavior and Blind Spot Analysis report pack contains a set of smart reports that help you
identify vulnerabilities and easily answer questions such as:

- Has there been any abnormal access to sensitive data?
- Is anyone accessing stale data?
- Have there been any unusual spikes in failed activity?
- Who is active outside of business hours and what are they doing?
- Has anyone put harmful files on corporate data storage?
- Are there any files likely to contain credentials, Social Security numbers, PHI or other sensitive
  data?

Analytics reports can be found in the User Behavior and Blind Spot Analysis folder under the
Predefined node.

![userbehaviorblindspotanalysis](/img/versioned_docs/auditor_10.6/auditor/admin/reports/types/userbehaviorblindspotanalysis.webp)

If you are sure that some audit data is missing (e.g., you do not see information on your file
servers in reports and search results), verify that the Audit Database settings are configured and
that data is written to databases that reside on the default SQL Server instance.

By default, Auditor allows generating reports and running interactive searches on data collected in
the last 180 days. If you want to investigate incidents that occurred more than 180 days ago, ask
your Auditor Global administrator to import that data from the Long-Term Archive.

![failedactivitytrend](/img/versioned_docs/auditor_10.6/auditor/admin/reports/types/failedactivitytrend.webp)

Each report has a set of filters which help organize audit data in the most convenient way. See the
[View Reports](/docs/auditor/10.6/auditor/admin/reports/view.md) topic for additional
information. You can also create a subscription to any report you want to receive on a regular
basis. See the [Subscriptions](/docs/auditor/10.6/auditor/admin/subscriptions/overview.md)
topic for additional information.

# Configuration and Stats

The Configuration and Stats report is a live update on the status and results of the Automated
Documentation system.

From the Netwrix Dashboard:

Click **Configuration and Stats** in the **Resources** section, or open **Settings** >
**Configuration and Stats**.

The **License Type** displays your current license.

![Configuration and Stats report](../../../static/img/product_docs/strongpointforsalesforce/installing_strongpoint/config_stats_overview.webp)

The report is divided into multiple tabs:

> Scanner Status
>
> > Documentation Stats
> >
> > Scanner Logs
> >
> > Scanner Additional Information
> >
> > Change Log Creation (sandbox option)
>
> Jira Configuration
>
> Orgs Credentials

## Scanner Status

Accesses the documentation stats, scanner logs, scanner additional configuration and change log
creation (sandbox).

### Documentation Stats

This section displays the current status of the documentation Platform Governance for Salesforce has
created for your account. The statistics included the total number of customization, and the various
**junctions** created to track the relationships between customizations. **junctions** represent
critical relationship information to help you determine if it is safe to delete or change something,
and how it affects other items. Click **Download PDF** to export a copy of the report.

![Configuration and Stats - Documentation Stats](../../../static/img/product_docs/strongpointforsalesforce/installing_strongpoint/config_doc_stats.webp)

### Scanner Logs

The section displays details for each of the scanner logs:

- Scanner Log Name
- Salesforce Type:
- Retrieved Stage: this column displays the current status when a scanner is running. For example,
  **DeDuplicate** is displayed if the scanner is running the **DeDuplicate** process during the
  scan.
- Total Customization: this column shows the number of customizations processed while a scanner is
  running. When the scan is complete, the column matches the total **Scanner Count**.
- Scanner Count

![Configuration and Stats - Scanner Logs](../../../static/img/product_docs/strongpointforsalesforce/installing_strongpoint/config_scanner_logs.webp)

### Scanner Additional Information

This section only applies to sandbox orgs. It displays each scanner function and the status:

- Last Scanner Run Date
- Last Automated Scanner Run Date
- Last Scanner Run Status

![Configuration and Stas - Scanner Additional Information](../../../static/img/product_docs/strongpointforsalesforce/installing_strongpoint/config_scan_add_info.webp)

### Change Log Creation

If you are in a sandbox, you can control whether change logs are created. Due to Salesforce space
limits on different
[sandbox accounts](https://help.salesforce.com/articleView?id=data_sandbox_environments.htmandtype=5),
you may want to disable change logs to save space.

![Control Change Log Creation in Sandbox](../../../static/img/product_docs/strongpointforsalesforce/installing_strongpoint/config_stats_enable_change_log.webp)

## Jira Configuration

Use these features to enter your Jira credentials and map the statuses between Jira and Platform
Governance for Salesforce.

- Credentials
- Status Mapping
- [Jira Field Mapping](../integrations/jira_field_map.md) (separate topic)

### Credentials

Your credentials are generated in Jira. Enter them here for the Platform Governance for Salesforce
Jira integration.

1. Open **Netwrix Dashboard** > **Settings** > **Configuration and Stats**.
2. Open the **Jira Configuration** tab. It opens on the **Credentials** tab.

    ![Open the credentials](../../../static/img/product_docs/strongpointforsalesforce/integrations/jira_sp_credentials.webp)

3. Enter your credentials:

    - **Jira Username** is your Jira login email associated with your Jira API token.
    - **Jira Token** is your Jira API token. If you do not have your token, follow the steps in the
      [Atlassian](https://confluence.atlassian.com/cloud/api-tokens-938839638.html) documentation.
    - **Jira Account Name** is the _company specific part_ of the Jira site URL
      (**https://\_**JiraAccountName**\_.atlassian.net**). Only enter the _JiraAccountName_, not the
      entire URL.
    - **Site URL** is **https://site.force.secure.com**

4. Click **Save**.

### Status Mapping

1. Open **Netwrix Dashboard** > **Settings** > **Configuration and Stats**.
2. Open the **Jira Configuration** tab.
3. Open the **Status Mapping** tab.

    ![Set up the Jira status mappings for Change Request status](../../../static/img/product_docs/strongpointforsalesforce/integrations/jira_status_settings.webp)

4. Enter the mappings between your Jira statuses and the Change Request statuses. You must define
   your Jira statuses prior to this step. You can enter multiple Jira statuses for each Change
   Request status, separated by commas. For example, **In Progress, Backlog**. Assign your mapping
   for each of the Change Request statuses:

    - **Approved Values**
    - **Complete Values**
    - **In Progress Values**
    - **Pending Approval Values**
    - **Rejected Values**

5. Check **Is Automatic Sync** to enable Platform Governance for Salesforce to handle the
   synchronization between Jira and Salesforce when a Ticket status is updated to a mapped status.
   without having to click **Push**. If you are using an org where you do not want to create a
   Change Request, leave this unchecked so you can do your research or testing without generating
   Change Requests.
6. Change Requests are not automatically created, as not all tickets result in a Change Request.
   Tickets must be pushed to Platform Governance for Salesforce to begin the process. If Automatic
   Synchronization is turned on, then changes to the Status and Customizations are synchronized
   between Jira and Platform Governance for Salesforce without the need to keep manually pushing the
   changes.
7. Click **Save**.

## Orgs Credentials

Create credentials for your Salesforce orgs and link the a Named Credential Change Request
deployments.

1. Open **Netwrix Dashboard** > **Settings** > **Configuration and Stats**.
2. Open the **Orgs** Credentials tab.

    ![Orgs Credentials](../../../static/img/product_docs/strongpointforsalesforce/installing_strongpoint/orgs_credentials.webp)

3. Click **New** to enter new credentials. For existing credentials, you can click **Edit** to
   modify the credential, **Delete** to remove it, or the **credential name** to sync your
   credentials.

    ![New org credentials](../../../static/img/product_docs/strongpointforsalesforce/installing_strongpoint/orgs_credentials_new.webp)

4. Click **Save**.

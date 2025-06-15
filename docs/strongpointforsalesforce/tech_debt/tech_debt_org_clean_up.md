# Org Clean Up

Cleaning up your orgs is a process. The key to clean up success is to move forward through sets of closely-related customizations using clear and repeatable steps. Platform Governance for Salesforce helps you through each step in the process.

Every clean up project has these key steps:

1. Identify and prioritize what needs to be cleaned up.
2. Assess the risk of downstream problems and add related Customizations to be cleaned up.
3. Track the progress of your clean up process.
4. Group Customizations for approval and clean up.
5. Archive the Customization definitions and data.
6. Clean up the approved Customizations.
7. Validate you followed your change approval process.

Stepping through this process helps organize the work and manage the risk. Small orgs can do the whole process with an Automated Documentation license. Large orgs likely require the tighter approval processes and environment comparison capabilities of the Intelligent Change Enablement license.

These items can help you identify Customizations for Clean Up:

> Date Last Used
>
> Automated Report Clean Up
>
> Employees Related to a Customization

## Date Last Used

Date Last Used (DLU) is a key criterion for clean up, as you generally are not cleaning up active Customizations. DLU means different things to different people in the Salesforce community. The generic definition is:

> _The last date the Customization, or the data it contains, was created, changed, accessed, processed or used._

[DLU](../clean_up/date_last_used.md) is calculated differently for each Customization type.

For all clean up activities, consider the following items:

- Blank DLU means there is no verified date. A blank date does not mean it is safe to remove.
- DLU is not the only criterion. You must look at the dependencies. An unused field with related code is not safe to remove. It is, however, a sign you may have unnecessary code.
- An unused field may have important data from the history of your company. A good question to investigate is why isn’t it being used? It might be a good idea that never got off the ground.
- Cleaned up Customizations are archived if you need to restore.

Like all Salesforce Date fields, DLU can be filtered using relative date formats (typically what you will want). You can also filter on specific dates.

![DLU Filter](../../../static/img/product_docs/strongpointforsalesforce/tech_debt/tech_debt_2.webp)

## Automated Report Clean Up

The most common unused Customizations are Reports. In most orgs, new Reports are created every day. Some are critical to ongoing business processes, others are quick solutions to day-to-day problems. These one-time quick reports accumulate in your orgs, causing confusion and inefficiency. Refer to [Automated Report Clean Up](../tools/automated_report_clean_up.md) for more details.

Automated Report Clean Up safely archives Reports following the rules and criteria you set up. The process is simple:

1. Set up default rules. For example,

   - Reports not used within the past year
   - Reports owned by people who no longer have access to Salesforce and have not used in 6 months
2. Run the analysis on an ad hoc basis and review your results.
3. Exclude any Reports to be retained, either manually by changing the rule settings to exclude Reports based on:

   - Report Owners
   - Related Roles
   - Scheduled
   - Private Reports
   - Date Last Used
4. - Excludes Reports covered by a special policy or with any downstream dependencies to ensure you do not delete something important.
   - Emails Report owners (if desired) that the Report is being archived. The owner can retain the Report with a simple mouse click. The Date Last Used is updated to the current date.
   - Deletes the Reports that were not retained, but keeps the Report definition.

   When you run the Clean Up, Archived Reports can be easily be restored if needed.
5. Schedule your rules to run on a regular basis to keep your orgs cleaned up and efficient.

## Employees Related to a Customization

Knowing who is using a customization is useful. This is tackled in steps, by Users and Owners.

### Users

__Field and Object Users__: Track employees editing a Field (using a custom or standard Object). It is not turned on for all Customizations which would be inefficient. If you use _Salesforce Shield Event Monitoring_, Platform Governance for Salesforce captures this data automatically.

To capture the data without Salesforce Shield Event Monitoring:

1. Enable __Field Audit Trail__ for the field.
2. Permit Salesforce to populate the audit log for the last 18 months.
3. Rescan the tracked fields.
4. Names of the employees changing the data in each field are gathered automatically. This process can take multiple days for a large dataset.
5. Turn off audit history if desired.

__Code, App, and Component Users__: With _Salesforce Shield Event Monitoring_, capture users from the execution history of APEX-related objects.

__Other objects__: There are two strategies for other objects:

- __Sharing Rules__: Often, you can determine who is using a List View or Dashboard by understanding the shared Users, Roles, and Groups.
- __Salesforce Shield Event Monitoring__: Employee usage data for Reports, Dashboards, and many other objects, is only available with Salesforce Shield Event Monitoring. It enhances usage metadata to show users who are viewing non-scripted objects and executing or triggering code and workflows. Once you activate _Salesforce Shield Event Monitoring_, data is collected from that point on. It is not retroactive.

__Users referred to in objects__: Fields are not created for everything, but all the metadata is available. You can identify users (and other things) referred to in dashboard filters, formula fields, SOQL, or even code, by searching the raw XML, JSON or code. The [Specific Clean Up Approaches](tech_debt_org_specific_clean_up_approaches.md) section contains examples.

### Owners

The current owner of each Customization is tracked. By default, it is the person who created it. In cases such as Reports, this is useful to understand who needs to approve a change to a report.

> __TIP__
>
> You can use the __Change Owner__ button on any Customization List View. For an individual Customization, edit the Owner field on the Customization Record. Best practice if you have a staff change, is to update the Process record, which then updates the owner for all the affected Customizations.

__Next Technical Debt Topic:__[ Org Clean Up Example](tech_debt_org_clean_up_example.md)

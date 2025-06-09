# AD\_ResetPasswordPermissions Job

The AD\_ResetPasswordPermissions Job highlights all Active Directory users that are capable of resetting another user's password within the targeted domains. It uses the data collected by the 0.Collection Job Group to provide information on permissions applied to user objects in Active Directory.

## Analysis Tasks for the AD\_ResetPasswordPermissions Job

Navigate to the __Active Directory Permissions Analyzer__ > __1.Users__ > __AD\_ResetPasswordPermissions__ > __Configure__ node and select __Analysis__ to view the analysis tasks.

__CAUTION:__ Do not modify or deselect the selected analysis tasks. The analysis tasks are preconfigured for this job.

![Analysis Tasks for the AD_ResetPasswordPermissions Job](/img/product_docs/accessanalyzer/enterpriseauditor/solutions/activedirectorypermissionsanalyzer/users/resetpasswordpermissionsanalysis.png)

The default analysis tasks are:

- List user password reset permissions – Creates the SA\_AD\_ResetPasswordPermissions\_Details table accessible under the job’s Results node
- Summarize password reset permissions – Creates an interim processing table in the database for use by downstream analysis and report generation

In addition to the tables and views created by the analysis tasks, the AD\_ResetPasswordPermissions Job produces the following pre-configured report.

| Report | Description | Default Tags | Report Elements |
| --- | --- | --- | --- |
| Reset Password | This report highlights instances where "Reset Password" permissions are applied to Active Directory user objects. This information is summarized at the domain and enterprise levels. By default, this report excludes members of administrator groups such as Domain Admins, Schema Admins, and Enterprise Admins. | None | This report is comprised of three elements:   - Bar Chart – Displays affected accounts by domain - Table – Provides details on reset password permissions - Table – Provides details on top users with reset password permissions |

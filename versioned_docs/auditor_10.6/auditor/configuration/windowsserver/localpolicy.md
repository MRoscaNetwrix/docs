# Configure Local Audit Policies

Local audit policies must be configured on the target servers to get the "Who" and "When" values for the changes to the following monitored system components:

- Audit policies
- File shares
- Hardware and system drivers
- General computer settings
- Local users and groups
- Services
- Scheduled tasks
- Windows registry
- Removable media

You can also configure advanced audit policies for same purpose. See the [Configure Advanced Audit Policies](/versioned_docs/auditor_10.6/auditor/configuration/windowsserver/advancedpolicy.md) topic for more information.

## Manual Configuration

While there are several methods to configure local audit policies, this topic covers just one of them: how to configure policies locally with the Local Security Policy snap-in. To apply settings to the whole domain, use the Group Policy but consider the possible impact on your environment.

Follow the steps to configure local audit policies.

__Step 1 –__ On the audited server, open the __Local Security Policy__ snap-in: navigate to Start > Windows Administrative Tools__>__Local Security Policy.

__Step 2 –__ Navigate to __Security Settings > Local Policies > Audit Policy__.

| Policy Name | Audit Events |
| --- | --- |
| Audit account management | _"Success"_ |
| Audit object access | _"Success"_ |
| Audit policy change | _"Success"_ |

Local audit policy is configured and can be changed in the same location:

![manualconfig_ws_local_audit_policies2016](/img/versioned_docs/auditor_10.6/auditor/configuration/fileservers/windows/manualconfig_ws_local_audit_policies2016.png)

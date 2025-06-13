# Box

Use the __Box__ source configuration window to set up the crawling and classification operations for content stored in a Box Enterprise account.

By default, configuration window displays basic configuration settings only. It is recommended that you click the "wrench" icon in the bottom left corner to configure advanced settings.

__NOTE:__ To configure advanced settings, your user account may need advanced privileges. [See Users and Security Settings for more information.](/versioned_docs/dataclassification_5.6.2/ndc/security/users.md)

[![addbox_thumb_0_0](/img/versioned_docs/dataclassification_5.6.2/ndc/sources/box/addbox_thumb_0_0.png)](/versioned_docs/dataclassification_5.6.2/images/addbox.png)

Configure the following:

| Setting | Description |
| --- | --- |
| __Basic settings__ |  |
| JSON Import | Drag and drop the JSON file with Box app configuration settings that you downloaded at [Step 1. Create the App](/versioned_docs/dataclassification_5.6.2/ndc/config_infrastructure/configure_box.md#Step-1-Create-the-App) (see #12). The program then parses this file so that many settings are filled in automatically. |
| Enterprise ID | Specifies the internal unique identifier for your Box account (filled in automatically). |
| API Key | _Client ID_ of the Box app created at [Step 1. Create the App](/versioned_docs/dataclassification_5.6.2/ndc/config_infrastructure/configure_box.md#Step-1-Create-the-App)(Filled in automatically.) |
| Client Secret | Will be generated when allowing access to the Netwrix Data Classification app. Is also known as the “App Key”. |
| Public Key ID  Private Key  Private Key Password | Created when generating the trust between your Box account, and the Netwrix Data Classification app – these should be kept secret and secure. |
| Write Classifications | Identifies whether classifications should be written back to the Box source documents. Classification results can either be written to classification templates or to the generic ‘tags’ property. This is specified using the __Write Configuration__ setting of the source. For more information, see [Use Tagging](/versioned_docs/dataclassification_5.6.2/ndc/sources/tagging.md) |
| Source Group | Select the source group (if any). |
| Pause source on creation | Select if you want to make other configuration changes before collection of the source occurs. |
| __Advanced settings__ |  |
| Email Address | Specify one or more users (email addresses) for impersonated crawling.   - If specified explicitly, the crawling engine will impersonate these users when crawling their content as well as shared content where they are the owners. Enter one or several accounts from those listed in the _Managed Users_ on the '_Users and Groups_' tab of the Box console. - If not specified explicitly, the program will automatically create and use an admin user account (_NDC Crawling Account_) for crawling.   Remember to provide this app user account with sufficient permissions for the content you want to index (i.e. share access). To share content for crawling with this account, use group membership. |
| Re-Index Period | Specifies how often the source should be checked for changes (period in days). Default is __7__ days. |
| Priority | Set priority for this data source to be crawled. |
| Document Type | Specify a value which can be used to restrict queries when utilizing the Netwrix Data Classification search index. |

See also:

- [Configure Box for Crawling](/versioned_docs/dataclassification_5.6.2/ndc/config_infrastructure/configure_box.md)
- [Manage Sources and Control Data Processing](/versioned_docs/dataclassification_5.6.2/ndc/sources/sources_manage.md)

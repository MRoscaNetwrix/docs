# Export Profiles and Permission Sets

Administrators can use this tool to export all user permissions into a single view for easy review
and management. The export is done in the background to avoid timing out or exceeding the Salesforce
Governor Limits. You will receive an email with a link to the
[Export Object Attachment](export_object_attachment_records.md) record, where you can download your
file.

1. Open **Netwrix Dashboard** > **Tools** > **Export Objects**.
2. Open the **Profiles & Permission Sets** tab.

    ![export_profile_ui](../../../static/img/product_docs/strongpointforsalesforce/tools/export_profile_ui.webp)

3. Scroll through the **Select Profile to be Exported**.
4. Select one or more objects in the scroll box. Use **Shift** or **Ctrl** to select multiple
   objects.
5. Click the right arrow to move the items to the **Selected Profiles** list. To remove an item from
   the **Selected Profiles** list, select it and click the left arrow.
6. Select the **Settings to be exported**.

    ![export_profile_ui_settings](../../../static/img/product_docs/strongpointforsalesforce/tools/export_profile_ui_settings.webp)

7. Click **Download XLS**. The file _ProfileExport.xls_ is created.

### ProfilesExport.xls File

When you open an exported file, this message may be displayed, as the exported _ProfilesExport.xls_
file is in XML instead of the Excel format. Click **Yes** to load the file.

![Excel error message - Click Yes to continue.](../../../static/img/product_docs/strongpointforsalesforce/tools/export_excel_error_msg.webp)

The _ProfilesExport.xls_ file contains a **Summary** tab and a separate tab for each selected
profile.

The **Summary** tab shows who created the export, the creation date and time, and the list of
selected profiles.

![export_profile_summary](../../../static/img/product_docs/strongpointforsalesforce/tools/export_profile_summary.webp)

The **Profile** tabs contain all of the requested information for each profile.

![export_profile_profile](../../../static/img/product_docs/strongpointforsalesforce/tools/export_profile_profile.webp)

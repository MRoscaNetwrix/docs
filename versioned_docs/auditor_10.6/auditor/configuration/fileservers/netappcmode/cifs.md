# Configure Audit Settings for CIFS File Shares

Netwrix Auditor can be configured to audit all access types, review the table below and select options that you want to track:

| Option |  | Description |
| --- | --- | --- |
| Changes | Successful | Use this option to track changes to your data. Helps find out who made changes to your files, including their creation and deletion. |
| Failed | Use this option to detect suspicious activity on your file server. Helps identify potential intruders who tried to modify or delete files, etc., but failed to do it. |  |
| Read access | Successful | Use this option to supervise access to files containing confidential data intended for privileged users. Helps identify who accessed important files besides your trusted users.  Enabling this option on public shares will result in high number of events generated on your file server and the amount of data written to the AuditArchive. |
| Failed | Use this option to track suspicious activity. Helps find out who was trying to access your private data without proper justification.  Enabling this option on public shares will result in high number of events generated on your file server and the amount of data written to the AuditArchive. |  |

Actions reported by Netwrix Auditor vary depending on the file server type and the audited object (file, folder, or share). The changes include creation, modification, deletion, moving, renaming, and copying. To track the copy action, enable successful read access and change auditing. See the [File Servers](/versioned_docs/auditor_10.6/auditor/configuration/fileservers/overview.md) topic for additional information.

Do one of the following depending on the OS:

- [To configure audit settings for the CIFS file shares from computers running pre-Windows Server 2012 versions](#to-configure-audit-settings-for-the-cifs-file-shares-from-computers-running-pre-windows-server-2012-versions)
- [To configure audit settings for the CIFS file shares from computers running Windows Server 2012 and above](#to-configure-audit-settings-for-the-cifs-file-shares-from-computers-running-windows-server-2012-and-above)

## To configure audit settings for the CIFS file shares from computers running pre-Windows Server 2012 versions

1. Navigate to the root share folder, right-click it and select __Properties__.
2. In the __`<Share_Name>` Properties__ dialog, select the __Security__ tab and click __Advanced__.

   If there is no such tab, it means a wrong security style has been specified for the volume holding this file share.
3. In the __Advanced Security Settings for `<Share_Name>`__ dialog, navigate to the __Auditing__ tab, click Edit.

   ![auditing_entries_netapp](/img/versioned_docs/auditor_10.6/auditor/configuration/fileservers/netappcmode/auditing_entries_netapp.png)
4. In a separate __Advanced Security Settings for `<Share_Name>`__ dialog, click Add to add a principal. You can also select __Everyone__ (or another user-defined group containing users that are granted special permissions) and click __Edit__.

   You can specify any other user group, but in this case Netwrix Auditor will send emails with warnings on incorrect audit configuration. This will not affect the Reports functionality and the product will only audit user accounts that belong to the selected group.
5. Apply settings to your Auditing Entries depending on actions that you want to audit. If you want to audit all actions (successful reads and changes as well as failed read and change attempts), you need to add three separate Auditing Entries for each file share. Otherwise, reports will contain limited data and warning messages.

   | Auditing Entry |
   | --- |
   | Successful reads |
   | The Auditing Entry below shows Advanced Permissions for auditing successful reads only:  - Apply onto—Select _"Files only"_. - Check _"Successful"_ and _"Failed"_ next to List folder / read data. - Make sure that the __Apply these auditing entries to objects and/or containers within this container only__ checkbox is cleared. |
   | Successful changes |
   | The Auditing Entry below shows Advanced Permissions for auditing successful changes only:  - Apply onto—Select _"This folder, subfolders and files"_. - Check _"Successful"_ next to the following permissions:    - Create files / write data   - Create folders / append data   - Write extended attributes   - Delete subfolders and files   - Delete   - Change permissions   - Take ownership - Make sure that the __Apply these auditing entries to objects and/or containers within this container only__ checkbox is cleared. |
   | Failed read attempts |
   | The Auditing Entry below shows Advanced Permissions for auditing failed read attempts only:  - Apply onto—Select _"This folder, subfolders and files"_. - Check _"Failed"_ next to List folder / read data. - Make sure that the __Apply these auditing entries to objects and/or containers within this container only__ checkbox is cleared. |
   | Failed change attempts |
   | The Auditing Entry below shows Advanced Permissions for auditing failed change attempts only:  - Apply onto—Select _"This folder, subfolders and files"_. - Check _"Failed"_ next to the following permissions:    - Create files / write data   - Create folders / append data   - Write extended attributes   - Delete subfolders and files   - Delete   - Change permissions   - Take ownership - Make sure that the __Apply these auditing entries to objects and/or containers within this container only__ checkbox is cleared. |

## To configure audit settings for the CIFS file shares from computers running Windows Server 2012 and above

1. Navigate to the root shared folder, right-click it and select Properties.
2. In the __`<Share_Name>` Properties__ dialog, select the __Security__ tab and click __Advanced__.

   If there is no such tab, it means a wrong security style has been specified for the volume holding this file share.
3. In the __Advanced Security Settings for `<Share_Name>`__ dialog, navigate to the __Auditing__ tab, click Edit.

   ![auditing_entries_netapp_2016](/img/versioned_docs/auditor_10.6/auditor/configuration/fileservers/netappcmode/auditing_entries_netapp_2016.png)
4. Click Add to add a new principal. You can also select Everyone (or another user-defined group containing users that are granted special permissions) and click Edit.
5. In the Auditing Entry for `<Folder_Name>` dialog, click the Select a principal link and specify Everyone.

   You can specify any other user group, but in this case Netwrix Auditor will send emails with warnings on incorrect audit configuration. In this case, the product will only monitor user accounts that belong to the selected group.
6. Apply settings to your Auditing Entries depending on actions that you want to audit. If you want to audit all actions (successful reads and changes as well as failed read and change attempts), you need to add three separate Auditing Entries for each file share. Otherwise, reports will contain limited data and warning messages. Review the following for additional information:

   - Successful reads
   - Successful changes
   - Failed read attempts
   - Failed change attempts
   | Auditing Entry |  |
   | --- | --- |
   | Successful reads |  |
   | The Auditing Entry below shows Advanced Permissions for auditing successful reads only:  ![manualconfig_fileserver_auditingentry_1_2016](/img/versioned_docs/auditor_10.6/auditor/configuration/fileservers/netappcmode/manualconfig_fileserver_auditingentry_1_2016.png)  - Type—Set to_"Success"_. - Applies to—Set to_"Files only"_. - Advanced permissions—SelectList folder / read data. - Make sure that theOnly apply these auditing settings to objects and/or containers within this containercheckbox is cleared. |  |
   | Successful changes |  |
   | The Auditing Entry below shows Advanced Permissions for auditing successful changes only:  ![manualconfig_fileserver_auditingentry_2_2016](/img/versioned_docs/auditor_10.6/auditor/configuration/fileservers/netappcmode/manualconfig_fileserver_auditingentry_2_2016.png)  - Type—Set to_"Success"_. - Applies to—Set to_"This folder, subfolders and files"_. - Advanced permissions:   - Create files / write data   - Create folders / append data   - Write extended attributes   - Delete subfolders and files   - Delete   - Change permissions   - Take ownership - Make sure that theOnly apply these auditing settings to objects and/or containers within this containercheckbox is cleared. |  |
   | Failed read attempts |  |
   | The Auditing Entry below shows Advanced Permissions for auditing failed read attempts:  ![manualconfig_fileserver_auditingentry_3_2016](/img/versioned_docs/auditor_10.6/auditor/configuration/fileservers/netappcmode/manualconfig_fileserver_auditingentry_3_2016.png)  - Type—Set to_"Fail"_. - Applies to—Set to_"This folder, subfolders and files"_. - Advanced permissions—SelectList folder / read data. - Make sure that theOnly apply these auditing settings to objects and/or containers within this containercheckbox is cleared. |  |
   | Failed change attempts |  |
   | The Auditing Entry below shows Advanced Permissions for auditing failed change attempts:  ![manualconfig_fileserver_auditingentry_4_2016](/img/versioned_docs/auditor_10.6/auditor/configuration/fileservers/netappcmode/manualconfig_fileserver_auditingentry_4_2016.png)  - Type—Set to_"Fail"_. - Applies to—Set to_"This folder, subfolders and files"_. - Advanced permissions:   - Create files / write data   - Create folders / append data   - Write extended attributes   - Delete subfolders and files   - Delete   - Change permissions   - Take ownership - Make sure that theOnly apply these auditing settings to objects and/or containers within this containercheckbox is cleared. To audit successful changes on NetApp 8.x or earlier, also selectWrite Attributesin the__Advanced permissions__list in the auditing entry settings. |  |

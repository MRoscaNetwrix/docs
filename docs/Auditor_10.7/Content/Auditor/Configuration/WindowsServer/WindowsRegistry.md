---
sidebar_position: 1851
title: Configure Windows Registry Audit Settings
---

Filter: 

* All Files

Submit Search

# Configure Windows Registry Audit Settings

Windows Registry audit permissions must be configured on each Windows server you want to audit so that the “Who” and “When” values are reported correctly for each change. For test environment, PoC or evaluation you can use automatic audit configuration. If you want to configure Windows Registry manually, follow the instructions below.

The following audit permissions must be set to *"Successful"* for the `HKEY_LOCAL_MACHINE\SOFTWARE and HKEY_LOCAL_MACHINE\SYSTEM` keys:

* Set Value
* Create Subkey
* Delete
* Write DAC
* Write Owner

Perform one of the following procedures depending on the OS version:

* [Configuring Windows registry audit settings on pre-Windows Server 2012 versions](#pre2012 "Configuring Windows registry audit settings on pre-Windows Server 2012 versions")
* [Configuring Windows registry audit settings on Windows Server 2012 and above](#2012 "Configuring Windows registry audit settings on Windows Server 2012 and above")

## Configuring Windows registry audit settings on pre-Windows Server 2012 versions

**Step 1 –** On your target server, open **Registry Editor**: navigate to **Start → Run** and type *"regedit"*.

**Step 2 –** In the registry tree, expand the **HKEY\_LOCAL\_MACHINE** key, right-click **SOFTWARE** and select **Permissions** from the pop-up menu.

**Step 3 –** In the **Permissions for SOFTWARE** dialog, click **Advanced**.

**Step 4 –** In the **Advanced Security Settings for SOFTWARE** dialog, select the **Auditing** tab and click **Add**.

**Step 5 –** Select the **Everyone** group.

**Step 6 –** In the **Auditing Entry for SOFTWARE** dialog, select *"Successful"* for the following access types:

* **Set Value**
* **Create Subkey**
* **Delete**
* **Write DAC**
* **Write Owner**

![ManualConfig_WS_AuditingEntry2008](../../../../../../static/images/Auditor_10.7/Content/Resources/Images/Auditor/ManualConfig/ManualConfig_WS_AuditEnrty2008.png "ManualConfig_WS_AuditingEntry2008")

Repeat the same steps for the `HKEY_LOCAL_MACHINE\SYSTEM` key.

## Configuring Windows registry audit settings on Windows Server 2012 and above

**Step 1 –** On your target server, open **Registry Editor**: navigate to **Start → Run** and type *"regedit"*.

**Step 2 –** In the registry tree, expand the **HKEY\_LOCAL\_MACHINE** key, right-click **SOFTWARE** and select **Permissions** from the pop-up menu.

**Step 3 –** In the **Permissions for SOFTWARE** dialog, click **Advanced**.

**Step 4 –** In the **Advanced Security Settings for SOFTWARE** dialog, select the **Auditing** tab and click **Add**.

**Step 5 –** Click **Select a principal link** and specify the **Everyone** group in the **Enter the object name to select** field.

**Step 6 –** Set **Type** to *"Success"* and **Applies to** to *"This key and subkeys*.

**Step 7 –** Click **Show advanced permissions** and select the following access types:

* Set Value
* Create Subkey
* Delete
* Write DAC
* Write Owner

![Config_WS_AuditingEntry_2016](../../../../../../static/images/Auditor_10.7/Content/Resources/Images/Auditor/ManualConfig/ManualConfig_WS_AuditEnrty_2016.png "Config_WS_AuditingEntry_2016")

Repeat the same steps for the `HKEY_LOCAL_MACHINE\SYSTEM` key.

Using Group Policy for configuring registry audit is not recommended, as registry DACL settings may be lost.
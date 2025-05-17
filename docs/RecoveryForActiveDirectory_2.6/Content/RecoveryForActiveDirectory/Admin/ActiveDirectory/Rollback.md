---
sidebar_position: 6980
title: Rollback Objects
---

# Rollback Objects

You can revert an Active Directory object to its previous state.

Follow the steps to roll back an Active Directory object, including user accounts, groups, and organizational units.

**Step 1 –** Click Active Directory in the left pane to open the [Active Directory Page](Overview "Active Directory Page").

**Step 2 –** Select and expand a domain in the left pane and locate the object you want to rollback.

**Step 3 –** Do one of the following:

* Select the object to rollback and click the **Rollback** button.
* Right-click the object and select **Rollback** on the shortcut menu.

The Object Rollback wizard opens.

![Object Rollback wizard - Object Backup page](../../../../../../static/images/RecoveryForActiveDirectory_2.6/Content/Resources/Images/RecoveryForActiveDirectory/Console/Wizard/ObjectRollback/ObjectBackups.png "Object Rollback wizard - Object Backup page")

**Step 4 –** In the Backup Date section, select a backup to use for the rollback operation. Then select the checkbox(es) for the attributes you want to roll back. Click **Next**.

![Object Rollback wizard - Options page](../../../../../../static/images/RecoveryForActiveDirectory_2.6/Content/Resources/Images/RecoveryForActiveDirectory/Console/Wizard/ObjectRollback/Options.png "Object Rollback wizard - Options page")

**Step 5 –** Select a domain controller where the rollback changes will get affected. Options are:

* Use any writable domain controller – The system picks any writable domain controller in the domain for the rollback operation
* Use a specific domain controller – Select a domain controller from the drop-down menu for the rollback operation

**Step 6 –** Click **Next**.

![Object Rollback wizard - Credentials page](../../../../../../static/images/RecoveryForActiveDirectory_2.6/Content/Resources/Images/RecoveryForActiveDirectory/Console/Wizard/ObjectRollback/Credentials.png "Object Rollback wizard - Credentials page")

**Step 7 –** The account preforming the operation must have Domain Admin privileges to access the domain tree area where the object resides. On the Credentials page:

* If the account specified during domain configuration has Domain Admin privileges, click **Next**.
* If the domain account does not have Domain Admin privileges, select the **Use alternate credentials to perform the object rollback** checkbox and enter an account with Domain Admin privileges, then click **Next**.

For a Least Privilege Access Model to provision an Active Directory security group with the permissions that are necessary to perform backups, rollbacks and recovery, see the [Least Privilege Access Model](../../Requirements/TargetDomain#Least "Least Privilege Access Model") topic.

![Object Rollback wizard - Confirm page](../../../../../../static/images/RecoveryForActiveDirectory_2.6/Content/Resources/Images/RecoveryForActiveDirectory/Console/Wizard/ObjectRollback/Confirm.png "Object Rollback wizard - Confirm page")

**Step 8 –** The Confirm page displays a summary of the settings you provided on the pages of the wizard. Use the Back button to return to a previous page and change any setting. Click **Complete** to finish the wizard.

![Object Rollback Sucessful message](../../../../../../static/images/RecoveryForActiveDirectory_2.6/Content/Resources/Images/RecoveryForActiveDirectory/Console/Wizard/ObjectRollback/ObjectRollbackCompleted.png "Object Rollback Sucessful message")

**Step 9 –** A completed message is displayed when the rollback is successful. Click **OK**.

The object has been rolled back.
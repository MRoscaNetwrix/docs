# Start Agent

If the Agent has stopped on a server, it no longer monitors and captures events. You must restart it
on the server to enable it to monitor and capture the desired events.

Follow the steps to start a stopped Agent on a server.

**Step 1 –** Click Agents in the left pane to launch the Agents interface.

**Step 2 –** Right-click a server/Agent and select **Start Agent** on the menu.

![Enter Credentials window](/img/versioned_docs/threatprevention_7.4/threatprevention/install/upgrade/entercredentials.png)

**Step 3 –** On the Enter Credentials window, enter a username and password with sufficient rights
to connect to the target machine and query information about shares. A local Administrator account
on the target machine should have access to the system shares. Click **OK** after entering the
credentials.

**NOTE:** The wizard does not block access to the Administration Console and can be minimized while
actions are in progress. If this wizard is hidden by clicking outside of the dialog box, a flashing
blue link displays on the upper right corner of the interface with the action name displayed. Click
this link to bring back the focus to the wizard.

**Step 4 –** On the Start Agent window, the Agent will be started. One of two status messages
display:

- Failed – Read the failure messages and close the window. Ensure any error messages are taken care
  of prior to the next attempt.
- Completed – Indicates that the task is completed

**Step 5 –** When the task is successfully completed, click **Finish** to close the window.

The Agent has been started on the server.

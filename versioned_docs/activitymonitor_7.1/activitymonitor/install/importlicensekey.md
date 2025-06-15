# Import License Key

The Activity Monitor comes with a temporary 10-day license. Uploading a new license key or importing
a Enterprise Auditor key can be done from the Activity Monitor Console. If the Activity Monitor
Console is installed on a server where Enterprise Auditor has already been installed, it reads the
license information from the Enterprise Auditor installation directory.

Follow the steps to import a license key file.

![Activity Monitor Installation with Trial License](/img/versioned_docs/activitymonitor_7.1/activitymonitor/install/triallicense.png)

**Step 1 –** Click the **Licensed to: &lt;Trial User&gt;** hyperlink in the lower-left corner of the
Console. Alternatively, click the **View License** link in the yellow warning bar at the top. The
License Information window opens.

![Trial License Information](/img/versioned_docs/activitymonitor_7.1/activitymonitor/install/triallicenseinfo.png)

**Step 2 –** Click Load New License File and navigate to where the key is located. A Windows file
explorer opens.

![Open Dialog Box to load New License File](/img/versioned_docs/activitymonitor_7.1/activitymonitor/install/loadlicense.png)

**Step 3 –** Select the `.lic` file and click Open. The selected license key is then read.

![Activity Monitor License Information](/img/versioned_docs/activitymonitor_7.1/activitymonitor/install/licenseinfo.png)

**Step 4 –** In the License Information window, click **Apply** to import the License Key.

![Activity Monitor with License](/img/versioned_docs/activitymonitor_7.1/activitymonitor/install/licenseadded.png)

**Step 5 –** The organization's license key is now imported into the Activity Monitor. The Console
returns to the Agents tab and is ready to deploy activity agents.

**NOTE:** License keys are crafted for companies based on their preference for Active Directory,
Microsoft Entra ID (formerly Azure AD), File System, SharePoint, and SharePoint Online monitoring.
Any environment that is omitted from the license has its corresponding features disabled.

Once a key has expired, the Console displays an Open License File… option for importing a new key.
Once a new key is loaded, the Console returns to the Agents tab.

# Monitor NAS Devices

Monitoring a NAS device first requires the Netwrix Activity Monitor to have an Activity agent deployed and configured to monitor the device. A Threat Prevention Agent must be deployed on the same Windows server hosting the Activity agent. Once monitoring begins, follow the steps to configure a Threat Prevention policy to monitor file system changes.

__NOTE:__ The Threat Prevention policy does not change what the Activity Monitor agent is monitoring. It reads information collected by the Activity Monitor and applies any additional filters defined in the policy. Therefore, it is necessary for the Activity Monitor agent to be configured to monitor the desired activity.

Follow the steps to monitor NAS devices.

__Step 1 –__ In Threat Prevention, create a new policy.

__Step 2 –__ On the Event Type tab of the policy, add the __File System Changes__ event type.

__Step 3 –__ In the Event Filters section, go to the Paths filter tab and click the __Add__ button in the Include Paths area to open the [Select File System Objects Window](/docs/product_docs/threatprevention/threatprevention/admin/policies/eventtype/window/selectfilesystemobjects.md).

_Remember,_ any files or folders to be excluded need to be a subset of a folder identified in the Include Paths area.

__Step 4 –__ Connect to the Threat Prevention Agent deployed to a Windows server hosting the Activity agent. The local drives of the Windows server and all NAS devices being monitored by the Activity agent are listed in the Navigation pane.

__Step 5 –__ Select the desired NAS device in the Navigation pane and type the path(s) to be monitored by this policy in the Results pane, one path per row.

The paths entered can be file or folder names.

- For example, type c:\HR\NewHireProcess.doc for a NAS device with 192.168.16.188 as IP address, and it appears in the paths list as c:\HR\NewHireProcess.doc (\192.168.16.188).

> __NOTE:__ Unlike Windows path, NAS paths are not validated by Threat Prevention. You must accurately enter the path of the file or folder to be monitored. The format of the paths needs to match the data in the TSV files produced by the Netwrix Activity Monitor agent. The Search feature in the Netwrix Activity Monitor can be used to validate path formats. See the [Netwrix Activity Monitor Documentation](https://helpcenter.netwrix.com/category/activitymonitor) for additional information.

__Step 6 –__ Click __OK__ to close the Select File System Objects window.

__Step 7 –__ Save the policy.

The NAS paths are now added to the list of paths to be monitored.

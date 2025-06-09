# Change Log Level

The ```AccessInformationCenter.Service.exe.Config``` file is located in the ```Logs``` folder of the Access Reviews installation directory:

...\Netwrix\Access Reviews

Follow the steps to modify the log level.

__Step 1 –__ Open the ```AccessInformationCenter.Service.exe.Config``` file in a text editor, e.g. Notepad.

![AccessInformationCenter.Service.exe.Config file in Notepad](/img/product_docs/auditor/access/reviews/admin/troubleshooting/logvalue.png)

__Step 2 –__ The level value is set in the ```LogLevel``` parameter, where "2" is the default level. As the logging level increases from 0 to 3, the types of information and level of detail included within the log file also increase. Change to the desired log level:

<add key="LogLevel" value="2" />

- Error level is when ```value="0"```
- Warning level is when ```value="1"```
- Info level is when ```value="2"```
- Debug level is when ```value="3"```

  - Debug logging can be enabled from the Diagnostics page of the Configuration interface

__Step 3 –__ Save and close the ```AccessInformationCenter.Service.exe.Config``` file.

Once troubleshooting has finished, it is recommended to return the log level to the default level, Info = 2, to prevent the log file from growing too large.

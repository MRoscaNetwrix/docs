# Enable Remote Registry and Windows Management Instrumentation Services

Follow the steps to enable the Remote Registry service.

__Step 1 –__ Navigate to Start > Windows Administrative Tools > Services.

![Services Console](/img/product_docs/1secure/configuration/computer/manualconfig_genevents_remoteregistry2016.webp)

__Step 2 –__ In the Services window, locate the Remote Registry service, right-click it and select __Properties__.

__Step 3 –__  In the Remote Registry Properties dialog box, make sure the Startup type parameter is set to _Automatic_ and click __Start__.

![Remote Registry Properties dialog box](/img/product_docs/1secure/configuration/computer/manualconfig_genevents_remoteregistry_start2016.webp)

__Step 4 –__ In the Services window, ensure that the Remote Registry service has the _Running_ status on Windows Server 2012 and above.

__NOTE:__ The Remote Registry service should be enabled on the target server.

5. Locate the Windows Management Instrumentation service and repeat these steps.

---
id: enable-secondary-logon-service
title: "Enable Secondary Logon Service"
pagination_label: "Enable Secondary Logon Service"
sidebar_label: "Enable Secondary Logon Service"
sidebar_position: 110
description: "Learn how to enable the Secondary Logon service on the computer where Netwrix Cloud Agent resides."
---

# Enable Secondary Logon Service

**Step 1 –** On the computer where Netwrix Cloud Agent resides, navigate to **Start** > **Windows
Administrative** Tools (Windows Server 2016 and higher) or Administrative Tools (Windows 2012) **>
Services**.

**Step 2 –** In the **Services** dialog, locate the **Secondary Logon** service.

**Step 3 –** Right-click the service and on the **General** tab make sure that **Startup type** for
this service is other than _Disabled_. Startup type can be either _Automatic_ or _Manual_.

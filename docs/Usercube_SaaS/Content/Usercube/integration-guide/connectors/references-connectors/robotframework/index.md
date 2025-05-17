---
sidebar_position: 540
title: Robot Framework
---

# Robot Framework

This connector writes to an external system via a [Robot Framework](https://robotframework.org) script.

This page is about [Robot Framework](../../references-packages/robot-framework/index "Robot Framework")

![Package: Custom/Robot Framework](../../../../../../../../static/images/Usercube_SaaS/Content/Resources/Images/Packages_robot_V603.png)

## Overview

Robot Framework is an open-source automation framework which can be used for robotic process automation (RPA). This framework is easy to use thanks to its human-readable syntax.  
It has a modular architecture that can be extended by [libraries](https://robotframework.org/#libraries) implemented with Python or Java. These libraries provide various tools to interact with a managed system.

## Prerequisites

Implementing this connector requires the agent to include the following elements:

* [Python](https://www.python.org/downloads/) 3.7 or above. Specific Robot Framework libraries may require a specific Python version;
* Python folder location in the `PATH` environment variable list and the location of its subfolder `Scripts`;
* Robot Framework: use `pip install robotframework` in the command prompt. If the installation ran correctly, `robot.exe` should be in your path. You can confirm this by running `gcm robot` in a powershell console.

## Export

There are no export capabilities for this connector.

## Fulfill

This connector can create, update and/or delete any entity linked to the managed system.

### Configuration

This process is configured through a [Connection](../../../toolkit/xml-configuration/connectors/connection/index "Connection") in the UI and/or the XML configuration, and in the `appsettings.agent.json > Connections` section:

```
appsettings.agent.json
{
  ...
  "Connections": {
    ...
    "": {
      ...
    }
  }
}
```
:::note
The identifier of the connection and thus the name of the subsection must:
- be unique.
- not begin with a digit.
- not contain , :, ", /, \, |, ?, \* and \_.
:::

> The following example fills in a CSV file by using the script `FulfillRobotFramework.robot`:
>
> ```
> appsettings.agent.json
> {
>   "Connections": {
>     ...
>     "RobotFrameworkFulfillment": {
>       "RobotFrameworkScriptPath": "C:/UsercubeDemo/Scripts/FulfillRobotFramework.robot",
>       "Options": {
>         "Message": "Hello"
>       }
>     }
>   }
> }
> ```
#### Setting attributes

| Name | Details |
| --- | --- |
| RobotFrameworkScriptPath required | **Type**  String  **Description** Path to the executed Robot Framework script (.robot). |
| Options optional | **Type**  String Pair List  **Description** List of key-value pairs for all the variables required by the PowerShell script. **Example** `"Options": {  "Login": "admin",  "Password": "secret" }`  Access these options in the script using the following method:  `${login}= Get Secure Data Login False ${password}= Get Secure Data Password True`  **Info:** when the boolean argument from `Get Secure Data` is set to `True`, then the value is stored in the variable and erased from memory, hence not retrievable on next call. This enables control over sensitive data like passwords by defining the lifetime of the variable containing sensitive data. **Warning:** never use `Get Secure Data` when `Options` is empty. |

### Write a script

See how to[Write a Robot Framework Script](../../how-tos/write-fulfill-robotframework-script/index "Write a Robot Framework Script") to allow provisioning with this connector.

## Authentication

### Password reset

The script manages password reset.

### Credential protection

Data protection can be ensured through:

* [Connection](../../../toolkit/xml-configuration/connectors/connection/index "Connection"), configured in the `appsettings.encrypted.agent.json` file;
* an [Connection](../../../toolkit/xml-configuration/connectors/connection/index "Connection") safe;

| Attribute | Naming Convention for the Key in Azure Key Vault |
| --- | --- |
| Login (optional) | `Connections----Options--Login` |
| Password (optional) | `Connections----Options--Password` |
| RobotFrameworkScriptPath | `Connections----RobotFrameworkScriptPath` |

* A [Connection](../../../toolkit/xml-configuration/connectors/connection/index "Connection") able to store the attributes from the `Options` section that are compatible with CyberArk.

Protected attributes are stored inside a safe in CyberArk, into an account whose identifier can be retrieved by Identity Manager from `appsettings.cyberark.agent.json`.

> For example, consider `Login` and `Password` values stored in the `RobotFramework_Account` account:
>
> ```
> appsettings.cyberark.agent.json
> {
>   "Connections": {
>     ...
>     "RobotFrameworkFulfillment": {
>       "Options": {
>         "Login": "RobotFramework_Account",
>         "Password": "RobotFramework_Account"
>       }
>     }
>   }
> }
> ```
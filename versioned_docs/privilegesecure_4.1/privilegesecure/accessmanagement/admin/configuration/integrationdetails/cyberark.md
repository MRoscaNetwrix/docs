# Advanced CyberArk Settings

Use the Advanced CyberArk Settings to override the default behavior of the CyberArk connector. This section provides the option to enter customer PowerShell scripts that Privilege Secure will use to check out and check in accounts.

## SkipCertificateCheck

Allows the rest call to skip the certificate check for the built-in check out step.

## CheckoutScriptBlock

Supply a PowerShell script block to be used for checking out password from CyberArk. The script block will be called with two arguments. It is recommended to use a param() block as follows:

param(

        [Parameter(Mandatory = $true)]

$Options,

        [Parameter(Mandatory = $true)]

        $Credential

    )

The scriptblock must return the updated $Credential setting the Username, Domain and Password value to the values that represent the information for the account checked out. The default implementation will set these values to the returned Username, Address and Content of the response from the API call of the Central Credential Provider.

$Options will have settings from the BYOV connector and information populated by the activity session.

| Variable Name | Definition | Example Value |
| --- | --- | --- |
| $Options.Connector | The options defined by the connector configuration. |  |
| $Options.Connector.Name | The connector name | CyberArk |
| $Options.Connector.Id | The connector GUID identifier | 45adf881-2875-485f-b789-80ea6ba03623 |
| $Options.Connector.Options.ApiURL | The base URL for the CyberArk Central Credential Provider webservice. The script will append /AIMWebService/api/Accounts to this URL. For more information on the Central Credential Provider you can reference [Central Credential Provider Webservice Configuration](https://docs.cyberark.com/Product-Doc/OnlineHelp/AAM-CP/Latest/en/Content/CCP/Configure_CCPWindows.htm?tocpath=Administration%7CCentral%20Credential%20Provider%7CCentral%20Credential%20Provider%20Webservice%20Configuration%7C_____0) | https://vault.example.com |
| $Options.Connector.Options.Appid | The application id to be used by Privilege Secure to make requests. | privilegesecure |
| $Options.Connector.Options.ClientCertificate | Thumbprint of certificate to use for client certificate authentication, leave empty if client certificates are not used. The certificate must be installed into the certificate store of the ActionService machine. | 64D25855C84CCDC581799b49362BA13DB66BD795 |
| $Options.Connector.Options.SkipCertificateCheck | Whether or not to skip the certificate check. | True  False |
| $Options.ActivitySession | The ActivitySession members of the $Options object only exist if the checkout happens during an Activity Session. |  |
| $Options.ActivitySession.LoginAccountNameFormat | The template used by the activity session to generate the LoginAccountName | %targetdomainname%\%samaccountname%-a |
| $Options.ActivitySession.LoginAccountName | The generated LoginAccountName | PrivilegeSecure\username-a |
| $Options.ActivitySession.UserId | The GUID identifier of the requesting user | 45adf881-2875-485f-b789-80ea6a03623 |
| $Options.ActivitySession.TargetUserId | The GUID identifier of the target user for the activity session | 45adf881-2875-485f-b789-80ea6a03623 |
| $Options.ActivitySession.TargetId | The GUID identifier of the target host for the activity session | 45adf881-2875-485f-b789-80ea6a03623 |
| $Options.TargetHost | The host record associated with the activity session |  |
| $Options.TargetHost.Id | The GUID identifier of the target host | 45adf881-2875-485f-b789-80ea6a03623 |
| $Options.TargetHost.DistinguishedName | The Active Directory distinguished name of the host | CN=PrivilegeSecure,CN=Computers,DC=example,DC=com |
| $Options.TargetHost.DnsHostName | The FQDN of the target host | PrivilegeSecure.example.com |
| $Options.TargetHost.IPAddress | The IPv4 Address of the target host | 192.168.1.1 |
| $Options.TargetHost.Name | The Name of the target host | Example\privilegesecure |
| $Options.TargetHost.NetBiosName | The NETBIOS name of the target host | PRIVILEGESECURE |
| $Options.TargetHost.ObjectSid | The Sid of the computer | S-1-5-21-2801403971-1535060088-5098816251143 |
| $Options.TargetHost.Samaccountname | The Domain and Samaccountname of the computer | EXAMPLE\PRIVILEGESECURE$ |

$Credential has the values for the Credential generated for lookup, on Checkout the username/domain/password will most likely be a random value not related to the account to be checked out.

| Variable Name | Definition | Example Value |
| --- | --- | --- |
| $Credential.Username | The username to be checked out, this should be updated with the actual name of the account that was checked out. | Username |
| $Credential.Domain | The domain name of the user to be checked out, this should be updated with actual domain OR computer name if local computer account | Example  Example.com  HOST  HOST.EXAMPLE.COM |
| $Credential.Password | On checkout this will have a random value, overwrite this with the actual password given by the vault |  |
| $Credential.SudoCommand | The command to use for performing elevated commands on a Linux/Unix based system. Add a value to override the default of “sudo” | sudo |
| $Credential.PasswordValueConnectorId | The vault connector GUID identifier for this credential. This has the same value as the $Options.Connector.Id |  |
| $Credential.PasswordVaultInfo | A JSON string that contains vault specific options for this credential |  |

The custom script block should return the $Credential object passed in, updated with any relevant information.

## CheckinScriptBlock

Supply PowerShell script block to be used for checking in password from CyberArk. The script block will be called with two arguments. It is recommended that you use a param() block as follows:

```    param(```

```        [Parameter(Mandatory = $true)]```

```        $Options,```

```        [Parameter(Mandatory = $true)]```

```        $Credential```

```    )```

The scriptblock must return the updated $Credential setting the Username, Domain and Password value to the values that represent the checked in account information. The default implementation will set these values to the returned Username, Address and Content of the response from the API call of the Central Credential Provider.

$Options will have settings from the BYOV connector and information populated by the activity session.

| Variable Name | Definition | Example Value |
| --- | --- | --- |
| $Options.Connector | The options defined by the connector configuration. |  |
| $Options.Connector.Name | The connector name | CyberArk |
| $Options.Connector.Id | The connector GUID identifier | 45adf881-2875-485f-b789-80ea6ba03623 |
| $Options.Connector.Options.ApiURL | The base URL for the CyberArk Central Credential Provider webservice. The script will append /AIMWebService/api/Accounts to this URL. For more information on the Central Credential Provider you can reference [Central Credential Provider Webservice Configuration](https://docs.cyberark.com/Product-Doc/OnlineHelp/AAM-CP/Latest/en/Content/CCP/Configure_CCPWindows.htm?tocpath=Administration%7CCentral%20Credential%20Provider%7CCentral%20Credential%20Provider%20Webservice%20Configuration%7C_____0) | https://vault.example.com |
| $Options.Connector.Options.Appid | The application id to be used by Privilege Secure to make requests. | PrivilegeSecure |
| $Options.Connector.Options.ClientCertificate | Thumbprint of certificate to use for client certificate authentication, leave empty if client certificates are not used. The certificate must be installed into the certificate store of the ActionService machine. | 64D25855C84CCDC581799B49362BA13DB66BD795 |
| $Options.Connector.Options.SkipCertificateCheck | Whether or not to skip the certificate check. | True  False |
| $Options.ActivitySession | The ActivitySession members of the $Options object only exist if the checkin happens during an Activity Session. |  |
| $Options.ActivitySession.LoginAccountNameFormat | The template used by the activity session to generate the LoginAccountName | %targetdomainname%\%samaccountname%-a |
| $Options.ActivitySession.LoginAccountName | The generated LoginAccountName | PrivilegeSecure\username-a |
| $Options.ActivitySession.UserId | The GUID identifier of the requesting user | 45adf881-2875-485f-b789-80ea6ba03623 |
| $Options.ActivitySession.TargetUserId | The GUID identifier of the target user for the activity session | 45adf881-2875-485f-b789-80ea6ba03623 |
| $Options.ActivitySession.TargetId | The GUID identifier of the target host for the activity session | 45adf881-2875-485f-b789-80ea6ba03623 |
| $Options.TargetHost | The host record associated with the activity session |  |
| $Options.TargetHost.Id | The GUID identifier of the target host | 45adf881-2875-485f-b789-80ea6ba03623 |
| $Options.TargetHost.DistinguishedName | The Active Directory distinguished name of the host | CN=PRIVILEGESECURE,CN=Computers,DC=example,DC=com |
| $Options.TargetHost.DnsHostName | The FQDN of the target host | PrivilegeSecure.example.com |
| $Options.TargetHost.IPAddress | The IPv4 Address of the target host | 192.168.1.1 |
| $Options.TargetHost.Name | The Name of the target host | Example\privilegesecure |
| $Options.TargetHost.NetBiosName | The NETBIOS name of the target host | PRIVILEGESECURE |
| $Options.TargetHost.ObjectSid | The Sid of the computer | S-1-5-21-2801403971-1535060088-509881625-1143 |
| $Options.TargetHost.Samaccountname | The Domain and Samaccountname of the computer | EXAMPLE\PRIVILEGESECURE$ |

$Credential has the values for the Credential generated for lookup, on Checkin the username/domain/password will most likely be a random value not related to the account to be checked in.

| Variable Name | Definition | Example Value |
| --- | --- | --- |
| $Credential.Username | The username to be checked in. | Username |
| $Credential.Domain | The domain name of the user to be checked in. | Example  Example.com  HOST  HOST.EXAMPLE.COM |
| $Credential.Password | The existing known password for the account to be checked in. |  |
| $Credential.SudoCommand | The command to use for performing elevated commands on a Linux/Unix based system. | sudo |
| $Credential.PasswordValueConnectorId | The vault connector GUID identifier for this credential. This has the same value as the $Options.Connector.Id |  |
| $Credential.PasswordVaultInfo | A JSON string that contains vault specific options for this credential |  |
| $Credential.PasswordVaultInfo | A JSON string that contains vault specific | { “safe”: “safename”, “folder”: “root” } |

Your custom script block should return the $Credential object passed in, updated with any relevant information.

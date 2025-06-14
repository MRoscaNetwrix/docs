# Export the Configuration

This guide shows how to export the configuration as XML files to a given folder.

## Overview

The process for configuration export varies according to the situation:

- when working on-premise, the configuration must be exported locally;
- when working SaaS, the configuration must be exported remotely.

[See more details on configuration export](/versioned_docs/usercube_6.1/usercube/integration-guide/executables/references/export-configuration/index.md).

## Export the Configuration Locally

Export your configuration by using the [```Export-Configuration``` executable](/versioned_docs/usercube_6.1/usercube/integration-guide/executables/references/export-configuration/index.md#export-configuration-executable) and declaring at least:

- the directory where the configuration is to be exported to;
- the connection string of the database.

> ```
>
> ./Usercube-Export-Configuration.exe --database-connection-string "data source=.;Database=Usercube;Integrated Security=SSPI;Min Pool Size=10;encrypt=false;" --configuration-directory "C:/Usercube/ExportedConf"
>
> ```

## Export the Configuration Remotely

Export a SaaS configuration by proceeding as follows:

1. Log in for configuration deployment/export with the [```Login``` executable](/versioned_docs/usercube_6.1/usercube/integration-guide/executables/references/login/index.md).

   Usercube provides an Open Id Connect (OIDC) authentication process in order to ensure strong security, visibility and ease of use.
     
   NETWRIX recommends using Usercube's dedicated in-house OIDC Identity Provider (IDP), but you can also use your own IDP if you want to manage authentication yourself.
     
   When using your own IDP, make sure that the IDP implements a valid OIDC protocol and serves id tokens.

   > For example, when using Usercube's IDP:
   >
   > ```
   >
   > ./Usercube-Login.exe
   >
   > ```

   > For example, when using another IDP:
   >
   > ```
   >
   > Usercube-Login.exe --authority https://my_oidc_authentication_server.com --client-id 34b3c-fb45da-3ed32
   >
   > ```

   Either method will open your default browser to ```http://localhost:5005``` where you will be redirected to the specified IDP and will be prompted to log in.

   Specify ```--port <port>``` if you want the login page to use another local port.

   If you have already successfully deployed or exported your SaaS configuration at least once, then there is no need to communicate the authentication information again. Go directly to step 4.
     
   However, if, since then, there has been a change in the identity deploying/exporting the configuration or in the Identity Provider used to log in at step 1, then go through the whole process again.
2. Log in to the IDP to be redirected back to this screen:

   ![Usercube-Login.exe Success Screen](/img/versioned_docs/usercube_6.1/usercube/integration-guide/toolkit/how-tos/export-configuration/usercube-login_success_v602.png)

   Once authenticated, an identification token is stored on your local machine for the authentication to Usercube's deployment and export processes.
3. Copy the entire text within the blue square and send it to your Usercube administrator.

   The administrator will add the identity information to the configuration of your Usercube instance, to allow the configuration deployment/export.

4. Export the configuration by using the [```Export-Configuration``` executable](/versioned_docs/usercube_6.1/usercube/integration-guide/executables/references/export-configuration/index.md#export-configuration-executable) and declaring at least:

   - the configuration directory;
   - the API URL of your Usercube instance.
   > ```
   >
   > ./Usercube-Export-Configuration.exe -d "C:\Usercube\ExportedConf" --api-url https://my_usercube_instance.com
   >
   > ```

   You can export the configuration by launching only the ```Export-Configuration``` executable until the authentication token expires. Then, the token must be refreshed via the ```Login``` executable before exporting again.
     
   The token served by Usercube's IDP expires after one hour.

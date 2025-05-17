---
sidebar_position: 1036
title: End-User Authentication
---

# End-User Authentication

## Overview

Before end-users can connect to Identity Manager through the UI, they will have to authenticate.

Identity Manager supports seven authentication methods organized into two categories: Internal methods and External methods.

It is highly recommended that you use an External method. Internal methods are mostly used for debug, test and development purposes.

Internal methods

The Internal methods use Identity Manager Server's internal authentication server. They rely on one of these Identity Server User Stores:

* Test User Store, used in development environments.
* Active Directory User Store, using an Active Directory to authenticate.

External methods

External methods use external authentication providers.

Identity Manager supports five types of external authentication providers of which four are based on different flavors of the OAuth 2.0 protocol, and the last one is integrated with Windows.

The types of authentication providers supported by Identity Manager are:

* [OpenIdConnect](https://openid.net/connect/)
* [WS-Federation](http://docs.oasis-open.org/wsfed/federation/v1.2/ws-federation)
* [OAuth](https://tools.ietf.org/html/rfc6749)
* [SAML2](http://docs.oasis-open.org/security/saml/Post2.0/sstc-saml-tech-overview-2.0)
* [Integrated Windows Authentication (IWA)](https://docs.microsoft.com/en-us/aspnet/web-api/overview/security/integrated-windows-authentication)

Using more than one provider

For each authentication method, one or several authentication providers can be set up. If several authentication providers are set up, end-users will be prompted to choose their preferred method of authentication.

Internal method & test mode form:

![](../../../../../../../../static/images/Usercube_6.2/Content/Resources/Images/authent_1.png)

External method prompt:

![](../../../../../../../../static/images/Usercube_6.2/Content/Resources/Images/authent_2.png)

## Identity Server RSA Key Pair

A public key certificate and a private key are used to handle encrypted communication with external authentication providers. This is used, for example, by the Identity Manager Server to retrieve the provider's signing key. It is mandatory to validate JWT tokens in an OAuth-flavor scenario.

This information can be set one of two ways:

* As a [PKCS #12](https://en.wikipedia.org/wiki/PKCS_12) archive (also called `.pfx` file) stored in the Agent's host file system. The archive contains both the public key certificate and the private key.
* As a certificate from a Windows' [certificate store](https://docs.microsoft.com/en-us/dotnet/framework/wcf/feature-details/working-with-certificates#certificate-stores) identified by SubjectDistinguishedName or by Thumbprint. The Windows certificate also contains both the public key certificate and the private key.

### PFX file

The archive is set using the following attributes on the appsettings > IdentityServer section:

* X509KeyFilePath is the [PKCS #12](https://en.wikipedia.org/wiki/PKCS_12) archive path on the Agent's host file system.
* X509KeyFilePassword (optional) is the [PKCS #12](https://en.wikipedia.org/wiki/PKCS_12) archive password.

Example

Code attributes enclosed with  need to be replaced with a custom value before entering the script in the command line.

```
"": {  
    "X509KeyFilePath":C:/UsercubeAgentContoso/contoso.pfx",  
    "X509KeyFilePassword": "oarjr6r9f00"  
  }  

```
### Certificate

The certificate from a Windows certificate store is set up using these attributes on the appsettings > IdentityServer section:

| Name | Description |
| --- | --- |
| X509SubjectDistinguishedName optional (if Thumbprint is non-empty) | Sets the store certificate's SubjectDistinguishedName. |
| X509Thumbprint optional (if DistinguishedName is non-empty) | Sets the store certificate's Thumbprint. |
| X509StoreLocation required | Sets the Relevant Windows certificate store's location: `LocalMachine` or `CurrentUser`. |
| X509StoreName required | Sets the relevant Windows certificate store's name. |

Example

Code attributes enclosed with  need to be replaced with a custom value before entering the script in the command line.

```
"": {  
    "X509SubjectDistinguishedName":"",  
    "X509StoreLocation": "",  
    "X509StoreName": ""  
}  

```
**NOTE:** Identity Manager Server won't start if the [PKCS #12](https://en.wikipedia.org/wiki/PKCS_12) archive set up during this step is identical to the one provided with the SDK. Users must provide their own certificate. Self-signed certificates are accepted as valid. See the[Install the Server](../../../../installation-guide/production-ready/server/index "Install the Server")topic for additional information.

## Configuration Section Description

Authentication is set up using the following two sections of the Server's appsettings set:

* IdentityServer
* Authentication

```
{  
    "IdentityServer":{  
        ...  
    },  
    "Authentication":{  
        ...  
    }  
}  

```
The authentication section mostly fits the following pattern:

Code attributes enclosed with  need to be replaced with a custom value before entering the script in the command line.

```
"":{  
    :{  
          :{  
                  ...  
          },  
          ....,  
          :{  
                  ...  
          },  
    },  
    :{  
          :{  
                  ...  
          },  
          ....,  
          :{  
                  ...  
          },  
    }  
}  

```
Several authentication providers can be defined (here above,  to ), using one or several authentication protocols (here above,  and ).

Most of the authentication providers need the user to choose an AuthenticationScheme. It is a string that will be used to uniquely identify this authentication method in Identity Manager. Its goal is to enable Identity Manager's testers to identify which authentication method is used in the logs or in the code, with a mnemonic name. Any name can be used as long as all AuthenticationSchemes are different.

**NOTE:** This guide doesn't cover how to set up authorizations within Identity Manager. Authorization for an end-user to access Identity Manager resources relies on assigning roles to profiles. Identity credentials used for authentication must be linked to these profiles in the applicative configuration. See the [Various XML Settings](../../settings/index "Various XML Settings")topic for additional information.

Authentication-related settings are done through the following sections of the appsettings set:

* IdentityServer
* Authentication

See the[Architecture](../../../architecture/index "Architecture")topic for additional information.

### Identity Server

This is the general-purpose authentication settings section.

The Identity Server section allows the following attributes:

| Name | Type | Description |
| --- | --- | --- |
| Enabled (default value: true) | Boolean | Enables or disables the Identity Server. |
| AllowWindowsAuthentication (default value: false) | Boolean | Allows Windows authentication. Will work only when the Active Directory User Store is enabled. |
| ShowPII (default value: false) | Boolean | Sets whether or not PII is shown in logs. For security reasons, this setting should be used sparingly. |
| ValidationKeys (optional) | String Array | Allows the definition of public certificate paths for token validation. |
| IssuerURI (optional) | String | Sets the unique name of this server instance. |
| PostLogoutRedirectUri (optional) | String | Sets a specific URI to which the user will be redirected after a successful logout. |
| PublicOrigin (optional) | String | Sets the origin name for this Identity Manager Server instance. Useful if end-users authenticate through a proxy server. |
| X509File (required) | String | Is the [PKCS #12](https://en.wikipedia.org/wiki/PKCS_12) archive path on the Agent's host file system. |
| X509KeyFilePassword (optional) | String | Is the [PKCS #12](https://en.wikipedia.org/wiki/PKCS_12) archive password. |
| X509SubjectDistinguishedName (optional) | String | Sets the store certificate's SubjectDistinguishedName. |
| X509Thumbprint (optional) | String | Sets the store certificate's Thumbprint. |
| X509StoreLocation (required) | String | Sets the relevant Windows certificate store's location. |
| X509StoreName (required) | String | Sets the relevant Windows certificate store's name. |

### Authentication

This section contains specific settings for each configuration method.

At the root, the following properties can be used:

| Name | Type | Description |
| --- | --- | --- |
| Enabled default value: true | Boolean | Enables or disables authentication. |
| RequireHttpsMetadata default value: true | Boolean | Specifies whether HTTPS is required for the discovery endpoint. |
| AllowLocalLogin required | Boolean | If `true`, a Login Form replaces Windows Authentication. |
| CookieLifeTime default value: 8 | Int | Maximum duration (in hours) after which the session expires automatically. |
| LifeTimeSliding default value: 10 | Int | Duration (in minutes) after which the session expires automatically, if no action is taken during this time. |

Then, a subsection for every authentication method is used. Supported subsections are:

* OpenId
* OAuth
* WsFederation
* SAML2
* ActiveDirectoryUserStore
* TestUserStore

## Set Up Integrated Windows Authentication (IWA)

This authentication method can be used to authenticate users within an Active Directory domain using their respective domain account.

This authentication is silent: when an end-user tries to access Identity Manager, the browser retrieves identity credentials from the Windows session where the user is logged in and sends them to the domain controller for authentication. The domain controller confirms the user's identity and validates it for Identity Manager. The end-user doesn't have to input any credentials.

**NOTE:** If Integrated Windows Authentication is used, internal methods have to be disabled with the `"AllowLocalLogin":false` setting.

### Requirements

Setting up this authentication method requires the following:

* Identity Manager runs as an [Internet Information Services (IIS)](https://www.iis.net/) website.
* Windows Authentication is [enabled on Windows server](https://www.microsoft.com/en-us/evalcenter/evaluate-windows-server-2016).
* Windows Authentication is [enabled for the Usercube IIS](https://docs.microsoft.com/en-us/iis/configuration/system.webserver/security/authentication/windowsauthentication/#how-to-enable-windows-authentication-for-a-web-site-web-application-or-web-service) [enabled for the Usercube IIS website](https://docs.microsoft.com/en-us/iis/configuration/system.webserver/security/authentication/windowsauthentication/#how-to-enable-windows-authentication-for-a-web-site-web-application-or-web-service) website.

### Configuration

Integrated Windows Authentication is configured using the following sections:

1. Set the **IdentityServer** > **AllowWindowsAuthentication** attribute to `true`.
2. Set the **Authentication** > **AllowLocalLogin** attribute to `false`.

> The following example sets up Windows Authentication. Windows Server and IIS requirements have been checked.
>
> Code attributes enclosed with  need to be replaced with a custom value before entering the script in the command line.
>
> ```
> appsettings.json  
>   
> ...  
> "":{  
>     "AllowWindowsAuthentication":"",  
> },  
> "":{  
>     "AllowLocalLogin":"",  
> }  
> ...  
>
> ```
## Set Up an OpenID Connect Provider

One or several OpenID Connect authentication providers can be set up under the Authentication > OpenId section.

Multiple providers

One or several OpenID Connect authentication providers can be set up.

Registration process

Using an OpenID Connect authentication requires the Identity Manager Server to be registered to the provider. A ClientID and a ClientSecret are issued as a result of the registration process. They both allow Identity Manager to identify itself to the authentication provider. [[See an example](https://docs.microsoft.com/en-us/powerapps/maker/portals/configure/configure-openid-settings)](https://docs.microsoft.com/en-us/powerapps/maker/portals/configure/configure-openid-settings) of how to register Identity Manager to an Microsoft Entra ID (formerly Microsoft Azure AD) used as OpenID Connect provider.

Callback URL

The target OpenID Connect provider needs to be aware of the URI where to send the authentication token if the authentication succeeds. Depending on the provider, it is called a callback URL, a callback path, an authorization callback URL, or a redirect URI.

During the registration process, the provider will ask for the URL.

Identity Manager's callback URL for OpenID Connect is `/signin-oidc where  is the address of your Identity ManagerServer such as https://usercube.contoso.com.

Authority

An OpenID Connect provider is identified by its Authority, according to the [OpenID](https://openid.net/connect/) Connect specifications.

NameClaimType

To authorize an end-user, Identity Manager Server retrieves a specific claim (a key-value pair, transmitted through the OIDC-issued JWT token) returned by the provider and looks for a resource that matches this claim's value. The comparison is carried out according to the resource and property set as the end-user's identity in the applicative configuration. See the [Select User by Identity Query Handler Setting](../../../toolkit/xml-configuration/metadata/settings/selectuserbyidentityqueryhandlersetting/index "Select User By Identity Query Handler Setting")

The name of the claim that is retrieved for this purpose defaults to `sub` which is one of the standard [Claim names for the OpenID Connect protocol](https://openid.net/specs/openid-connect-core-1_0.html#StandardClaims). However, some providers might not fill the `sub` value with meaningful data, or use non-standard Claim names.

For this reason, the name of the claim that is retrieved by Identity Manager for authorization purposes can be set up according to the provider's specifics.

**NOTE:** Users should be able to get a list of the claim names used by their authentication providers from their providers' portal website, documentation or administrators.

For example, the following claim provides no meaningful `sub` value.

Code attributes enclosed with  need to be replaced with a custom value before entering the script in the command line.

```
{  
    "name": "",  
    "preferred_username": "",  
    "sub": ""  
}  

```
Using the following applicative configuration setting that sets `Ad_Entry:userPrincipalName` as the value to be matched against a claim in order to identify a user's profile, the `preferred_username` NameClaimType should be used.

Code attributes enclosed with  need to be replaced with a custom value before entering the script in the command line.

```
" ... />  

```
### Configuration

First, the OpenID Connect method must be enabled.

Under the OpenId section:

| Name | Type | Description |
| --- | --- | --- |
| Enabled required | Boolean | Enables or disables the OpenId connection. |

For each OpenID Connect provider to integrate, a new section is added under the OpenID subsection. Any section name can be used. This section name is only used as a means for the user to find the authentication method in the configuration files.

Under the new subsection, the following parameters are used to configure the authentication method:

| Name | Type | Description |
| --- | --- | --- |
| AuthenticationScheme required | String | Is the unique identifier of this authentication method within Identity Manager. Any string value can be used, unique among all authentication methods. |
| DisplayName optional | String | Is the provider display name. Chosen by the user, it is used in the UI to identify the authentication method. |
| ClientId required | String | Is the Client ID issued during the registration of Identity Manager to the chosen OpenID Connect provider. |
| ClientSecret required | String | Is the Client Secret issued during the registration of Identity Manager to the chosen OpenID Connect provider. |
| Authority required | String | This URL identifies the OpenID Connect provider for Identity Manager according to the [OpenID Connect specifications](https://openid.net/connect/). It can be retrieved from the target OpenID Connect provider documentation. For example, [Microsoft's documentation](https://docs.microsoft.com/en-us/azure/active-directory/develop/v2-protocols-oidc) indicates the Microsoft Identity Platform OpenID Connectauthority. |
| NameClaimType optional | String | Sets the type of the claim that will be retrieved by Identity Manager to identify the end-user. The retrieved claim will be compared against the resource and property set as the end-user's identity in the applicative configuration. See the [Select User by Identity Query Handler Setting](../../../toolkit/xml-configuration/metadata/settings/selectuserbyidentityqueryhandlersetting/index "Select User By Identity Query Handler Setting")topic for additional information. |
| Scopes optional | String | Sets the list of the requested [scopes](https://auth0.com/docs/scopes/openid-connect-scopes). By default, the requested scopes are: openid, profile and email. |
| SaveTokens default value: false | Boolean | Only for Okta providers. Set to `true if authentication uses an Okta provider. See the [Configure Okta](../../how-tos/okta/index "Configure Okta for Usercube Authentication")topic for additional information. |
| MetadataAddress optional | String | URL address of a copy of the metadata, used when the authority metadata cannot be accessed from the Identity Manager server, for example because of a firewall. |
| RequireHttpsMetadata default value: true | Boolean | By default the authority metadata must use HTTPS. Set to `false to use a simple HTTP metadata, in case a local copy of the metadata is used or for test environment. |
| ResponseMode optional | String | Response mode for OpenIdConnect.   * Query * FormPost * Fragment   [See OpenId documentation](https://openid.net/specs/openid-connect-core-1_0). |
| ResponseType optional | String | Response type for OpenIdConnect.   * Code * CodeIdToken * CodeIdTokenToken * CodeToken * IdToken * IdTokenToken * None * Token   See examples in the [OpenId documentation.](https://openid.net/specs/openid-connect-core-1_0.html#AuthorizationExamples) |

Example

This example configures an OpenId Connect authority located at .

This authentication provider is identified within the appsettings.json OpenId Connect providers list as OpenId1.

Within Identity Manager, it will be identified with the authentication scheme AzureOIDC.

It will be displayed as Connection Microsoft Entra ID with OIDC protocol in the UI external login prompt.

Code attributes enclosed with  need to be replaced with a custom value before entering the script in the command line.

```
{  
    "Authentication":  
    {  
        ...  
        "OpenId": {  
            "Enabled": "",  
            "OpenId1": {  
                "AuthenticationScheme": "",  
                "DisplayName": "",  
                "ClientId": "",  
                "ClientSecret": "",  
                "Authority": "",  
                "NameClaimType": "",  
                "Scopes": ["", ""]  
            }  
        }  
    }  
}  

```
## Set Up an OAuth Provider

One or several OAuth authentication providers can be set up under the authentication > OAuth section.

Multiple providers

One or several OAuth authentication providers can be set up.

Registration process

Using an OAuth authentication requires Identity Manager Server to be registered to the provider. A ClientID and a ClientSecret are issued as a result of the registration process. They both allow Identity Manager to identify itself to the authentication provider.

#### Callback URL

The target OAuth provider needs to be aware of the URI where to send the authentication token if the authentication succeeds. Depending on the provider, it is called a callback URL, a callback path, an authorization callback URL, or a redirect URI.

During the registration process, the provider will ask for the URL.

Identity Manager's callback URL for OAuth is / where  is the address of your Identity Manager Server such as https://usercube.contoso.com and  can be set up to any value chosen by the user using the CallbackPath configuration attribute. The only constraint is to make sure the CallbackPath value in Identity Manager's configuration is the same as in the OAuth provider registration screen for Identity Manager.

### Configuration

First, the OAuth method must be enabled under the authentication > OAuth section.

| Name | Type | Description |
| --- | --- | --- |
| Enabled required | Boolean | Enables or disables the OAuth connection. |

Then, users must create a new section per OAuth provider. Users are free to choose any section name. Its sole purpose is for users to find the authentication method in the configuration files.

Each section is configured with the following settings:

| Name | Type | Description |
| --- | --- | --- |
| AuthenticationScheme required | String | Is the unique identifier of this authentication method within Identity Manager. Any string value can be used, unique among all authentication methods. |
| DisplayName optional | String | Is the provider display name. Chosen by the user, it is used in the UI to identify the authentication method. |
| ClientId required | String | Is the Client ID issued to Identity Manager during the registration process. |
| ClientSecret required | String | Is the Client Secret issued to Identity Manager during the registration process. |
| ClaimsIssuer required | String | Is a unique identifier that will mark claims issued by this OAuth provider for Identity Manager. This mark is used for debugging, monitoring, or security purposes in situations where multiple OAuth providers are involved. It's still useful if only one provider is used. Any string value can be used. Convention dictates that it is a URL shaped value such as https://accounts.google.com. |
| AuthorizationEndpoint required | String | Is the provider's Authorization Endpoint URI. This is where the end-user's browser is redirected to start the authentication process. Usually ends with /auth or /authorize. This information must be retrieved from the provider's portal. |
| TokenEndpoint required | String | Is the provider's Token Endpoint URI. This is where the client sends token requests, using an authorization code obtained during the authentication process. This information must be retrieved from the provider's portal. |
| CallbackPath required | String | Sets the callback path where the client is redirected after a successful authentication. Any string value can be used as long as it is reported to the provider during the registration process. |
| SaveTokens default value: false | Boolean | Only for Okta providers. Set to `true if authentication uses an Okta provider. See the [Configure Okta](../../how-tos/okta/index "Configure Okta for Usercube Authentication")topic for additional information. |
| Scope optional | String | Sets the list of the requested [scopes](https://auth0.com/docs/scopes/openid-connect-scopes). |

Example

The following example configures an OAuth-based authentication provider identified as OAuthContoso\_Washington in the configuration file.

It will be displayed as Contoso OAuth Washington in the UI external login prompt, and uniquely identified within Identity Manager by the authentication scheme contoso\_0987.

Identity Manager Server marks received claims using  as a claim issuer identifier.

/signin-oauth has been chosen as CallbackPath and set up as such in the OAuth provider's portal during Identity Manager's registration.

Code attributes enclosed with  need to be replaced with a custom value before entering the script in the command line.

```
{  
    "Authentication":  
    {  
        ...  
        "OAuth": {  
            "Enabled": "",  
            "OAuthContoso_Washington": {  
                "AuthenticationScheme": "",  
                "DisplayName": "",  
                "ClientId": "",  
                "ClientSecret": "",  
                "ClaimsIssuer": "",  
                "AuthorizationEndpoint": "",  
                "TokenEndpoint": "",  
                "CallbackPath": "",  
                "Scopes": ["", ""]  
            }  
        }  
    }  
}  

```
## Set Up a WS-Federation Provider

One or several WS-Federation authentication providers can be set up under the authentication > WsFederation subsection. Examples of WS-Federation providers include Active Directory Federation Services (ADFS) and Microsoft Entra ID (AAD).

Multiple providers

One or several WS-Federation authentication providers can be set up.

Registration process

Using a WS-Federation authentication requires Identity ManagerServer to be registered to the provider. A Wtrealm value is set up during the registration process. The value can be generated by the provider, or set manually as a URL-shaped string value. This allows Identity Manager to identify itself to the authentication provider. Here are two examples of registration process:

* with an [Active Directory Federation Services](https://docs.microsoft.com/en-us/aspnet/core/security/authentication/ws-federation?view=aspnetcore-5.0#active-directory-federation-services) provider
* with an [Microsoft Entra ID](https://docs.microsoft.com/en-us/aspnet/core/security/authentication/ws-federation?view=aspnetcore-5.0#azure-active-directory) provider

Callback URL

The target WS-Federation provider needs to be aware of the URI where to send the authentication token if the authentication succeeds. Depending on the provider, it is called a callback URL, a callback path, an authorization callback URL, or a redirect URI.

During the registration process, the provider will ask for the URL.

Identity Manager's callback URL for WS-Federation is /signin-wsfed where  is the address of your Identity Manager Server such as https://usercube.contoso.com.

Encryption algorithm

The nature of the encryption algorithm used for exchanging the sign-in key with the provider is automatically negotiated between Identity Manager Server and the authentication server. The most secure algorithm that both systems support is chosen.

### Configuration

First, the WS-Federation must be enabled under the authentication > WsFederation section:

| Name | Type | Description |
| --- | --- | --- |
| Enabled required | Boolean | Enables or disables the **WS-Federation** authentication. |

Then, users must create a new subsection per **WS-Federation** provider. They are free to choose any section name. Its sole purpose is for users to find the authentication method in the configuration files.

Each section is configured with the following settings:

| Name | Description |
| --- | --- |
| MetadataAddress required | Identifies, for Identity Manager, the target **WS-Federation** server's metadata. This information is to be retrieved from the app registration process or directly from the **WS-Federation** provider. The value commonly ends with the path `/`FederationMetadata/2007-06/FederationMetadata.xml.   * For [Active Directory Federation Services](https://docs.microsoft.com/en-us/aspnet/core/security/authentication/ws-federation?view=aspnetcore-5.0#active-directory-federation-services), it is https:///federationmetadata/2007-06/federationmetadata.xml with  the name of your ADFS server such portal.contoso.com. * For [Microsoft Entra ID](https://docs.microsoft.com/en-us/aspnet/core/security/authentication/ws-federation?view=aspnetcore-5.0#azure-active-directory), it is also known as **Federation Metadata Document**. It is available in Identity Manager's registered app *blade*, in the *endpoint* panel, *Federation Metadata Document* value. It looks like https://bbd35166-7c13-49f3-8041-9551f2847b69/FederationMetadata/2007-06/FederationMetadata.xml with bbd35166-7c13-49f3-8041-9551f2847b69 Microsoft Entra ID tenant id. |
| Wtrealm required | Identifies the Identity Manager app within the **WS-Federation** provider. This information is available directly at the authentication provider's portal. It is chosen during the registration process.   * For [Active Directory Federation Services](https://docs.microsoft.com/en-us/aspnet/core/security/authentication/ws-federation?view=aspnetcore-5.0#active-directory-federation-services), it is the value set as the relying party WS-Federation Passive protocol URL parameter during the [registration](https://docs.microsoft.com/en-us/aspnet/core/security/authentication/ws-federation?view=aspnetcore-5.0#active-directory-federation-services) of Identity Manager to the ADFS server. It usually looks like an URL such as https://portal.contoso.com. * For [Microsoft Entra ID](https://docs.microsoft.com/en-us/aspnet/core/security/authentication/ws-federation?view=aspnetcore-5.0#azure-active-directory), this is the Application ID URI. It is available from Identity Manager's registered app blade > Expose an API > APP ID URI. It has been either chosen by the user or generated by the [Microsoft Entra ID](https://docs.microsoft.com/en-us/aspnet/core/security/authentication/ws-federation?view=aspnetcore-5.0#azure-active-directory) provider during the Expose an API > set > save step of the registration. Generated values look like api://bbd35166-7c13-49f3-8041-9551f2847b69. |
| DisplayName optional | Is the provider display name. Chosen by the user, it is used in the UI to identify the authentication method. |
| AuthenticationScheme required | Is the unique identifier of this authentication method within Identity Manager. Any string value can be used, unique among all authentication methods. |

Example

This example configures a WS-Federation-based authentication provider identified as WsFederationContoso\_LA in the configuration file.

Within Identity Manager, it will be identified with the authentication scheme WsFederationAAD.

It will be displayed as *Connection Microsoft Entra ID with WS-Federation protocol* in the UI external login prompt.

Code attributes enclosed with  need to be replaced with a custom value before entering the script in the command line.

```
{  
    "Authentication":  
    {  
        ...  
        "WsFederation": {  
            "Enabled": "",  
            "WsFederationContoso_LA": {  
                "AuthenticationScheme": "",  
                "DisplayName": "",  
                "MetadataAddress": "",  
                "Wtrealm": ""  
            }  
        }  
    }  
}
```
## Set Up SAML2 Authentication

One or several **SAML2** authentication providers can be set up under the authentication > SAML2 section.

Identity Manager does not provide a signature for SAML2 authentication.

Multiple providers

One or several **SAML2** authentication providers can be set up.

Registration process

Using a **SAML2** authentication requires Identity Manager Server to be registered to the provider. An **Entity ID URI** value is set up for Identity Manager during the registration process. It is used as the prefix for scopes and as the value of the audience claim in access tokens. The value can be generated by the provider, or set manually as a URL-shaped string value. This allows Identity Manager to identify itself to the authentication provider.

Reply URL

The target **SAML2** provider needs to be aware of the URI where to send the authentication token if the authentication succeeds. This URI is called **Reply URL** or **Assertion Consumer Service (ACS) URL**.

During the registration process, the provider will ask for the URL.

Identity Manager's **Reply URL** for **SAML2** is /Saml2/Acs where  is the address of your Identity Manager Server such as https://usercube.contoso.com.

:::warning
Make sure to enter this exact URL which is treated case sensitively.
:::

Configuration

First, the SAML2 method must be enabled under the authentication > SAML2 section.

| Name | Type | Description |
| --- | --- | --- |
| Enabled required | Boolean | Enables or disables SAML2 Authentication. |

Then, users must create a new subsection per SAML2 provider. Users are free to choose any section name. Its sole purpose is for users to find the authentication method in the configuration files.

Each section is configured with the following settings:

| Name | Description |
| --- | --- |
| MetaDataLocation required | Identifies, for Identity Manager, the target SAML2 server's metadata. This information is to be retrieved from the app registration process or directly from the SAML2 provider. The value commonly ends with the path /FederationMetadata/2007-06/FederationMetadata.xml. |
| IdentityProviderEntityID required | Is the Identity Provider Issuer (also known as provider Entity ID) that identifies the provider to Identity Manager. This information is to be retrieved from the provider's portal. For Microsoft Entra ID, it is the first line of metadata file. |
| DisplayName optional | Is the provider display name. Chosen by the user, it is used in the UI to identify the authentication method. |
| EntityIdAppliUriID required | Is Identity Manager's Entity ID issued during the registration process. Also referred to as an Identifier URI. For Microsoft Entra ID, it is set during the Expose an API > set > save step of the registration. Generated values look like api://bbd35166-7c13-49f3-8041-9551f2847b69. |
| NameIdFormat optional | Is the requested format of the subject's name identifier. |
| MinIncomingSigningAlgorithm optional | Is minimal signing algorithm to validate SAML2 response. |
| EncryptionCertificate optional | Sets the location of the public key certificate and the private key used to handle input and output files encryption.  **NOTE:** This is required to enable logout. |

> This example configures a SAML2-based authentication provider identified as SAMLConnection in the configuration file.
>
> It will be displayed as Connection Azure ActiveDirectory with SAML2 protocol in the UI external login prompt.
>
> Code attributes enclosed with  need to be replaced with a custom value before entering the script in the command line.
>
> ```
> {  
>     "Authentication":  
>     {  
>         ...  
>         "SAML2": {  
>             "Enabled": true,  
>             "SAMLConnection": {  
>                 "DisplayName": "",   
>                 "EntityIdAppliUriID": "",   
>                 "MetaDataLocation": "",   
>                 "": "",  
>                 "EncryptionCertificate": {  
>                 ...  
>                 }  
>             }  
>         }  
>     }  
> }
> ```
### Encryption Certificate

This information can be set one of two ways:

* As a [Public Key Cryptography Standards (PKCS) #12](https://en.wikipedia.org/wiki/PKCS_12) archive (also called [Personal](https://docs.microsoft.com/en-us/windows-hardware/drivers/install/personal-information-exchange---pfx--files) Information Exchange file or `.pfx` file) stored in the Agent's host file system. The archive contains both the public key certificate and the private key.
* As a certificate from a Windows' [certificate store](https://docs.microsoft.com/en-us/dotnet/framework/wcf/feature-details/working-with-certificates#certificate-stores) identified by SubjectDistinguishedName or by Thumbprint. The Windows certificate also contains both the public key certificate and the private key.

*Remember,* Netwrix recommends using Windows' certificate store.
  
On the other hand, the PFX file takes priority over Windows' certificate, which means that when `File` is specified then the PFX certificate is used, even if the options for Windows' certificate are specified too.
  
In both ways, missing and/or incorrect settings trigger an error and no certificate is loaded.

*Remember,* the AzureKeyVault section is mandatory when using CertificateAzureKeyVault. Identity Manager server loads the encryption certificate from Azure Key Vault only if the AzureKeyVault and EncryptionCertificate are defined at the same level in the configuration file.

#### As a PFX file

For example:

Code attributes enclosed with  need to be replaced with a custom value before entering the script in the command line.

```
{  
    ...  
    "EncryptionCertificate": {  
        "File": "",  
        "Password": ""  
     }  
 }
```
The archive is set using the following attributes:

| Name | Type | Description |
| --- | --- | --- |
| File required | String | [PKCS #12](https://en.wikipedia.org/wiki/PKCS_12) archive path on the host file system. |
| Password optional | String | [PKCS #12](https://en.wikipedia.org/wiki/PKCS_12) archive password. |

Storing a `.pfx` file password in plain text in a production environment is strongly discouraged. It should always be encrypted using the Identity Manager-Protect-CertificatePassword tool. See the [Usercube-Protect-CertificatePassword](../../../executables/references/protect-certificatepassword/index "Usercube Protect Certificate Password") topic for additional information.

The archive is set using the following attributes:

| Name | Type | Description |
| --- | --- | --- |
| File required | String | [PKCS #12](https://en.wikipedia.org/wiki/PKCS_12) archive path on the host file system. |
| Password optional | String | [PKCS #12](https://en.wikipedia.org/wiki/PKCS_12) archive password. Storing a `.pfx` file's password in plain text in a production environment is strongly discouraged. It should always be encrypted using the Usercube-Protect-CertificatePassword.exetool. |

#### As a Certificate in the Windows Store

For example:

Code attributes enclosed with  need to be replaced with a custom value before entering the script in the command line.

```
{  
    ...  
    "EncryptionCertificate": {  
         "DistinguishedName":"",  
         "StoreLocation": "",  
         "StoreName": ""  
     }  
 }
```
The Windows certificate is set using these attributes:

| Name | Type | Description |
| --- | --- | --- |
| DistinguishedName (optional) | String | SubjectDistinguishedName of the store certificate.  **NOTE:** This is required when Thumbprint is not specified. |
| Thumbprint (optional) | String | Thumbprint of the store certificate.  **NOTE:** This is required when DistinguishedName is not specified. |
| StoreLocation (required) | String | Location of the relevant Windows certificate store: LocalMachine or CurrentUser. |
| StoreName (required) | String | Name of the relevant Windows certificate store. |

##### Using Azure Key Vault

If the certificate is saved in Azure Key Vault, we must define the certificate identifier and the Vault connection. See the [Azure Key Vault](../../agent-configuration/azure-key-vault/index "Azure Key Vault") topic for additional information.

*Remember,* the AzureKeyVault section is mandatory when using CertificateAzureKeyVault. Identity Manager server loads the encryption certificate from Azure Key Vault only if the AzureKeyVault and EncryptionCertificate are defined at the same level in the configuration file.

Code attributes enclosed with  need to be replaced with a custom value before entering the script in the command line.

```
{  
    "Authentication": {  
        ...  
        "SAML2": {  
            "Enabled": true,  
            "": {  
                ...  
                "AzureKeyVault": {  
                    "Vault": "",  
                    "ConnectionString": "..."  
                },  
                "EncryptionCertificate": {  
                    "CertificateAzureKeyVault": ""  
                }  
            }  
        }  
    }  
}
```
## Set Up Internal Methods

When Internal Methods is enabled, the end-user is prompted via a form to input a login and a password. The login to be used is defined within the applicative configuration's Select User By Identity Query Handler Setting element. See the [Various XML Settings](../../settings/index "Various XML Settings") topic for additional information.

First, the AllowLocalLogin parameter needs to be set to true in the Authentication section.

Code attributes enclosed with  need to be replaced with a custom value before entering the script in the command line.

```
"":{  
    "AllowLocalLogin":true  
}
```
Then, Active Directory User Store or Test User Store can be enabled.

### Active Directory User Store

The Active Directory User Store allows users to authenticate with a login and password that will be compared against the Active Directory content.

Several forests can be set up as identity providers for authentication. This allows, for example, the authentication of users that belong to different Active Directory forests.

It is configured under the Authentication > ActiveDirectoryUserStore section.

First, the ActiveDirectoryUserStore must be enabled.

Code attributes enclosed with  need to be replaced with a custom value before entering the script in the command line.

```
"":{  
    "AllowLocalLogin":true,  
    "ActiveDirectoryUserStore": {  
        "Enabled": true  
        ...  
    }  
}
```
| Name | Type | Description |
| --- | --- | --- |
| Enabled required | Boolean | True to enable authentication via the Active Directory User Store. |

In the same section, several authentication providers can be defined, each one based on an Active Directory forest.

For each forest, a new section is added under ActiveDirectoryUserStore. Any name may be chosen for the forest section as long as it is unique. Two forest sections can't be identical though.

Code attributes enclosed with  need to be replaced with a custom value before entering the script in the command line.

```
"": {  
    "Enabled": true,  
    "Forest1": {  
        "AuthenticationScheme": "",  
        "Server": "",  
        ...  
    }  
}
```
Under the new forest section, the following parameters are used to configure the authentication method.

> The following example sets a single authentication method, based on the Forest1 forest. The domain controller is located at 127.168.0.1. If the user enters the login MyLogin, the resulting logon will be CONTOSO\paris\MyLogin. The Postfix won't be used as a Prefix is already provided.
>
> Code attributes enclosed with  need to be replaced with a custom value before entering the script in the command line.
>
> ```
> "": {  
>   "Enabled": true,  
>   "Forest1": {  
>       "AuthenticationScheme": "",  
>       "Server": "",  
>       "Domain": "",  
>       "Prefix": "",  
>       "Postfix": ""  
>   }  
> }
> ```
>
> In the following example, if the user enters the login MyLogin, the resulting logon will be MyLogin@Identity Manager.contoso.
>
> Code attributes enclosed with  need to be replaced with a custom value before entering the script in the command line.
>
> ```
> "": {  
>   "Enabled": true,  
>   "Forest1": {  
>       "AuthenticationScheme": "",  
>       "Server": "",  
>       "Postfix": ""  
>   }  
> }
> ```
>
> The following example enables authentication via the Active Directory User Store, for the Forest1 forest,by checking not only the password and account activation, but also whether the password is expired.
>
> Code attributes enclosed with  need to be replaced with a custom value before entering the script in the command line.
>
> ```
> "": {  
>   "Enabled": true,  
>   "Forest1": {  
>       "AuthenticationScheme": "",  
>       "Server": "",  
>       "Domain": "",  
>       "FastBind": false  
>       ...  
>   }  
> }
> ```
| Name | Type | Description |
| --- | --- | --- |
| AuthenticationScheme required | String | Unique identifier of this authentication method within Identity Manager. Any string value can be used, unique among all authentication methods. |
| Server required | String | Identification of the domain controller that runs the Active Directory Domain Service against which the authentication is performed. Based on [Microsoft's documentation](https://docs.microsoft.com/en-us/dotnet/api/system.directoryservices.protocols.ldapconnection?view=dotnet-plat-ext-8.0), the format is defined either:   * by a domain name * by an LDAP server name * or a dotted string representing the IP address of the LDAP server/Domain Controller (example: 98.20.33.2). Optionally, this parameter may also include a port number, separated from the host by a colon (example: 98.20.33.2:4520). |
| Domain optional | String | Identification of the Active Directory domain or sub-domain against which the authentication will be performed. It is a string used to complete the user's logon in an INet name fashion. The resulting logon will resemble Domain\login. The domain is used only if no postfix was provided.  This parameter is ignored if the domain or the UPN suffix is already specified in the login. This is the case for a login that conforms to the format domain\login or login@domain.com. |
| FastBind default value: True | Boolean | True to check a user's credentials by verifying only the password and account activation. |
| NoSigning default value: true | Boolean | Enables or disables [Kerberos encryption](https://en.wikipedia.org/wiki/Kerberos_(protocol)). |
| Prefix optional | String | Is a string used to complete the user's logon in an INet name fashion. The resulting logon will resemble Prefix\login. The Postfix isn't used if the domain or the UPN suffix is already specified in the login. |
| Postfix optional | String | Is used to complete the user's login in a principal name fashion. The Postfix corresponds to the User Principal Name (UPN) suffix. The resulting logon will resemble login@Postfix. The Postfix isn't used if the domain or the UPN suffix is already specified in the login, or if the Prefix is already provided. |
| Ssl default value: false | Boolean | Enables or disables SSL for network communication between Identity Manager and the Active Directory. |

### Test User Store

A Test User Store can be set up under the authentication > TestUserStore section. It allows all users to authenticate with their login and the same password.

*Remember,* this should never be used in a production environment.

The following parameters are available under the authentication > TestUserStore section:

| Name | Type | Description |
| --- | --- | --- |
| Enabled required | Boolean | Enables or disables the OpenId Connection. |
| Password required | String | Is the password for all users to authenticate Identity Manager. |

Example

Code attributes enclosed with  need to be replaced with a custom value before entering the script in the command line.

```
{  
    "Authentication":  
    {  
      "AllowLocalLogin":true  
        ...  
        "": {  
            "Enabled": true,  
            "Password": ""  
        }  
    }  
}  
  
Here is an example using both `IdentityServer` and `Authentication` sections.  
  
appsettings.json  
{  
    ...  
    "IdentityServer": {  
        "X509KeyFilePath": "",  
        "X509KeyFilePassword": ""  
    },  
    "Authentication": {  
        "RequireHttpsMetadata": false,  
        "TestUserStore": {  
            "Enabled": "",  
            "Password": ""  
        },  
        "AllowLocalLogin": true  
    }  
    ...  
}
```
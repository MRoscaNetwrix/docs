# ServiceNowTicket

This connector opens tickets in [ServiceNow](https://www.servicenow.com/) for manual provisioning.

This page is about [Ticket/ServiceNow](/versioned_docs/usercube_6.1/usercube/integration-guide/connectors/references-packages/servicenow-ticket/index.md).

![Package: Ticket/ServiceNow](/img/versioned_docs/usercube_6.1/usercube/integration-guide/connectors/references-connectors/servicenowticket/packages_servicenowticket_v603.png)

## Overview

ServiceNow is a cloud-based company that provides software as a service (SaaS) for technical management support. The company specializes in IT service management (ITSM), IT operations management (ITOM) and IT business management (ITBM), allowing users to manage projects, teams and customer interactions via a variety of apps and plugins.  
This section focuses on ServiceNow ticket creation for the fulfillment of resources that can't or shouldn't be performed with an existing fulfill. To learn about how to manage entities, see [ServiceNow Entity Management](/versioned_docs/usercube_6.1/usercube/integration-guide/connectors/references-connectors/servicenowentitymanagement/index.md).

## Prerequisites

Implementing this connector requires:

- reading first the [appsettings documentation](/versioned_docs/usercube_6.1/usercube/integration-guide/network-configuration/agent-configuration/appsettings-agent/index.md);
- a service account with the __snc\_platform\_rest\_api\_access__ role, as well as reading and writing permissions on the target ServiceNow instance;
- the version ServiceNow London or later;
- the appropriate configuration in ServiceNow of authentication, Basic or OAuth.

## Export

This connector exports some of ServiceNow entities, [see the export capabilities of the ServiceNow connector](/versioned_docs/usercube_6.1/usercube/integration-guide/connectors/references-connectors/servicenowentitymanagement/index.md#see-the-export-capabilities-of-the-servicenow-connector). Some entities cannot be exported.

## Fulfill

This connector writes to ServiceNow to create incident and request tickets containing information to create, update or delete a resource. It does not create nor update a resource directly.

Once created, the ticket is managed in ServiceNow, not in Usercube.

When the ticket is closed or canceled, Usercube updates the [provisioning state](/versioned_docs/usercube_6.1/usercube/integration-guide/role-assignment/assignments-of-entitlements/index.md#provisioning-state) of the resource accordingly.

[See the fulfill capabilities of the ServiceNow connector](/versioned_docs/usercube_6.1/usercube/integration-guide/connectors/references-connectors/servicenowentitymanagement/index.md#see-the-fulfill-capabilities-of-the-servicenow-connector).

> For example:
>
> ```
> appsettings.agent.json
> {
>   ...
>   "Connections": {
>     ...
>     "ServiceNowFulfillManual": {
>         "Server": "https://instance.service-now.com/api/now/table",
>         "Login": "login",
>         "Password": "password"
>     }
>   }
> }
> ```

## Authentication

### Password reset

[See how to configure password reset settings](/versioned_docs/usercube_6.1/usercube/integration-guide/network-configuration/agent-configuration/appsettings-agent/index.md#see-how-to-configure-password-reset-settings).

When setting a password for a ServiceNow user, the password attribute is set to the chosen value and the user's __password\_needs\_reset__ attribute is set to ```true```.

### Credential protection

Data protection can be ensured through:

- [RSA encryption](/versioned_docs/usercube_6.1/usercube/integration-guide/network-configuration/agent-configuration/rsa-encryption/index.md), configured in the ```appsettings.encrypted.agent.json``` file;
- an [Azure Key Vault](/versioned_docs/usercube_6.1/usercube/integration-guide/network-configuration/agent-configuration/azure-key-vault/index.md) safe;

| Attribute | Naming Convention for the Key in Azure Key Vault |
| --- | --- |
| Server | ```Connections--<identifier>--Server``` |
| Login | ```Connections--<identifier>--Login``` |
| Password | ```Connections--<identifier>--Password``` |
| ClientId | ```Connections--<identifier>--ClientId``` |
| ClientSecret | ```Connections--<identifier>--ClientSecret``` |
| OAuth2Url | ```Connections--<identifier>--OAuth2Url``` |
| TicketCookieDirectoryPath | ```Connections--<identifier>--TicketCookieDirectoryPath``` |
| ResponseSizeLimit | ```Connections--<identifier>--ResponseSizeLimit``` |

- a [CyberArk Vault](/versioned_docs/usercube_6.1/usercube/integration-guide/network-configuration/agent-configuration/cyberark-application-access-manager-credential-providers/index.md) able to store Active Directory's ```Login```, ```Password```, ```Server```, ```ClientId``` and ```ClientSecret```.

Protected attributes are stored inside a safe in CyberArk, into an account whose identifier can be retrieved by Usercube from ```appsettings.cyberark.agent.json```.

> For example:
>
> ```
> appsettings.cyberark.agent.json
> {
>   ...
>   "Connections": {
>     ...
>     "ServiceNowFulfillManual": {
>         "Login": "ServiceNowFulfillManual_CyberArkKey",
>         "Password": "ServiceNowFulfillManual_CyberArkKey",
>         "Server": "ServiceNowFulfillManual_CyberArkKey",
>         "ClientId": "ServiceNowFulfillManual_CyberArkKey",
>         "ClientSecret": "ServiceNowFulfillManual_CyberArkKey"
>     }
>   }
> }
> ```

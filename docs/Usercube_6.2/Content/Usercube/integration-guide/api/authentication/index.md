---
sidebar_position: 1006
title: Authentication
---

# Authentication

Identity Manager API authentication is based on the [OpenIdConnect protocol](https://openid.net/connect/ "OpenIdConnect protocol"). Configuration informations are accessible on: `[Usercube application URL]/.well-known/openid-configuration`.

An OpenId client must be previously defined using an [OpenIdClient](../../toolkit/xml-configuration/access-control/openidclient/index "OpenIdClient") configuration element.

The `client_id` parameter to use in calls to the OpenIdConnect protocol endpoints must be the concatenation of `clientId`, `@` and the domain of the application.

For example, client defined by

```


```
for the Identity Manager application hosted on `usercube.mycompany.com` must use `MyApplication@usercube.mycompany.com` as `client_id` parameter in any call to the OpenIdConnect endpoints.

The scope to access to the Identity Manager API is `usercube_api`.
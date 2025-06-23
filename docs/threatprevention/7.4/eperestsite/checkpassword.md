# Check Password APIs

You can use APIs to check a candidate password against the EPE rules defined on the
[EPE Settings Window](/docs/threatprevention/7.4/admin/configuration/epesettings.md).

- POST api/Epe/CheckPassword (Basic)
- POST api/Epe/CheckPassword (Digest)
- POST api/Epe/CheckPassword (Bearer)

Create a JSON file with a request. This file should contain the account name and the password you
want to test.

**NOTE:** The EPE Rest service only checks the password; it does not change it.

## POST api/Epe/CheckPassword (Basic)

This API verifies the password value.

Authentication required – Yes

Authentication Type – Basic

Input Parameters

```
{
"username":"domain\\account",
"password":"password",
"server":"DC_DNS_Name"
}
```

The “username” and “password” parameters are required. The “server” parameter is optional.

Example

![POST api/Epe/CheckPassword (Basic)](/img/versioned_docs/threatprevention_7.4/threatprevention/eperestsite/basic.webp)

## POST api/Epe/CheckPassword (Digest)

This API verifies the password value.

Authentication required – Yes

Authentication Type – Digest

Input Parameters

```
{
"username":"domain\\account",
"password":"password",
"server":"DC_DNS_Name"
}
```

The “username” and “password” parameters are required. The “server” parameter is optional.

Required Header Input Parameters

```
"User”: <username>
"Authorization”:”Hash”
"Hash": <hashvalue>
```

Example

![POST api/Epe/CheckPassword (Digest)](/img/versioned_docs/threatprevention_7.4/threatprevention/eperestsite/digest.webp)

## POST api/Epe/CheckPassword (Bearer)

This API verifies the password value.

Authentication required – Yes

Authentication Type – Bearer

Input Parameters

```
{
"username":"domain\\account",
"password":"password",
"server":"DC_DNS_Name"
}
```

The “username” and “password” parameters are required. The “server” parameter is optional.

Required Header Input Parameters

```
"User”: <username>
"Authorization”:”Bearer <access_token>”
```

Example

![POST api/Epe/CheckPassword (Bearer)](/img/versioned_docs/threatprevention_7.4/threatprevention/eperestsite/bearer.webp)

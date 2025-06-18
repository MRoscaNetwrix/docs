# Server

This section identifies hardware and software requirements for Usercube's server.

## License Key

The server requires a
[license key](/docs/identitymanager/6.1/identitymanager/integration-guide/network-configuration/server-configuration/general-purpose/index.md)
provided by NETWRIX.

## Software

The server is a .NET application.

Running the server requires installing the
[ASP.Net hosting bundle in version 8.0](https://dotnet.microsoft.com/en-us/download/dotnet/8.0).

## Hosting

The server can be run as:

- an [Internet Information Services (IIS)](https://www.iis.net/) website from the minimal version
  IIS 10.0 (recommended);
- a
  [Windows service](https://docs.microsoft.com/en-us/dotnet/framework/windows-services/introduction-to-windows-service-applications);
- a stand-alone executable for tests or debugging purposes.

It is recommended to enable the following
[Internet Information Services (IIS)](https://www.iis.net/) features to host Usercube:

- [Windows Authentication](https://docs.microsoft.com/en-us/iis/configuration/system.webserver/security/authentication/windowsauthentication/#windows-authentication);
- [Anonymous Authentication](https://docs.microsoft.com/en-us/iis/configuration/system.webserver/security/authentication/anonymousauthentication#anonymous-authentication).

## Service Accounts

The installation of the server as part of an Active Directory domain requires the use of an account
with sufficient privileges to create a service account on the domain.

The server should be assigned a
[custom Windows service account](https://docs.microsoft.com/en-us/windows/security/identity-protection/access-control/service-accounts).

The IIS built-in
[application pool identity](https://support.microsoft.com/en-us/help/4466942/understanding-identities-in-iis)
should not be used, because it will prevent the custom account from connecting to a distant SQL
Server. Hence NETWRIX recommends using a domain account.

### Working directory permissions

The agent's service account needs specific permissions on the
[working directory](/docs/identitymanager/6.1/identitymanager/installation-guide/production-ready/working-directory/index.md):

- _Read_ and _List folder contents_ on the working directory;
- _Read & Execute_ and _List folder contents_ on the
  [`Runtime` directory](/docs/identitymanager/6.1/identitymanager/installation-guide/production-ready/working-directory/index.md),
  usually `C:/identitymanager<Organization>/Runtime`, in order to run the agent executable;
- _Read_ and _List folder contents_ on the directory for provisioning orders, whose path depends on
  the
  [`Work` folder's path](/docs/identitymanager/6.1/identitymanager/integration-guide/network-configuration/agent-configuration/appsettings/index.md);
- _Read_, _List folder contents_, and _Write_ on the directory for data collection, whose path
  depends on the
  [`Work` folder's path](/docs/identitymanager/6.1/identitymanager/integration-guide/network-configuration/agent-configuration/appsettings/index.md).

Other permissions should be denied.

> **FAQ**:
> [How to set up directory permissions in Windows Server?](/docs/identitymanager/6.1/identitymanager/installation-guide/production-ready/server/index.md)

### Database permissions

If Windows' authentication is used for SQL Server, then the server should be able to authenticate to
SQL Server with its assigned service account. It means that the server's service account needs to be
assigned an SQL Server login with the relevant
[roles](/docs/identitymanager/6.1/identitymanager/installation-guide/requirements/database-requirements/index.md),
including necessarily either `sysadmin` or `securityadmin`.

For more information, see the
[server installation procedure](/docs/identitymanager/6.1/identitymanager/installation-guide/production-ready/server/index.md).

## Hostname and DNS

In the case of an on-premises installation, the server needs to be assigned a hostname within the
organization's domain. Agents must be able to resolve the server's hostname.

The associated DNS zone needs to be
[updated accordingly](https://docs.microsoft.com/en-us/windows-server/networking/core-network-guide/cncg/server-certs/create-an-alias-cname-record-in-dns-for-web1).

The DNS alias should be written in lowercase in order to comply with as many security rules as
possible.

## SSL Certificate

The server requires the use of an SSL certificate in order to perform HTTPS communication with
end-users' browsers.

Usercube SaaS offering comes with an SSL certificate signed by a trusted certificate authority for
the `*.usercube.com` domains. This certificate allows end-users to access the server through the
Internet without any further configuration. Using another domain name for the SaaS installation
requires providing NETWRIX with the corresponding SSL certificate signed by a trusted certificate
Authority.

Usercube on-premises offering requires the use of an SSL certificate trusted by all the target
end-users' browsers. Standard practices use a certificate signed by the target organization's Public
Key Infrastructure (PKI) root certificate authority.
[The on-premise SSL certificate must be set up in IIS](/docs/identitymanager/6.1/identitymanager/installation-guide/production-ready/server/index.md).

## Emails

The server needs access to an SMTP server to send
[email notifications](/docs/identitymanager/6.1/identitymanager/installation-guide/production-ready/email-server/index.md).

## Encryption and Identity Server Key Pairs

An [RSA-2048 encryption key pair](https://en.wikipedia.org/wiki/Public-key_cryptography) is required
for:

- Usercube's server in order to perform various encryption operations, such as source,
  configuration, or log file encryptions;
- Usercube's Identity Server for end-user authentication purposes.

Such a certificate does not need to be integrated into the target organization's Public Key
Infrastructure and does not require an expiration date. They are only relevant to internal and
temporary Usercube data and can be changed at any time.

An RSA key pair, as in an [X.509](https://fr.wikipedia.org/wiki/X.509) public key certificate and a
private key, can be stored either:

- As a [PKCS #12](https://en.wikipedia.org/wiki/PKCS_12) archive (also called
  [Personal Information Exchange file](https://docs.microsoft.com/en-us/windows-hardware/drivers/install/personal-information-exchange---pfx--files)
  or `.pfx` file) stored in the _server_'s host file system. The archive contains both the public
  key certificate and the private key.
- As a certificate from a Windows'
  [certificate store](https://docs.microsoft.com/en-us/dotnet/framework/wcf/feature-details/working-with-certificates#certificate-store)
  identified by _SubjectDistinguishedName_ or by _Thumbprint_. The Windows certificate also contains
  both the public key certificate and the private key. This is the recommended method.

The key pair can be generated with tools such as
[OpenSSL](https://www.openssl.org/docs/manmaster/man1/req.html) or Microsoft's
[New-SelfSignedCertificate](https://docs.microsoft.com/en-us/powershell/module/pkiclient/new-selfsignedcertificate?view=win10-ps)and[pvk2pfx tool](https://docs.microsoft.com/en-us/windows-hardware/drivers/devtest/pvk2pfx?redirectedfrom=MSDN).

## What's Next?

Let's move on to
[Usercube's agent requirements](/docs/identitymanager/6.1/identitymanager/installation-guide/requirements/agent-requirements/index.md).

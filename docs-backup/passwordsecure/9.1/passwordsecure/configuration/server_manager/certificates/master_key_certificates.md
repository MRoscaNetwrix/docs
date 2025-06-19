# Master Key certificates

#### What is a Master Key certificate?

If Active Directory is accessed via
[Masterkey mode](/docs/passwordsecure/9.1/passwordsecure/configuration/advanced_view/clientmodule/organisationalstructures/directoryservices/activedirectorylink/masterkey_mode.md),
a certificate will be created. This has the name

Active Directory: Domain:

![installation_with_parameters_208](/img/versioned_docs/passwordsecure_9.1/passwordsecure/configuration/server_manager/certificates/installation_with_parameters_208.webp)

NOTE: The Master Key certificate cannot be replaced by your own certificate.

NOTE: The certificates for Master Key mode have an expiry date. However, this is not checked. The
certificate thus does not need to be renewed.

**CAUTION:** If the database is being moved to another server, it is essential that the Master Key
certificate is also transferred!

#### Exporting and importing the certificate

The section certificates explains how to back up the certificate and link it again.

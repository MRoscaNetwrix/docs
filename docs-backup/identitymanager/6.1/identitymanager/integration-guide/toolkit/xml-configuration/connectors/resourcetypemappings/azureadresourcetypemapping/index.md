# AzureADResourceTypeMapping

Any resource type mapping must be configured with the same identifier as the related resource type.

## Examples

```

<AzureADResourceTypeMapping Identifier="MicrosoftEntraID_DirectoryObject_Guest" Connection="MicrosoftEntraIDExportFulfillment" DefaultObjectClass="users" InvitationMode="MicrosoftInvitation" InvitationRedirectUrl="https://demo.usercube.com" PasswordResetSetting="ToSponsor">  <Property Property="objectid" IsDNProperty="true" />  <Property Property="groups" DataSourceBacklinkColumnName="member" />  <Property Property="displayName" IsDisplayNameProperty="true" />  <Property Property="mail" IsMailProperty="true" /></AzureADResourceTypeMapping>

```

## Properties

| Property                                 | Details                                                                                                                                                                                                                                                                                                                                                                                  |
| ---------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Connection required                      | **Type** String **Description** Identifier of the corresponding connection.                                                                                                                                                                                                                                                                                                              |
| DefaultObjectClass required              | **Type** String **Description** Default object class used by the provisioner, for example `person`, `organizationalPerson`, `user`, etc. **Note:** multiple default object classes are separated with `&#xA;`.                                                                                                                                                                           |
| InvitationCustomizedMessageBody optional | **Type** String **Description** Message that will replace Azure's default message in the invitation. **Note:** only used when `InvitationMode` is set to `MicrosoftInvitation`.                                                                                                                                                                                                          |
| InvitationMessageLanguage optional       | **Type** String **Description** Language of the invitation's message. **Note:** when not specified, the message is in English. **Note:** only used when `InvitationMode` is set to `MicrosoftInvitation`.                                                                                                                                                                                |
| InvitationMode default value: None       | **Type** InvitationMode **Description** Mode of the invitation email sent during the creation of a guest Microsoft Entra ID account. - **None**: nothing is sent. - **MicrosoftInvitation**: an invitation email is sent to another person to initiate the external user's guest account in Microsoft Entra ID according to the related password reset setting (one-way, two-way, etc.). |
| InvitationRedirectUrl optional           | **Type** String **Description** URL that will be displayed in the invitation email. **Note:** required when `InvitationMode` is set to `MicrosoftInvitation`.                                                                                                                                                                                                                            |
| PasswordResetSetting optional            | **Type** String **Description** Identifier of the corresponding password reset setting. **Note:** required when `InvitationMode` is set to `None` and `DefaultObjectClass` set to `users`.                                                                                                                                                                                               |

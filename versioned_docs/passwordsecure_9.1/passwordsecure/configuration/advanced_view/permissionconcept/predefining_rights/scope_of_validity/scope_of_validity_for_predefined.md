# Scope of validity for predefined rights

In general, all of the predefined rights for an organisational structure are applied to all underlying objects. These objects could be passwords, forms, form fields documents, users, applications or also other nested organisational structures in the hierarchy. In the following example, the rights template __IT general__ has been defined for the organisational unit __IT__.

![rights template](/img/versioned_docs/passwordsecure_9.1/passwordsecure/configuration/advanced_view/permissionconcept/predefining_rights/scope_of_validity/scope_of_validity_1-en.png)

If this type of “preset” has been defined, the corresponding icon is displayed at the corresponding level (= green arrow). As no other icons exist below this level, this means that the preset is valid for all underlying objects.

The following example shows how a preset can be defined for when the “password” form is used that not only grants the existing permissions to the roles but also provides the sales manager with read rights.

![working with rights template](/img/versioned_docs/passwordsecure_9.1/passwordsecure/configuration/advanced_view/permissionconcept/predefining_rights/scope_of_validity/scope_of_validity_2-en.png)

As can be seen, the preset “IT general” is valid for all objects. An exception here is the “password” form because a unique preset has been defined for this form (blue arrow). As a result, all records created using the “password” form receive permissions as defined in this preset (incl. the sales manager).

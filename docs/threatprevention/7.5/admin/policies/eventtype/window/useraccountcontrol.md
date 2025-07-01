# User Account Control Window

The User Account Control (UAC) window enables you to select specific UAC settings to be monitored by
the policy.

The User Account Control window is accessible if the userAccountControl attribute is included or
excluded in the policy through the AD Attributes filter.

![AD Attributes filter - serAccountControl attribute selected](/img/product_docs/threatprevention/7.5/admin/policies/eventtype/window/useraccountcontrolattribute.webp)

In the Include Attributes or Exclude Attributes boxes, click the Operation menu that displays **Any
Value** for the userAccountControl attribute to open the User Account Control Window window.

![User Account Control Window](/img/product_docs/threatprevention/7.5/admin/policies/eventtype/window/useraccountcotrol.webp)

This window displays a list of UAC flags for additional scoping. Select specific userAccountControl
flags using the **Attribute Set** and/or **Attribute Clear** checkboxes. When the selected attribute
is either added or removed in Active Directory, an event is created.

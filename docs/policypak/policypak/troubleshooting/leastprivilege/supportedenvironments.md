# Why doesn't Endpoint Privilege Manager work Windows 7 + SHA256 signed.JS and .VBS files ?

Windows 7 doesn't have the internal "plumbing" to see SHA256 signed.JS and .VBS files are signed.  
Here's an example of what you might see when just looking at a signed .JS file inside Windows 7.

Because of this, Endpoint Policy Manager [https://www.policypak.com/products/policypak-least-privilege-manager.html](https://www.policypak.com/products/policypak-least-privilege-manager.html) cannot use a SIGNATURE rule type when using .JS and .VBS files along with Windows 7.

Two other notes:

- This should work fine in Windows 10 though.
- SHA1 signed .JS and .VBS files should work in Windows 7.

![696_1_ghjklyhuouioui3333333](/img/product_docs/policypak/policypak/troubleshooting/leastprivilege/696_1_ghjklyhuouioui3333333.jpg)

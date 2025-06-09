# Why must I run LT from a Windows Server if I want to properly count Citrix / Terminal Services / RDS connections?

When you license Citrix / Terminal Services / RDS, you purchase keypak licenses in blocks of 50 from Microsoft and Citrix, and apply them to your servers.

Netwrix Endpoint Policy Manager (formerly PolicyPak) LT attempts to read these keypak files and report on your maximum inbound connections. In short, LT can only look for these Keypack licenses when running on a Windows server and not a Windows client machine. That is what this message is about.

![352_1_image001_(1)](/img/product_docs/352_1_image001_(1).png)

__NOTE:__ Sometimes LT can acquired the correct number of RDS connections, and sometimes it cannot.

![352_2_image002](/img/product_docs/policypak/policypak/license/virtualization/352_2_image002.jpg)

To be compliant with our EULA, if the count returned by LT shows zero, or otherwise fails to acquire the number of Citrix / Terminal Services / RDS licenses, you must manually declare them to your sales representative.

There are also multiple ways the Endpoint Policy Manager On-Prem suite can be licensed for Citrix. For understanding all the scenarios, please see the following additional technotes:

- [How are Terminal Services and/or Citrix connections licensed?](/docs/policypak/policypak/license/virtualization/terminalservices.md)
- [Citrix & WVD Multi-session Windows Licensing Scenarios](https://www.policypak.com/purchasing/vdi-licensing-scenarios/)

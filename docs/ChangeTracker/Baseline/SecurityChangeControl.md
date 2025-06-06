---
id: securitychangecontrol
title: Security and Change Control Using Baseline Policies
---

# Security and Change Control Using Baseline Policies

Several security frameworks reference the need for change control, integrity monitoring and an established configuration standard or hardened build standard. You will find the need for a Gold Build Standard in all compliance frameworks (for example, NIST 800-53 CM-2 and CM-3, CIS Control 5.2, PCI DSS Requirement 2 and especially NERC CIP 007-3 and 010-3) as a means of guaranteeing security. Without a consistent build how else can you expect security to be maximized?

The NERC CIP 010 process is shown in the diagram below and the Netwrix Baseline Configuration management process allows you to follow this cycle:

![](/img/changetracker/baseline/NERC_CIP_010_Lifecycle.png)

Every configuration item that is included within the Baseline Policy must be essential and justified, since every decision regarding configuration will potentially increase your attack surface.

Your Auditor will be looking for a fully documented Baseline Policy and the reasoning behind it.

Equally any time the Baseline is extended or updated, this must be with good reason and thereafter, all systems in scope of this Baseline must be shown to be within compliance.
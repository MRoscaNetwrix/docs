# Baseline Policy Rule Options: Rule Creation Options

![baselineeditrulecreationoptions](../../../../../static/img/product_docs/changetracker/changetracker/baseline/baselineeditrulecreationoptions.webp)

- **Extend Selected Rules** — Indicates whether to extend the rule to check for the old and new
  values, or replace the rule with one checking for the new value only
- **Missing Value Passes** — Indicates whether the rule passes if a missing item is detected (e.g.,
  installed software item is not present on target)
- **Add No Others Rule** — Indicates whether a rule is added to the sub-section which specifies that
  no other items of the type should be present on the target, other than ones already specified in
  other rules. For example, this allows the specification of a set of rules for software versions,
  and the additional requirement that no other installed software be present
- **Add Device Information Section** — Indicates whether a section is added at the start of the
  report to describe to details of the device the report is running on, including OS and IP address
  details. Note that this should only be used when a Per Device Baseline Policy is being operated –
  for a Group-wide Baseline Policy, disable this option.
- **Preview Changes** — Indicates whether a preview of the rule changes is presented for
  confirmation before they are applied.

From the CIS Controls 7.1: "For a complex enterprise, the establishment of a single security
baseline configuration (for example, a single installation image for all workstations across the
entire enterprise) is sometimes not practical or deemed unacceptable. It is likely that you will
need to support different standardized images, based on the proper hardening to address risks and
needed functionality of the intended deployment. For example, a web server in the demilitarized zone
(DMZ) versus an email or other application server in the internal network. The number of variations
should be kept to a minimum in order to better understand and manage the security properties of
each, but organizations then must be prepared to manage multiple baselines."

**NOTE:** Just click the Query icon to get a quick tip on what the Rule Option provides.

## Baseline Policy Rule Options: Review and Edit Rules

![baselinereviewandeditrules](../../../../../static/img/product_docs/changetracker/changetracker/baseline/baselinereviewandeditrules.webp)

Edit Rules provides a means to edit or remove rules before incorporating into your baseline policy,
or for managing an existing Policy. It is important to understand that during the Setup phase you
are selecting items with rule logic in order to build a Netwrix policy, in effect, another
Compliance Report like the hundreds of other reports Netwrix provide for CIS, NIST. PCI etc.

![baselineeditrules](../../../../../static/img/product_docs/changetracker/changetracker/baseline/baselineeditrules.webp)

The Edit Rules function provides an opportunity to add a description and justification for the
attribute and its inclusion in the policy.

The Description is prefilled with default explanatory text for open ports and services, but this can
be replaced or augmented with your own notes, important when deciding to include attributes in your
baseline as any addition inevitably increases your attack surface. A minimized configuration is
always the most secure.

Complete:

Baseline Policy creation is now complete, and you can run your first Baseline Policy report using
the Run Report button

![baselinerunreport](../../../../../static/img/product_docs/changetracker/changetracker/baseline/baselinerunreport.webp)

Running the report will take you to the regular Reports tab, filtered to your new Baseline Policy.
You can see more about scheduling and controlling reports in the main Reports section.

You can now either add more devices to the Baseline Members Group or just assign the Baseline Policy
to an existing group of devices, then choose your schedule and results delivery options.

![baselinereportsandqueryschedules](../../../../../static/img/product_docs/changetracker/changetracker/baseline/baselinereportsandqueryschedules.webp)

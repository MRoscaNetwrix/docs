---
sidebar_position: 3602
title: Internal Item-Level Targeting for the AppSet Itself
---

# Internal Item-Level Targeting for the AppSet Itself

**NOTE:**  To see an overview of Internal ItemLevel Targeting, including how to bypass the filters, see this video: [http://www.policypak.com/videos/bypassing-internal-item-level-targeting-filters.html](http://www.policypak.com/products/policypak-preconfigured-paks).

Many preconfigured AppSets that Endpoint Policy Manager Application Settings Manager makes available for free have built-in predefined, or internal, Item -Level Targeting filters.

For instance, an AppSet might be set to apply specifically to only Windows 7 or later. Or an AppSet might be set to apply specifically to a certain version of an application. For instance, Endpoint Policy Manager Application Settings Manager's Java 7 U 40 AppSet will only apply when Java 7 U 40 is present on the machine.

The preconfigured AppSets do this with internal Item-Level Targeting filters that are set within the AppSet. These internal filters are NOT configurable within the MMC. They are only configurable using the Endpoint Policy Manager DesignStudio at design time.

Figure 51 shows an example of how you might configure an internal filter.

![](../../../../../../../static/images/PolicyPak/Content/Resources/Images/ApplicationSettings/PolicyPak Application Settings_2_5.png)

Figure 51. Configuring an internal filter.

The purpose is to make sure that configuration items aren't delivered unless these predefined conditions match and are actually present on the target machine.

This keeps your target machines cleaner, because no Endpoint Policy Manager Application Settings Manager data is written unless it's actually needed.

However, you might find the need to bypass sets of internal filters and apply the AppSet anyway, regardless of whether the application is present on the machine. To do this, you need to modify the AppSet entry's options and change the "Predefined Item-Level Targeting" switch, as seen in Figure 52.

![](../../../../../../../static/images/PolicyPak/Content/Resources/Images/ApplicationSettings/PolicyPak Application Settings_2_6.png)

Figure 52.  Changing the Predefined Item-Level Targeting switch.

There are three ways to configure this entry, which are presented in Table 1 (also see Figure 53 for an example of one of the scenarios).

Table 1: Internal Item-Level Targeting settings options.

| Setting | Reason for Using This | Notes |
| --- | --- | --- |
| On (Installed Applications) | This is the default if you don't set it specifically.  When this is selected, Endpoint Policy Manager Application Settings Manager's internal Item-Level Targeting will apply ONLY to applications when they are actually installed on the machine. | Internal Item-Level Targeting is  automatically bypassed for virtualized applications.  This is recommended because Endpoint Policy Manager Application Settings Manager can only evaluate if something is true within the operating system itself and not within a virtualized application (e.g., Microsoft App-V 4 or App-V 5, ThinApp 4, ThinApp 5, Spoon.Net, Symantec Workspace Virtualization, or Citrix Streaming). |
| On (Installed and Virtual Applications) | This forces Endpoint Policy Manager Application Settings Manager to evaluate internal Item-Level Targeting, even when the application is virtualized.  You might want to set this setting if you would like to ensure that an internal filter for the operating system, IP range, or other system-specific setting is validated. | Typically, you wouldn't use this setting if you have internal filters that check for particular application-specific entries—such as Registry entries or file entries—since those cannot be evaluated inside the virtualized application.  Remember that Endpoint Policy Manager Application Settings Manager can only evaluate the "real" machine and not the conditions within the virtualized application itself. |
| Off | Set this to Off to bypass ANY internal filters.  This is a good troubleshooting step if you're not seeing settings being applied on your target machine. | When this is set to Off, no internal Item-Level Targets will "interfere" with the application of the settings. |

![](../../../../../../../static/images/PolicyPak/Content/Resources/Images/ApplicationSettings/PolicyPak Application Settings_2_7.png)

Figure 53. One scenario for item-level targeting on installed applications only.
# Endpoint Privilege Manager Implementation QuickStart Guide

Netwrix Endpoint Policy Manager (formerly PolicyPak) Least Privilege Manager can help you remove your local admin rights across your environment. And the tool has a lot to offer. In this Endpoint Policy Manager Least Privilege Manager Implementation Quickstart guide we will give you a basic action plan to get started, learn what applications and concerns you need to overcome, then generate rules to overcome those concerns.

You can use this guide if you’re planning to use Endpoint Policy Manager with On-Prem Active Directory and GPOs (Group Policy Objects), an MDM service like Intune or with Endpoint Policy Manager Cloud.

__NOTE:__ Some customers will be starting from a point where many/most end-users are still running with Local Admin Rights. But others customers have already removed Local Admin Rights and working to overcome that scenario. This guide will work for either customer type.

_Remember,_ as the phrase goes, “Rome wasn’t built in a day.” Your Endpoint Policy Manager Least Privilege Manager project is expected to take a little bit of time to gather details, and be implemented in a steady manner that everyone can live with, both end-users and the IT team.

## Installing Endpoint Policy Manager MMC and Endpoint Policy Manager CSE

Getting Endpoint Policy Manager up and going is done quickly.

The Endpoint Policy Manager Portal is where you download Endpoint Policy Manager Bits and keys used for when using Endpoint Policy Manager with On-Prem or MDM. You’ll even use the Endpoint Policy Manager Portal a little for Endpoint Policy Manager Cloud because you’ll need those downloads to make your perfect Endpoint Policy Manager Cloud test lab (explained later.) That URL is Portal.policypak.com.

__NOTE:__ Endpoint Policy Manager Cloud has its own URL, which is Cloud.policypak.com, and is considered the Endpoint Policy Manager Cloud Service. Please see the [Installation Quick Start](/docs/policypak/policypak/gettingstarted/quickstart/overviewinstall.md) for an overview of what is in the download, how to download, unpack, and get organized and quick licensed.

Here’s the Endpoint Policy Manager QuickStart Guide with specific steps and ideas for Endpoint Policy Manager with On-Prem Active Directory and GPOs, an MDM service like Intune or with Endpoint Policy Manager Cloud: [Netwrix Endpoint Policy Manager Quick Start](/docs/policypak/policypak/gettingstarted/quickstart/overview.md)

When done you will have the Endpoint Policy Manager MMC Console installed, your endpoints prepared and be ready to go.

![poc1](/img/product_docs/policypak/policypak/leastprivilege/poc1.png)

__NOTE:__ If you’re confused about which method you want to use to get Endpoint Policy Manager policies deployed (GPO, MDM or Cloud) this video can help you make an informed decision: [Endpoint Policy ManagerSolution Methods: Group Policy, MDM, UEM Tools, and Endpoint Policy Manager Cloud compared.](/docs/policypak/policypak/video/gettingstarted/solutionmethods.md)

## Licensing some trial machines (or many machines) for Endpoint Privilege Manager and other Endpoint Policy Manager Components

The Endpoint Policy Manager CSE on the endpoint only works when it is licensed. It is automatically licensed when a license from Endpoint Policy Manager Cloud is issued. However, if you are using Active Directory&GPOs or an MDM service like Intune, you will need to enable Endpoint Policy Manager licensing on those machines.

It’s easy to put one or a few machines into Trial mode with Endpoint Policy Manager without a license. For more information on this, please see these steps: [What is the fastest way to get started in an Endpoint Policy Manager trial, without running the License Request Tool?](/docs/policypak/policypak/license/trial.md)

If you need to request a license, please follow the steps outlined in this video: [How to Request Licenses fromPolicyPak by Creating a "License Request Key"](https://helpcenter.netwrix.com/bundle/PolicyPak/page/Content/PolicyPak/Video/License/LicenseRequestKey.html)

If you have a trial or full license for Endpoint Policy Manager and you wish to deploy it to all your computers, please follow these steps: [How to install UNIVERSAL licenses for NEW Customers (via GPO, SCCM or MDM)](/docs/policypak/policypak/video/license/installuniversal.md)

## (Optional, Recommended) Endpoint Policy Manager Cloud or Endpoint Policy Manager via MDM Test Lab Creation

Working within Endpoint Policy Manager Cloud itself, you can generally create nearly all the policy types you will need with the in-cloud editors. However, there will always be some policy-creation areas that are only accessible using the MMC.

As such we recommend that if you’re using Endpoint Policy Manager Cloud, that you create a small-scale on-prem test lab. This will accelerate your rule creation because you won’t need to create a rule and test in the cloud and then sync each time, which could be slower than creating them first in a small-scale on-prem test lab and then uploading those policies to Endpoint Policy Manager Cloud.

Additionally, since there is no way to create policies for Endpoint Policy Manager within an MDM service like Intune, having a small-scale on-prem test lab is required.

For a video review on how to get organized and create a small-scale on-prem test lab to use in conjunction with Endpoint Policy Manager Cloud or Endpoint Policy Manager alongside an MDM service like Intune, see: [Endpoint Policy Manager Cloud: What you need to get Started](/docs/policypak/policypak/video/cloud/testlab/start.md)

## (Optional, Recommended) Endpoint Policy Manager with an MDM service like Intune “Walk before you run.”

If you’re using Endpoint Policy Manager with an MDM service like Intune, you will also need some kind of management station and to pre-test your MDM license before you get going.

The best place to start for these instructions is here: [Video Learning Center](/docs/policypak/policypak/mdm/overview/videolearningcenter.md)

Additionally, get to know the details of how to create Endpoint Policy Manager Least Privilege Manager XMLs, export them, and wrap them up into MSIs for deployment with any MDM service with this video: [Using Least Privilege Manager with your MDM service](/docs/policypak/policypak/video/leastprivilege/mdm.md)

## Endpoint Privilege Manager “Base Hits” / “Walk Before You Run”

You’ll want to make sure Endpoint Policy Manager, and specifically Endpoint Policy ManagerLeast Privilege Manager is licensed, working, and accepting rules. To verify that Endpoint Policy Manager Least Privilege Manager is licensed and accepting rules, watch the video below and perform a Endpoint Policy Manager Least Privilege Manager Control Panel Rule for “Device Manager.” Again, you don’t need to perform the other steps in this video, you just want to verify that Device Manager can be overcome when Endpoint Policy ManagerLeast Privilege Manager is engaged. Remember to test this step as a proposed end-user who is running as a Standard User and doesn’t have Local Admin Rights.

Video: [Kill Local Admin Rights (Run applications with Least Privilege)](/docs/policypak/policypak/video/leastprivilege/localadminrights.md)

## Setting up Common Scenarios Most Customers need right away

If you are already running without Local Admin Rights, the top requests we get are to enable customers to perform:

- Printer installations
- Network Card Changes (DHCP vs. Static).
- Removing Installed Programs

As such we have some Helper Tools for these specific scenarios and pre-configured guidance to get them set up.

![poc2](/img/product_docs/policypak/policypak/leastprivilege/poc2.png)

For an overview, please see [Overcome Network Card, Printer, and Remove Programs UAC prompts](/docs/policypak/policypak/video/leastprivilege/uacprompts.md) and watch all videos in that section.

And because there’s an additional way to change Network Card Settings, you’ll want to also add an extra rule which you can learn how to do here: [COM Support](/docs/policypak/policypak/video/leastprivilege/comsupport.md)

## (Optional, Recommended): Creating an “example machine” with applications you know you need to overcome and (Part 3B) using Endpoint Policy Manager recommended rules

Of course, you have many machines out in the field where you want to remove local admin rights and use rules to replace them. However, if you also have the applications, you already know you need rules for, it is best to try these out in a test lab instead of relying on end-user machines and auditing events (explained later.)

So, on a test machineyou control, we recommend installing all the software you’d like to elevate and work around UAC prompts. Install the Endpoint Policy Manager Client Side Extension on this machine. Because Endpoint Policy Manager Least Privilege Manager doesn’t have any rules yet, the end-user software won’t work as expected and should present UAC prompts.

For more in formation on Endpoint Policy Manager Least Privilege Manager Pre-Configured rules, and to to see how many you can use right away, without having to generate your own rules, please see [Installing applications-and-Preconfigured-Rules](/docs/policypak/policypak/video/leastprivilege/installapplications.md)

![poc3](/img/product_docs/policypak/policypak/leastprivilege/poc3.png)

For the remaining applications where Endpoint Policy Manager Least Privilege Manager doesn’t have pre-configured rules, you’ll have to create your own rules.

You need to get familiar with the Best Practices, so you don’t “over permission” your applications. Therefore, as you go to create rules for your remaining applications on your test machine, please be familiar with the following video content:

- [Best Practices for Elevating User-Based Installs](/docs/policypak/policypak/video/leastprivilege/bestpractices/elevatinguserbasedinstalls.md)
- [Security and Child Processes](/docs/policypak/policypak/video/leastprivilege/bestpractices/securitychildprocesses.md)
- [Increase security by reducing rights on Open/Save dialogs](/docs/policypak/policypak/video/leastprivilege/bestpractices/opensavedialogs.md)
- [Endpoint Privilege Manager and Wildcards](/docs/policypak/policypak/video/leastprivilege/bestpractices/wildcards.md)

The more rules you can create to overcome your UAC prompts in these test machined, the easier it will be down the line, so users are only left with the UAC prompts you didn’t know about.

## (Optional): Integration with Netwrix Privilege Secure

If you are already a Netwrix Privilege Secure customer, you might want to also tie in Endpoint Policy Manager to Netwrix Privilege Secure. If you wish to perform these steps, please refer to this video: [Netwrix Privilege Secure and the NPS/Endpoint Policy Manager Client](/docs/policypak/policypak/video/leastprivilege/integration/privilegesecureclient.md)

## Turn on Global Auditing & Discovery to generate Interesting Events

Now that you’ve got severalrules created, you should be down to only the items you don’t know about on endpoint machines. You can turn on Auditing & Discovery to generate interesting events when users run (or attempt to run) many applications with Local Admin Rights. The two items you should turn on for starters are below.

![poc4](/img/product_docs/policypak/policypak/leastprivilege/poc4.png)

The way you do this is a little different from Group Policy vs. Endpoint Policy Manager Cloud. We recommend getting familiar with Eventing in general, and then turning on Discovery. Additionally, you can Auto-Create Policy from Global Audit Events once you’ve learned which applications require elevation. For more information on this issue, please see: [Events](/docs/policypak/policypak/video/leastprivilege/events.md)

Resulting events on endpoints look similar to an item like this:

![poc5](/img/product_docs/policypak/policypak/leastprivilege/poc5.png)

List of Endpoint Policy Manager Event Categories and IDs:

- 6200 AUDIT - Process runs elevated. This event will show if the user has local admin rights
- 6205 AUDIT - Process requires elevation. This event will show if the User is a STANDARD USER (UAC Prompt)
- 6206 A COM object requires elevation - This event will show if the User is a STANDARD USER (UAC Prompt)
- 6207 An ActiveX installer requires elevation - This event will show if the User is a STANDARD USER (UAC Prompt)

## (Optional, Recommended): Capture and Forward Events from Endpoints

If you are using Endpoint Policy Manager Cloud, this is enabled automatically for you. However, you need to turn it on for each Cloud group. For more information on this issue, please see: [Endpoint Policy Manager Cloud + PPLPM + Events: Collect Events in the Cloud](/docs/policypak/policypak/video/leastprivilege/cloudevents.md)

__NOTE:__ Endpoint Policy Manager Cloud Trailers and Customers get 24-hours of rolling logs stored. You can talk with Endpoint Policy Manager Sales about how to increase the number of days stored in Endpoint Policy Manager Cloud.

If you are already a Netwrix Auditor Customer, you can forward interesting Endpoint Policy Manager Least Privilege Manager events from endpoint computers to Netwrix Auditor so you can take action. This is recommended if you already own Netwrix Auditor For more information on this, please see: [How to use Netwrix Auditor to Report on Endpoint Policy Manager events](/docs/policypak/policypak/integration/auditor/reports.md).

An example of the kind of data you get back can be seen here.

![poc12](/img/product_docs/policypak/policypak/leastprivilege/poc12.png)

You may also use the in-box Windows Event System to forward interesting Endpoint Policy Manager Least Privilege Manager events from endpoint computers to a central source. The steps to do this are found here: [How to forward interesting events for Least Privilege Manager (or anything else) to a centralized location using Windows Event Forwarding.](/docs/policypak/policypak/leastprivilege/windowseventforwarding.md)

You may also use Azure Log Analytics if you wish to store interesting Endpoint Policy Manager Least Privilege Manager events from endpoints in Azure. For more information on this issue, please see: [Windows 10 (and Server) Event Logs to Azure Log Analytics Walkthru](/docs/policypak/policypak/tips/eventlogs.md).

## Removing End-Users’ Local Admin Rights (if they still have them)

At this point, this guide has provided advice if you have already removed local admin rights and if your users are still running with Local Admin Rights. However, we often get the question of how to perform this as a bulk task to remove Local Admin Rights from end-users.

For information on how to perform this, please see [Use Group Policy to remove local admin rights (then Endpoint Policy Manager to enable Least Privilege)](/docs/policypak/policypak/video/leastprivilege/removelocaladmin.md). While you can remove end-users local admin rights all at once, we recommend you proceed gradually. This will avoid potential issues with an increase in requests for help as users may need access in some situations.

## Generating Rules from Auditing Events

Once you have events generating on endpoints and you have access to those events (directly or via Event Forwarding, Netwrix Auditor, or another source), you can auto-create rules from those events.

![poc10](/img/product_docs/policypak/policypak/leastprivilege/poc10.png)

For details on how to do this on-prem, please see [Auto-Create Policy from Global Audit event](/docs/policypak/policypak/video/leastprivilege/globalauditevent.md)[Auto-Create Policy from Global Audit event](/docs/policypak/policypak/video/leastprivilege/globalauditevent.md)

For details on how to do it with Endpoint Policy Manager Cloud, please see [Endpoint Policy Manager Cloud + PPLPM + Events: Collect Events in the Cloud](/docs/policypak/policypak/video/leastprivilege/cloudevents.md). Note there is a new (not shown in the video) Generate Rule(s) button in Endpoint Policy Manager Cloud.

![poc11](/img/product_docs/policypak/policypak/leastprivilege/poc11.png)

## Turn on Admin Approval

You’ve already created the rules for the applications you know, and turned on Discovery Auditing for the applications you don’t know. However, you can also enable end users to be proactive and request one-time workarounds for UAC prompts without an automatic rule in place.

![poc6](/img/product_docs/policypak/policypak/leastprivilege/poc6.png)

For more in formation on the Endpoint Policy Manager Admin Approval feature, please see [Admin Approval demo](/docs/policypak/policypak/video/leastprivilege/adminapproval/demo.md) (all the videos in that section).

The goal is to minimize the times when users need one-off approval where you can implement automatic rules from the details you gather.

## Set up Company Branding

Admin Approval and other Endpoint Policy Manager Least Privilege Manager dialogs that appear to users can be branded with your company logo, colors, and text messages.

![poc7](/img/product_docs/policypak/policypak/leastprivilege/poc7.png)

For more information on branding, please see [Branding the UI and Dialogs](/docs/policypak/policypak/video/leastprivilege/branding.md).

## (Optional): Turn on Self Elevate

Use Endpoint Policy Manager Least Privilege Manager Self Elevate mode to overcome UAC prompts without requiring specific rules. This is useful if you want to take away local admin rights, but still give users the ability to "break the glass" if they have an emergency.

![poc9](/img/product_docs/policypak/policypak/leastprivilege/poc9.png)

This technique isn't generally recommended due to a potential lowering of your security posture, but it can be especially useful in the right circumstances.

For more information see::

- [Self Elevate Mode](/docs/policypak/policypak/video/leastprivilege/selfelevatemode/demo.md)
- [Endpoint Privilege: Re-Authenticate with Self Elevate](/docs/policypak/policypak/video/leastprivilege/selfelevatemode/reauthenticate.md)

## (Optional) Turning on Endpoint Policy Manager SecureRun(TM)

Endpoint Policy Manager Least Privilege Manager has built-in ransomware protection, blocking the user from downloading, and then running applications you didn’t sanction. When SecureRun™ is on, Endpoint Policy Manager Least Privilege Manager checks to see who owns the file executable, MSI file, script, or Java JAR file. When users download files off the Internet or copy them from a USB flash drive, they own the file, and since they aren't on the SecureRun™ Members list, Endpoint Policy Manager Least Privilege Manager will block all applications that you (the admin on the machine) didn’t install.

![poc13](/img/product_docs/policypak/policypak/leastprivilege/poc13.png)

However, if users were accustomed to downloading their applications, when Endpoint Policy Manager SecureRun is enabled you could get an increase in helpdesk calls from users unable to run applications they have installed.

In a previous step, you removed your users from the Local Administrators group if they were previously provided with full Local Admin Rights. But these unsanctioned, previously downloaded applications will still run (Until Endpoint Policy Manager SecureRun is enabled.)

Before you fully enable Endpoint Policy Manager SecureRun you can, once again, rely upon Global Audit Settings to alert you for untrusted applications. These are the ones not owned by the Computername\Administrator, the SYSTEM, TrustedInstaller, or other Administrators on the machine.

Refer to the Global Auditing step to re-enable these settings to turn on Events for Untrusted and optionally unsigned applications.

![poc15](/img/product_docs/policypak/policypak/leastprivilege/poc15.png)

Endpoint Policy Manager Least Privilege Manager Discovery Audit Policy Events Additional Notes

- 6210 AUDIT- Process is untrusted and would have been blocked by SecureRun. Helps with discovering user-based installs.

- 6215 - Executable is unsigned and would have been blocked by SecureRun Helps with discovering user-based installs.

Then you can investigate those Event IDs that come in and create Allow and Log actions. To learn more about how Endpoint Policy Manager Least Privilege Manager SecureRun helps you keep ransomware and unknown applications at bay, but open up specific applications as needed with Allow and Log actions, please see [Using Least Privilege Manager's SecureRun Feature](/docs/policypak/policypak/video/leastprivilege/securerun/feature.md)

For general tips on how to use SecureRun™ please see [How can I allow "Inline commands" blocked by SecureRun when a random path or filename is created each time?](/docs/policypak/policypak/leastprivilege/securerun/allowinlinecommands.md)

## Final Thoughts

This guide should give you the framework for getting your Endpoint Policy ManagerLeast Privilege Manager implementation up and rolling with Endpoint Policy Manager.

The next sections have three appendices with project rollout steps (referring to videos and documentation we’ve mentioned here: one for Active Directory/Group Policy, one for Endpoint Policy Manager Cloud, and one for Endpoint Policy Manager with an MDM service like Intune.

If you need any help along the way, simply open a ticket at [Netwrix Support](https://www.netwrix.com/tickets.html#Netwrix-Support) and we’ll be happy to give you one-on-one attention to help you out.

## Appendix A: Sample Endpoint Privilege Manager Project POC Plan for Endpoint Policy Manager with Active Directory / GPOs; removing local admin rights for 30 Developers

Estimated Milestone Details and Target Dates

| Milestone | Details & Tasks |  |
| --- | --- | --- |
| M1 Pre-Requisites | - Verify you actually want to use Endpoint Policy Manager + Group Policy method and not some other method or some kind of hybrid approach: See [PolicyPak Solution Methods: Group Policy, MDM, UEM Tools, and PolicyPak Cloud compared](https://helpcenter.netwrix.com/bundle/PolicyPak/page/Content/PolicyPak/Video/GettingStarted/SolutionMethods.html). - Identify 3 friendly developers for this project. - Identify the remaining devices for POC, but focus on first three. - Download Endpoint Policy Manager from portal.policypak.com and get organized. See [Netwrix Endpoint Policy Manager Quick Start](/docs/policypak/policypak/gettingstarted/quickstart/overview.md)   . - Get the Endpoint Policy Manager Quickstart Guide. See [Netwrix Endpoint Policy Manager Quick Start](/docs/policypak/policypak/gettingstarted/quickstart/overview.md)   . - Get familiar with Endpoint Policy Manager + Group Policy Basics . See [Endpoint Policy Manager Explained: In about two minutes](/docs/policypak/policypak/video/grouppolicy/explained.md) - On three developer machines perform the quick-licensing method via rename method. See [What is the fastest way to get started in an Endpoint Policy Manager trial, without running the License Request Tool?](/docs/policypak/policypak/license/trial.md) or run licensing tool. After receiving your trial keys from sales, install your trial or full licenses for your on-prem Active Directory. See [How to install UNIVERSAL licenses for NEW Customers (via GPO, SCCM or MDM)](/docs/policypak/policypak/video/license/installuniversal.md) - Install the Endpoint Policy Manager CSE on the three developer stations. - Move 3 developers into Active Directory OU named “Endpoint Policy Manager Test Devs” . - Verify Endpoint Policy Manager Least Privilege Manager is working with the “Device Manager” test. See [Kill Local Admin Rights (Run applications with Least Privilege)](/docs/policypak/policypak/video/leastprivilege/localadminrights.md) - Create a Group Policy Object which turns on PPLPM Global Auditing. See [Use Discovery to know what rules to make as you transition from Local Admin rights](/docs/policypak/policypak/video/leastprivilege/discovery.md) . - Identify KNOWN applications for Development stations which require Admin rights. | Day 1 - 3 |
| M2 Install PolicyPak CSE, common scenarios and known applications | - Install Endpoint Policy Manager CSE on the remaining 27 endpoints; ensure success (NO POLICIES, just the Endpoint Policy Manager moving parts) - (Optional) Set up Common Scenarios:    - Printers, Remove Programs and IP Address changes. See [Overcome Network Card, Printer, and Remove Programs UAC prompts](/docs/policypak/policypak/video/leastprivilege/uacprompts.md)   - Second Method for Network Cards: [COM Support](/docs/policypak/policypak/video/leastprivilege/comsupport.md) - Create rules for KNOWN applications which require ADMIN Rights.    - [Best Practices for Elevating User-Based Installs](/docs/policypak/policypak/video/leastprivilege/bestpractices/elevatinguserbasedinstalls.md)   - [Security and Child Processes](/docs/policypak/policypak/video/leastprivilege/bestpractices/securitychildprocesses.md)   - [Increase security by reducing rights on Open/Save dialogs](/docs/policypak/policypak/video/leastprivilege/bestpractices/opensavedialogs.md)   - [Endpoint Privilege Manager and Wildcards](/docs/policypak/policypak/video/leastprivilege/bestpractices/wildcards.md) - Use Endpoint Policy Manager Preconfigured rules when you can. See [Installing applications-and-Preconfigured-Rules](/docs/policypak/policypak/video/leastprivilege/installapplications.md) | Day 4 -6 |
| M3 Set up Event Forwarding | - Pick one (or choose another method, like Splunk, etc.)   . - Event Forwarding with Netwrix Auditor. See [How to use Netwrix Auditor to Report on Endpoint Policy Manager events](/docs/policypak/policypak/integration/auditor/reports.md) - Event Forwarding with Windows Eventing. See [How to forward interesting events for Least Privilege Manager (or anything else) to a centralized location using Windows Event Forwarding.](/docs/policypak/policypak/leastprivilege/windowseventforwarding.md) - Event Forwarding with Azure Log Analytics. See [Windows 10 (and Server) Event Logs to Azure Log Analytics Walkthru](/docs/policypak/policypak/tips/eventlogs.md) | Day 7 -9 |
| M4 Begin Test | - Remove local admin rights for 3 developer endpoints. One suggested method / demo is here (there are other ways to perform this task): [Use Group Policy to remove local admin rights (then Endpoint Policy Manager to enable Least Privilege)](/docs/policypak/policypak/video/leastprivilege/removelocaladmin.md) - Start to Generate Rules from Auditing Events. See [Auto-Create Policy from Global Audit event](/docs/policypak/policypak/video/leastprivilege/globalauditevent.md). - Set up Admin Approval (Secret / policy). See [Auto-Create Policy from Global Audit event](/docs/policypak/policypak/video/leastprivilege/globalauditevent.md) and [Admin Approval demo](/docs/policypak/policypak/video/leastprivilege/adminapproval/demo.md) - Set up Endpoint Policy Manager Least Privilege Manager “Approvers” workflow (Identify APPROVER(s), get the AA tool up and going). - Optionally: Set up Endpoint Policy Manager Least Privilege Manager UI branding. See [Branding the UI and Dialogs](/docs/policypak/policypak/video/leastprivilege/branding.md) - Deploy Admin Approval to existing systems. - Optional: Deploy Endpoint Policy Manager Least Privilege Manager Branding to existing systems. - Look at incoming EVENTS to determine the issues to make more rules. | Day 10 |
| M5 Review Events | - Turn on Self Elevate for existing 3 developers. - Create documentation for Developers on how to interact with Endpoint Policy Manager Self Elevate method. ([Self Elevate Mode](/docs/policypak/policypak/video/leastprivilege/selfelevatemode/demo.md)). - Review EVENTS to determine the issues to create rules. | Day 11 |
| M6 Addition | - Add 7 more developer PCs to existing 3 and remove local admin rights using existing rules. (Don’t use Self elevate on new 7 endpoint, just the first three.) | Day 12 |
| M7 Review Events | - Look at EVENTS to determine the issues to make more rules. - Investigate if SELF ELEVATE is being used or not by the 3 first developers (vs. Admin approval vs Direct Rules). - The is to get to as many direct rules as possible in the fastest amount of time. | Day 13 |
| M8 Make Rules | Make more Direct rules from 10 endpoints | Day 14 |
| M9 Addition | Add +5 endpoints to Endpoint Policy Manager Active Directory OU and remove their local admin rights. | Day 15 |
| M10 Review Events | Look at EVENTS to determine the issues to make more direct rules. | Day 16 |
| M11 Addition | Add +5 endpoints Endpoint Policy Manager Active Directory OU and remove their local admin rights. | Day 17 |
| M12 Review Events | Look at EVENTS to determine the issues to make more direct rules. | Day 18 |
| M13 Addition | Add +5 endpoints to Endpoint Policy Manager Active Directory OU and remove their local admin rights. | Day 19 |
| M14 Review Events | Look at EVENTS to determine the issues to make more rules. | Day 20 |
| M15 Addition | Add +5 endpoints Endpoint Policy Manager Active Directory OU and remove their local admin rights. | Day 21 |
| M16 Review Events | Look at EVENTS to determine the issues to make more rules. | Day 22 |
| M17 Remaining | Add Remaining endpoints to Endpoint Policy Manager Active Directory OU and remove their local admin rights. | Day 23 |
| M18 SecureRun (Optional) | • Turn on Global Auditing for Untrusted and Unsigned applications.  • Try turning on SecureRun for three developers.   - [Using Least Privilege Manager's SecureRun Feature](/docs/policypak/policypak/video/leastprivilege/securerun/feature.md) - [How can I allow "Inline commands" blocked by SecureRun when a random path or filename is created each time?](/docs/policypak/policypak/leastprivilege/securerun/allowinlinecommands.md) | Day 24 |
| M19 SecureRun Rollout (Optional) | Add +5 endpoints per day and triage incoming SecureRun blocks with “Allow and Log” rules. Repeat each day with +5 endpoints. | Day 25+ |

## Appendix B: Sample Endpoint Privilege Manager Project POC Plan for Endpoint Policy Manager Cloud, removing local admin rights for 30 Developers.

Estimated Milestone Details and Target Dates

| Milestone | Details & Tasks |  |
| --- | --- | --- |
| M1 Pre-Requisites | - Verify you actually want to use Endpoint Policy Manager + Cloud method and not some other method or some kind of hybrid approach. See [Endpoint Policy ManagerSolution Methods: Group Policy, MDM, UEM Tools, and Endpoint Policy Manager Cloud compared.](/docs/policypak/policypak/video/gettingstarted/solutionmethods.md) - Identify 3 friendly developers for this project. - Identify the remaining devices for POC, but focus on first three. - Get familiar with Endpoint Policy Manager Cloud Basics. See [Endpoint Policy Manager Cloud: Two minute introduction](/docs/policypak/policypak/video/cloud/introduction.md) - Download Endpoint Policy Manager bits from portal.policypak.com and Cloud MSI from cloud.policypak.com and get organized [Installation Quick Start](/docs/policypak/policypak/gettingstarted/quickstart/overviewinstall.md). - Get the Endpoint Policy Manager Quickstart Guide. See [Netwrix Endpoint Policy Manager Quick Start](/docs/policypak/policypak/gettingstarted/quickstart/overview.md) - Set up on prem test lab, even though we’re using Endpoint Policy Manager Cloud (Best Practice). See [Endpoint Policy Manager Cloud: What you need to get Started](/docs/policypak/policypak/video/cloud/testlab/start.md). - Install Endpoint Policy Manager Cloud Client which automatically installs the Endpoint Policy Manager CSE on 3 devices. - Identify the remaining devices for POC, but focus on first three. - Move 3 Endpoint Policy Manager cloud joined devices to Endpoint Policy Manager Cloud Company “GROUP1”. - Verify Endpoint Policy Manager Least Privilege Manager is working with the “Device Manager” test. See [Kill Local Admin Rights (Run applications with Least Privilege)](/docs/policypak/policypak/video/leastprivilege/localadminrights.md) - Turn on PPLPM Global Auditing for Cloud. See [Endpoint Policy Manager Cloud + PPLPM + Events: Collect Events in the Cloud](/docs/policypak/policypak/video/leastprivilege/cloudevents.md) - Test to make sure PPC Events are seen in Endpoint Policy Manager Cloud. - Identify KNOWN applications for Development stations which require Admin rights. | Day 1-3 |
| M2 Install PPC | - Install Endpoint Policy Manager CSE on the remaining 27 endpoints; ensure success. (NO POLICIES, just the Endpoint Policy Manager moving parts.). - (Optional) Set up Common Scenarios for Printers, Remove Programs and IP Address changes.    - [Overcome Network Card, Printer, and Remove Programs UAC prompts](/docs/policypak/policypak/video/leastprivilege/uacprompts.md)   - [COM Support](/docs/policypak/policypak/video/leastprivilege/comsupport.md) - Create rules for KNOWN applications which require ADMIN Rights.    - [Best Practices for Elevating User-Based Installs](/docs/policypak/policypak/video/leastprivilege/bestpractices/elevatinguserbasedinstalls.md)   - [Security and Child Processes](/docs/policypak/policypak/video/leastprivilege/bestpractices/securitychildprocesses.md)   - [Increase security by reducing rights on Open/Save dialogs](/docs/policypak/policypak/video/leastprivilege/bestpractices/opensavedialogs.md)   - [Endpoint Privilege Manager and Wildcards](/docs/policypak/policypak/video/leastprivilege/bestpractices/wildcards.md) - Use Endpoint Policy Manager Preconfigured rules when you can. See [Installing applications-and-Preconfigured-Rules](/docs/policypak/policypak/video/leastprivilege/installapplications.md) | Day 4-6 |
| M3 Begin Test | - Remove local admin rights for 3 developer endpoints. One suggested method / demo is here (there are other ways to perform this task): [Use Group Policy to remove local admin rights (then Endpoint Policy Manager to enable Least Privilege)](/docs/policypak/policypak/video/leastprivilege/removelocaladmin.md) - Start to Generate Rules from Auditing Events [Auto-Create Policy from Global Audit event](/docs/policypak/policypak/video/leastprivilege/globalauditevent.md) - Set up Admin Approval (Secret / policy): [Auto-Create Policy from Global Audit event](/docs/policypak/policypak/video/leastprivilege/globalauditevent.md) and [Admin Approval demo](/docs/policypak/policypak/video/leastprivilege/adminapproval/demo.md) - Set up Endpoint Policy Manager Least Privilege Manager “Approvers” workflow (Identify APPROVER(s), get the AA tool up and going.) - Optionally: Set up Endpoint Policy Manager Least Privilege Manager UI branding: [Branding the UI and Dialogs](/docs/policypak/policypak/video/leastprivilege/branding.md) - Deploy Admin Approval to existing systems. - Optional: Deploy Endpoint Policy Manager Least Privilege Manager Branding to existing systems. - Look at incoming EVENTS in Endpoint Policy Manager Cloud to determine the issues to make more rules. | Day 7-8 |
| M4 Review Events | - Turn on Self Elevate for existing 3 developers. - Create documentation for Developers on how to interact with Endpoint Policy Manager Self Elevate method. See [Self Elevate Mode](/docs/policypak/policypak/video/leastprivilege/selfelevatemode/demo.md) - Review EVENTS to determine the issues to create rules. | Day 9 |
| M5 Addition | Add 7 more developer PCs to existing 3 and remove local admin rights using existing rules. (Don’t use Self elevate on new 7 endpoint, just the first three). | Day 10 |
| M6 Review Events | - Look at EVENTS to determine the issues to make more rules. - Investigate if SELF ELEVATE is being used or not by the 3 first developers (vs. Admin approval vs Direct Rules.) - Goal is to get to as many direct rules as possible in the fastest amount of time. | Day 11 |
| M7 Make Rules | Make more Direct rules from 10 endpoints. | Day 12 |
| M8 Addition | Add +5 endpoints to Endpoint Policy Manager Cloud and remove their local admin rights. | Day 13 |
| M9 Review Events | Look at EVENTS to determine the issues to make more direct rules. | Day 14 |
| M10 Addition | Add +5 endpoints to Endpoint Policy Manager Cloud and remove their local admin rights. | Day 15 |
| M11 Review Events | Look at EVENTS to determine the issues to make more direct rules. | Day 16 |
| M12 Addition | Add +5 endpoints to Endpoint Policy Manager Cloud and remove their local admin rights. | Day 17 |
| M13 Review Events | Look at EVENTS to determine the issues to make more rules. | Day 18 |
| M14 Addition | Add +5 endpoints to Endpoint Policy Manager Cloud and remove their local admin rights. | Day 19 |
| M15 Review Events | Look at EVENTS to determine the issues to make more rules. | Day 20 |
| M16 Remaining | Add Remaining endpoints to Endpoint Policy Manager Cloud and remove their local admin rights. | Day 21 |
| M17 SecureRun Setup | - Turn on Global Auditing for Untrusted and Unsigned applications. - Try turning on SecureRun for three developers.    - [Using Least Privilege Manager's SecureRun Feature](/docs/policypak/policypak/video/leastprivilege/securerun/feature.md)   - [How can I allow "Inline commands" blocked by SecureRun when a random path or filename is created each time?](/docs/policypak/policypak/leastprivilege/securerun/allowinlinecommands.md) | Day 22 |
| M18+ SecureRun Rollout | Add +5 endpoints per day and triage incoming SecureRun blocks with “Allow and Log” rules. Repeat each day with +5 endpoints. | Day 23+ |

## Appendix C: Sample Endpoint Privilege Manager Project POC Plan for Endpoint Policy Manager with an MDM service like Intune, removing local admin rights for 30 Developers.

Estimated Milestone Details and Target Dates

| Milestones | Details & Tasks |  |
| --- | --- | --- |
| M1 Pre-Requisites | - Verify you actually want to use Endpoint Policy Manager + Cloud method and not some other method or some kind of hybrid approach. See [Endpoint Policy ManagerSolution Methods: Group Policy, MDM, UEM Tools, and Endpoint Policy Manager Cloud compared.](/docs/policypak/policypak/video/gettingstarted/solutionmethods.md) - Identify 3 friendly developers for this project. - Identify the remaining devices for POC, but focus on first three. - Download Endpoint Policy Manager bits from portal.policypak.com and Cloud MSI from cloud.policypak.com and get organized. See the [Installation Quick Start](/docs/policypak/policypak/gettingstarted/quickstart/overviewinstall.md). - Get the Endpoint Policy Manager Quickstart Guide. See [Netwrix Endpoint Policy Manager Quick Start](/docs/policypak/policypak/gettingstarted/quickstart/overview.md)  - On ONE machine (any machine) perform the MDM “Walk before you run” test. See [Endpoint Policy Manager and MDM walk before you run](/docs/policypak/policypak/video/mdm/testsample.md) - On three developer machines perform the quick-licensing method via rename (see[What is the fastest way to get started in an Endpoint Policy Manager trial, without running the License Request Tool?](/docs/policypak/policypak/license/trial.md) or run licensing tool and after receiving your trial keys from sales, install your trial or full licenses for your MDM licenses. See [How to install UNIVERSAL licenses for NEW Customers (via GPO, SCCM or MDM)](/docs/policypak/policypak/video/license/installuniversal.md) - Install the Endpoint Policy Manager CSE on the three developer stations. - Move 3 developers into an Azure/MDM group named “Endpoint Policy Manager Test Devs”. - Target deploy the Endpoint Policy Manager CSE to the group. - Get to understand Endpoint Policy Manager Least Privilege Manager + MDM Service (Exporting policies, then wrapping up XMLs into MSIs). See [Using Least Privilege Manager with your MDM service](/docs/policypak/policypak/video/leastprivilege/mdm.md) - Verify Endpoint Policy Manager Least Privilege Manager is working wit the “Device Manager” test. See [Kill Local Admin Rights (Run applications with Least Privilege)](/docs/policypak/policypak/video/leastprivilege/localadminrights.md) - Create a policy which turns on PPLPM Global Auditing, export as XML and wrap up as MSI for deployment via MDM. See [Use Discovery to know what rules to make as you transition from Local Admin rights](/docs/policypak/policypak/video/leastprivilege/discovery.md) - Identify KNOWN applications for Development stations which require Admin rights. | Day 1-3 |
| M2 Install Endpoint Policy Manager CSE, common scenarios and known applications | - Install Endpoint Policy Manager CSE on the remaining 27 endpoints; ensure success. (NO POLICIES, just the PolicyPak moving parts). - (Optional) Set up Common Scenarios for Printers, Remove Programs and IP Address changes. See [Overcome Network Card, Printer, and Remove Programs UAC prompts](/docs/policypak/policypak/video/leastprivilege/uacprompts.md) and [COM Support](/docs/policypak/policypak/video/leastprivilege/comsupport.md)  - Create rules for KNOWN applications which require ADMIN Rights.    - [Best Practices for Elevating User-Based Installs](/docs/policypak/policypak/video/leastprivilege/bestpractices/elevatinguserbasedinstalls.md)   - [Security and Child Processes](/docs/policypak/policypak/video/leastprivilege/bestpractices/securitychildprocesses.md)   - [Increase security by reducing rights on Open/Save dialogs](/docs/policypak/policypak/video/leastprivilege/bestpractices/opensavedialogs.md)   - [Endpoint Privilege Manager and Wildcards](/docs/policypak/policypak/video/leastprivilege/bestpractices/wildcards.md) - Use Endpoint Policy Manager Preconfigured rules when you can. See [Installing applications-and-Preconfigured-Rules](/docs/policypak/policypak/video/leastprivilege/installapplications.md) | Day 4-6 |
| M3 Set up Event Forwarding | - Pick one (or choose another method, like Splunk, etc.)    - Event Forwarding with Netwrix Auditor. See [How to use Netwrix Auditor to Report on Endpoint Policy Manager events](/docs/policypak/policypak/integration/auditor/reports.md)   - Event Forwarding with Windows Eventing. See [How to forward interesting events for Least Privilege Manager (or anything else) to a centralized location using Windows Event Forwarding.](/docs/policypak/policypak/leastprivilege/windowseventforwarding.md)   - Event Forwarding with Azure Log Analytics (likely best scenario for MDM environments). See [Windows 10 (and Server) Event Logs to Azure Log Analytics Walkthru](/docs/policypak/policypak/tips/eventlogs.md) | Day 7-9 |
| M4 Begin Test | - Remove local admin rights for 3 developer endpoints. One suggested method / demo is here (there are other ways to perform this task): [Use Group Policy to remove local admin rights (then Endpoint Policy Manager to enable Least Privilege)](/docs/policypak/policypak/video/leastprivilege/removelocaladmin.md) - Start to Generate Rules from Auditing Events. See [Auto-Create Policy from Global Audit event](/docs/policypak/policypak/video/leastprivilege/globalauditevent.md). - Set up Admin Approval (Secret / policy). See [Auto-Create Policy from Global Audit event](/docs/policypak/policypak/video/leastprivilege/globalauditevent.md) and [Admin Approval demo](/docs/policypak/policypak/video/leastprivilege/adminapproval/demo.md) - Optionally: Set up Endpoint Policy Manager Least Privilege Manager UI branding. See [Branding the UI and Dialogs](/docs/policypak/policypak/video/leastprivilege/branding.md) - Deploy Admin Approval to existing systems. - Optional: Deploy Endpoint Policy Manager Least Privilege Manager Branding to existing systems. - Look at incoming EVENTS to determine the issues to make more rules. | Day 10 |
| M5 Review Events | - Turn on Self Elevate for existing 3 developers. - Create documentation for Developers on how to interact with Endpoint Policy Manager Self Elevate method. See [Self Elevate Mode](/docs/policypak/policypak/video/leastprivilege/selfelevatemode/demo.md) - Review EVENTS to determine the issues to create rules. | Day 11 |
| M6 Addition | Add 7 more developer PCs to existing 3 and remove local admin rights using existing rules. (Don’t use Self elevate on new 7 endpoint, just the first three.) | Day 12 |
| M7 Review Events | - Look at EVENTS to determine the issues to make more rules. - Investigate if SELF ELVATE is being used or not by the 3 first developers (vs. Admin approval vs Direct Rules). - Goal is to get to as many direct rules as possible in the fastest amount of time. | Day 13 |
| M8 Make Rules | Make more Direct rules from 10 endpoints. | Day 14 |
| M9 Addition | Add +5 endpoints to Endpoint Policy Manager group and remove their local admin rights. | Day 15 |
| M10 Review Events | Look at EVENTS to determine the issues to make more direct rules. | Day 16 |
| M11 Addition | Add +5 endpoints to Endpoint Policy Manager group and remove their local admin rights. | Day 17 |
| M12 Review Events | Look at EVENTS to determine the issues to make more direct rules. | Day 18 |
| M13 Addition | Add +5 endpoints to Endpoint Policy Manager group and remove their local admin rights. | Day 19 |
| M14 Review Events | Look at EVENTS to determine the issues to make more rules. | Day 20 |
| M15 Addition | Add +5 endpoints to Endpoint Policy Manager group and remove their local admin rights. | Day 21 |
| M16 Review Events | Look at EVENTS to determine the issues to make more rules. | Day 22 |
| M17 Remaining | Add Remaining endpoints to Endpoint Policy Manager group and remove their local admin rights. | Day 23 |
| M18 SecureRun Setup | - Turn on Global Auditing for Untrusted and Unsigned applications. - Try turning on SecureRun for three developers.    - [Using Least Privilege Manager's SecureRun Feature](/docs/policypak/policypak/video/leastprivilege/securerun/feature.md)   - [How can I allow "Inline commands" blocked by SecureRun when a random path or filename is created each time?](/docs/policypak/policypak/leastprivilege/securerun/allowinlinecommands.md) | Day 24 |
| M19 SecureRun Rollout | Add +5 endpoints per day and triage incoming SecureRun blocks with “Allow and Log” rules. Repeat each day with +5 endpoints. | Day 25+ |

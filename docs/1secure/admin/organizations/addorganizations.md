---
id: add-organizations
title: "Add Organizations"
pagination_label: "Add Organizations"
sidebar_label: "Add Organizations"
sidebar_position: 32
description: "Follow step-by-step instructions to add new organizations to your 1Secure system."
---

# Add Organizations

Follow the steps to add an organization.

**Step 1 –** On the Netwrix 1Secure Website, on the **Home** page, select the Add organization icon
to add an organization.

![organization_adding](../../../../static/img/product_docs/1secure/admin/organizations/organization_adding.webp)

**Step 2 –** On the Add Organization (Step 1 of 4) window, specify the following:

- Name – Specify a name for the organization
- Timezone – Select a timezone for the organization
- Country – Select a country for the organization
- Tags – Select tag(s) for the organization. Tags provide a way of adding metadata to the tenancies
  being managed. To specify multiple tags, select them one by one from the dropdown menu.
- Alert profile – Select an alert profile for the organization. Alert profiles enable you to group
  alert configurations and delivery notification settings together.
- Risk Profile – Select a risk profile for the organization. Risk profiles enable you to group
  thresholds together.
- Groups – Select a group for the organization. To assign an organization to multiple groups, select
  the groups one by one from the drop-down menu.

Click **Next**.

![addorganizationsselectdatasource](../../../../static/img/product_docs/1secure/admin/organizations/addorganizationsselectdatasource.webp)

**Step 3 –** On the Select Data Source (Step 2 of 4) window, add a preferred data source to your
organization:

- Active Directory
- Azure AD (now Microsoft Entra ID)
- Computer
- Exchange Online
- SharePoint Online

**NOTE:** See the [Sources and Connectors](sourcesandconnectors/index.md) topic for detailed
information.

![addorganizationssites](../../../../static/img/product_docs/1secure/admin/organizations/addorganizationssites.webp)

**Step 4 –** On the Configure source details (Step 3 of 4) window, add a site for your organization.
Sites are used to signify physical groupings within the organization. Click **Next**.

**NOTE:** This step is displayed only when adding Active Directory and Computer sources.

See the [Add Sites to an Organization](addsites.md) topic for additional information.

![addorganizationsagent](../../../../static/img/product_docs/1secure/admin/organizations/addorganizationsagent.webp)

**Step 5 –** On the Configure source details (Step 3 of 4) window, follow the instructions to
install the agent. Please go to the [Install Agent](../../install/installagent.md) topic of the
online help. Click **Next**.

**NOTE:** Install the agent only for on-prem sources - Active Directory and Computer. This step is
displayed only when adding these sources.

![addorganizationssourcedetails](../../../../static/img/product_docs/1secure/admin/organizations/addorganizationssourcedetails.webp)

**Step 6 –** On the Configure source details (Step 3 of 4) window, specify your source settings. See
the [Sources and Connectors](sourcesandconnectors/index.md) topic for additional information.

![addorganizationssourcesandconnectors](../../../../static/img/product_docs/1secure/admin/organizations/addorganizationssourcesandconnectors.webp)

**Step 7 –** On the Choose new connector (Step 4 of 4) window, add the connectors for your sources
on. See the [Sources and Connectors](sourcesandconnectors/index.md) topic for additional
information.

**Step 8 –** Click **Finish** or **Save & Add another source** to add a source for your
organization.

The organization is now added.

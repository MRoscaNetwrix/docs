# Perform a Simulation

How to assess the impact of a modification on the role model, including the
[role catalog](/versioned_docs/usercube_6.1/usercube/user-guide/set-up/single-roles-catalog-creation/index.md),
[role assignment rules](/versioned_docs/usercube_6.1/usercube/user-guide/optimize/assignment-automation/automate-role-assignment/index.md)
and
[resource correlation rules](/versioned_docs/usercube_6.1/usercube/user-guide/set-up/categorization/correlation/index.md),
using a dedicated
[policy](/versioned_docs/usercube_6.1/usercube/user-guide/optimize/policy-creation/index.md).

## Overview

Usercube's simulations gather roles and rules which are to be created, modified or deleted, without
being inserted in the actual role model straight away. More specifically, a simulation can involve:

- [correlation rules](/versioned_docs/usercube_6.1/usercube/integration-guide/toolkit/xml-configuration/provisioning/resourcecorrelationrule/index.md)
  and
  [classification rules](/versioned_docs/usercube_6.1/usercube/integration-guide/toolkit/xml-configuration/provisioning/resourceclassificationrule/index.md);
- [scalar rules](/versioned_docs/usercube_6.1/usercube/integration-guide/toolkit/xml-configuration/provisioning/resourcetype/index.md)
  and
  [navigation rules](/versioned_docs/usercube_6.1/usercube/integration-guide/toolkit/xml-configuration/provisioning/resourcetype/index.md);
- [resource type rules](/versioned_docs/usercube_6.1/usercube/integration-guide/toolkit/xml-configuration/provisioning/resourcetype/index.md);
- [single roles](/versioned_docs/usercube_6.1/usercube/integration-guide/toolkit/xml-configuration/provisioning/singlerole/index.md)
  and
  [composite roles](/versioned_docs/usercube_6.1/usercube/integration-guide/toolkit/xml-configuration/provisioning/compositerole/index.md);
- [single role rules](/versioned_docs/usercube_6.1/usercube/integration-guide/toolkit/xml-configuration/provisioning/singlerolerule/index.md)
  and
  [composite role rules](/versioned_docs/usercube_6.1/usercube/integration-guide/toolkit/xml-configuration/provisioning/compositerolerule/index.md).

A simulation can also be created by the
[role mining tool](/versioned_docs/usercube_6.1/usercube/user-guide/optimize/assignment-automation/role-mining/index.md)
for the automation of role assignments.

Through simulation, integrators can:

1. create, modify or delete roles and rules in a given policy;

    Only one simulation can be active per policy.

2. observe via simulation reports the impact on the whole system, i.e. both assignments and
   provisioning results, before the changes are applied;
3. decide to confirm or cancel changes.

NETWRIX recommends using simulation whenever performing an action (creation/modification/deletion)
on the role model.

## Participants and Artifacts

Integrators are able to perform simulation if they master the new role model.

| Input                                                                                                                                                                                                                                                                                                                                                                                               | Output             |
| --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------ |
| [Role catalog](/versioned_docs/usercube_6.1/usercube/user-guide/set-up/single-roles-catalog-creation/index.md) (optional) [Role assignment rules](/versioned_docs/usercube_6.1/usercube/user-guide/optimize/assignment-automation/automate-role-assignment/index.md) (optional) [Categorized resources](/versioned_docs/usercube_6.1/usercube/user-guide/set-up/categorization/index.md) (optional) | Updated role model |

## Launch a Simulation

Launch a simulation by proceeding as follows:

1. Access the simulation list by clicking on **Simulations** on the home page, in the
   **Configuration** section.

    ![Home - Simulations](/img/versioned_docs/usercube_6.1/usercube/user-guide/optimize/simulation/home_simulations_v600.webp)

    ![Simulation List](/img/versioned_docs/usercube_6.1/usercube/user-guide/optimize/simulation/simulation_list_v602.webp)

2. Create a new simulation by clicking on the addition button at the top right corner.

    ![Addition Icon](/img/versioned_docs/usercube_6.1/usercube/user-guide/set-up/categorization/classification/iconadd_v602.svg)

3. Fill in the fields.

    ![Simulation List](/img/versioned_docs/usercube_6.1/usercube/user-guide/optimize/simulation/simulation_new_v602.webp)

4. Click on **+ Create**.
5. Perform changes through the **Roles Changes** and **Rules Changes** tabs and the following icons,
   respectively for addition, modification and deletion:

    ![Edition - Approval Icon](/img/versioned_docs/usercube_6.1/usercube/user-guide/set-up/categorization/classification/iconadd_v602.svg)

    ![Recommendation Icon](/img/versioned_docs/usercube_6.1/usercube/user-guide/optimize/simulation/simulation_iconedit_v600.svg)

    ![Discouragement Icon](/img/versioned_docs/usercube_6.1/usercube/user-guide/optimize/simulation/simulation_icondelete_v600.svg)

    At any time, you can click on the line of a previously made change to access its description,
    even click on **Cancel** to erase it.

    ![Cancel Change](/img/versioned_docs/usercube_6.1/usercube/user-guide/optimize/simulation/simulation_cancel_v602.webp)

6. Click on **Start** to launch the simulation.

    ![Start Simulation](/img/versioned_docs/usercube_6.1/usercube/user-guide/optimize/simulation/simulation_start_v602.webp)

7. After a few seconds, click on **Refresh** to display the simulation results.
8. Observe the results in the overview and in the Excel report available via the Download button.

    ![Download Icon](/img/versioned_docs/usercube_6.1/usercube/user-guide/set-up/initial-identities-loading/load-identities/icondownload_v602.svg)

## Shift from Simulation to Production

After all needed changes have been simulated, you can decide to apply or cancel them.

![Apply or Cancel Changes](/img/versioned_docs/usercube_6.1/usercube/user-guide/optimize/simulation/simulation_decision_v600.webp)

Then, the simulation is no longer active.

Clicking on **Apply** applies the simulated changes to the role model. You need to launch the
[Compute-RoleModel](/versioned_docs/usercube_6.1/usercube/integration-guide/toolkit/xml-configuration/jobs/tasks/server/computerolemodeltask/index.md)
task to observe the actual changes in users' entitlements.

## Impact of Modifications

Once you've applied or canceled the changes of a simulation, said simulation is no longer active. If
you still need to simulate changes on the same policy, you can create a new simulation.

Deleting a simulation doesn't impact the role model. It simply undoes the simulated changes which
haven't been applied yet.

## Verify Modification

In order to verify the process, check that the roles and rules are created with the right
parameters.

For roles, click on **Access Roles** on the home page in the **Configuration** section.

![Home Page - Access Roles](/img/versioned_docs/usercube_6.1/usercube/user-guide/set-up/categorization/resource-type-creation/home_roles_v602.webp)

Select the type of role that you want to check, and find the roles you created inside the right
category and with the right parameters.

![Select Roles](/img/versioned_docs/usercube_6.1/usercube/user-guide/set-up/single-roles-catalog-creation/category-creation/categorycreation_test_v602.webp)

For rules, click on **Access Rules** on the home page in the **Configuration** section.

![Home Page - Access Rules](/img/versioned_docs/usercube_6.1/usercube/user-guide/set-up/categorization/classification/home_rules_v602.webp)

Select the type of rule that you want to check, and find the rules you created with the right
parameters.

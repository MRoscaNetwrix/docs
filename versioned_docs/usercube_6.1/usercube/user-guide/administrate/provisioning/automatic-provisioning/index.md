# Provision Automatically

How to make Usercube automatically write to the managed systems.

## Overview

In the lifecycle of a resource (entitlement assignment, resource creation, resource update, etc.),
automated provisioning is used to minimize human intervention and trust Usercube with role model
enforcement in external systems.

### Provisioning states

In an assignment request's lifecycle, provisioning automation implies skipping the `Transmitted`
state as Usercube no longer waits for a user to make changes anymore. For this reason, an assignment
request goes through the following provisioning states:

![Provisioning State Schema](/img/versioned_docs/usercube_6.1/usercube/user-guide/administrate/provisioning/automatic-provisioning/provauto_states_v523.png)

## Participants and Artifacts

At this point, integrators should have all the elements they need to operate.

| Input                                                                                                                                                                                                                                                                                         | Output                  |
| --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------- |
| [Provisioning orders](/versioned_docs/usercube_6.1/usercube/user-guide/administrate/provisioning/provisioning-review/index.md) (required) automated provisioning [connection](/versioned_docs/usercube_6.1/usercube/user-guide/set-up/connect-system/connection-creation/index.md) (required) | Updated managed systems |

## Implement Automated Provisioning

automated provisioning is performed through a connection using a
[package](/versioned_docs/usercube_6.1/usercube/integration-guide/connectors/references-packages/index.md)
for fulfilling external systems (e.g., the
[Active Directory package](/versioned_docs/usercube_6.1/usercube/integration-guide/connectors/references-packages/active-directory/index.md)).

## Perform Automated Provisioning

There is no procedure to perform automated provisioning, for it is automatic and thus handled by
Usercube in daily jobs.

Make sure that the task used to compute and generate provisioning orders was launched after the
request (or the provisioning review, if any), through the complete job in the **Job Execution**
page.

![Home Page - Job Execution](/img/versioned_docs/usercube_6.1/usercube/user-guide/set-up/synchronization/home_jobexecution_v602.png)

## Verify Automated Provisioning

In order to verify the process:

1. Select a test user in the directory, accessible from the home page.

    ![Home Page - Directory User](/img/versioned_docs/usercube_6.1/usercube/user-guide/set-up/configure-workflows/home_directoryuser_v523.png)

2. Follow the
   [manual assignment workflow](/versioned_docs/usercube_6.1/usercube/user-guide/administrate/manual-assignment-request/index.md)
   to make a change in one of their permissions, which involves automated provisioning.
3. Perform automated provisioning and check in Usercube that the change was effectively made.

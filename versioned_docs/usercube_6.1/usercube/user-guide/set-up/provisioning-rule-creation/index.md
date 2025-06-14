# Create a Provisioning Rule

How to define [scalar rules](/versioned_docs/usercube_6.1/usercube/integration-guide/toolkit/xml-configuration/provisioning/resourcetype/index.md), [navigation rules](/versioned_docs/usercube_6.1/usercube/integration-guide/toolkit/xml-configuration/provisioning/resourcetype/index.md) and/or [query rules](/versioned_docs/usercube_6.1/usercube/integration-guide/toolkit/xml-configuration/provisioning/resourcetype/index.md) to compute and provision target resources values from source resources values.

## Overview

[Categorization](/versioned_docs/usercube_6.1/usercube/user-guide/set-up/categorization/index.md) led to the grouping of resources into resource types (classification), and the establishment of source-to-target relationships between these resources (correlation).

Sources are usually identities, and targets are usually accounts from the managed systems.

Here, we are going to compute the values of [scalar and navigation properties](/versioned_docs/usercube_6.1/usercube/user-guide/set-up/connect-system/entity-type-creation/index.md) for the target resources used in entitlement management, based on source resources. We are going to [provision](/versioned_docs/usercube_6.1/usercube/user-guide/administrate/provisioning/index.md) these properties, i.e. write them to the managed system.

The right tools for the job are provisioning rules: scalar rules, navigation rules, query rules.

These provisioning rules are designed to:

1. retrieve the input data in source objects;
2. compute the output value for target objects;
3. provision the corresponding properties in the managed system with the computation result.

Another kind of provisioning rule is called resource type rule. Instead of computing existing properties, resource type rules create automatically target resources to be owned by given source resources (identities).

In testing mode, the impacted resource types can be [configured to block provisioning](/versioned_docs/usercube_6.1/usercube/user-guide/set-up/categorization/resource-type-creation/index.md), by adding a mandatory review before actually writing to the managed system.

## Participants and Artifacts

For a given managed system, integrators may need the help of the application owner who knows the application users, entitlements and data model.

| Input | Output |
| --- | --- |
| [Categorization](/versioned_docs/usercube_6.1/usercube/user-guide/set-up/categorization/index.md) (required) | Scalar rules     Navigation rules     Query rules |

## Create Provisioning Rules

- [Create resource type rules](/versioned_docs/usercube_6.1/usercube/user-guide/set-up/provisioning-rule-creation/resource-creation/index.md) to automatically create resources.
- [Create scalar rules](/versioned_docs/usercube_6.1/usercube/user-guide/set-up/provisioning-rule-creation/scalar-property-computation/index.md) to compute scalar properties;
- [Create navigation and/or query rules](/versioned_docs/usercube_6.1/usercube/user-guide/set-up/provisioning-rule-creation/navigation-property-computation/index.md) to compute navigation properties.

NETWRIX recommends creating/modifying/deleting provisioning rules using [simulations](/versioned_docs/usercube_6.1/usercube/user-guide/optimize/simulation/index.md) in order to anticipate changes.

## Next Steps

Once provisioning rules are created, integrators can start [creating the single role catalog](/versioned_docs/usercube_6.1/usercube/user-guide/set-up/single-roles-catalog-creation/index.md).

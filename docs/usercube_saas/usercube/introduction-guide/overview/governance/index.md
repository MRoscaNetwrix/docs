# Governance

Identity Manager not only gives the right entitlements to the right identities, but also makes sure that, over time, every assignment still complies with the configured policy.

## Enforcing the Policy

By reading entitlement data from the managed systems, Identity Manager builds an exhaustive list of existing assignments for all identities in all managed systems.

Rules and roles define a policy. By definition, assignments not supported by a rule do not comply with the policy. These assignments are identified as non-conforming in order to be acted upon by knowledgeable users who can decide whether the assignment is warranted, such as security officers.

![Non-Conforming Assignments](/img/product_docs/usercube/usercube/integration-guide/role-assignment/assignments-of-entitlements/governance_nonconforming.png)

A non-conforming assignment must be reviewed in Identity Manager by a knowledgeable user, and is therefore:

- either removed if Identity Manager correctly spotted it and the owner should indeed not possess this permission;
- or kept as an exception if the configured rules do not apply to this particular case.

## Other Governance Tools

Identity Manager provides a set of governance tools to help enforce the policy, like access certification campaigns, risk management or reporting.

## Next Steps

Let's read some [
Use Case Stories
](/docs/usercube_saas/usercube/introduction-guide/overview/use-cases/index.md).

## Learn More

Learn more on [Governance](/docs/usercube_saas/usercube/integration-guide/governance/index.md).

Learn more on how to [
Generate Reports
](/docs/usercube_saas/usercube/user-guide/administrate/reporting/index.md).

Learn more on [
Perform Access Certification
](/docs/usercube_saas/usercube/user-guide/administrate/access-certification/index.md).

Learn more on how to [
Manage Risks
](/docs/usercube_saas/usercube/user-guide/optimize/risk-management/index.md).

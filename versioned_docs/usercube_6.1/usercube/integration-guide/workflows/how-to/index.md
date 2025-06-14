# How To Create a Workflow

This guide shows how to create a [workflow](/versioned_docs/usercube_6.1/usercube/integration-guide/workflows/index.md) through the XML configuration.

## Process

1. Declare a new [workflow](/versioned_docs/usercube_6.1/usercube/integration-guide/toolkit/xml-configuration/workflows/workflow/index.md) with given activities following Usercube's [activity templates](/versioned_docs/usercube_6.1/usercube/integration-guide/workflows/activity-templates/index.md).
2. Configure the input [form](/versioned_docs/usercube_6.1/usercube/integration-guide/toolkit/xml-configuration/user-interface/form/index.md) with the right output type according to the purpose of the workflow.
3. Assign the adequate permissions via an [access control rule](/versioned_docs/usercube_6.1/usercube/integration-guide/toolkit/xml-configuration/access-control/accesscontrolrule/index.md).
4. Add [menu items](/versioned_docs/usercube_6.1/usercube/integration-guide/toolkit/xml-configuration/user-interface/menuitem/index.md).
5. Add [aspects](/versioned_docs/usercube_6.1/usercube/integration-guide/toolkit/xml-configuration/workflows/aspects/index.md), according to the purpose of the workflow.
6. Add optional elements if needed: [summaries](/versioned_docs/usercube_6.1/usercube/integration-guide/workflows/index.md); a [homonym detection](/versioned_docs/usercube_6.1/usercube/integration-guide/workflows/how-to/configure-homonym-test/index.md); a [display table](/versioned_docs/usercube_6.1/usercube/integration-guide/ui/how-tos/custom-display-table/index.md) different from Usercube's default one.

## Examples

You can also find configuration examples for several types of workflow:

- #### [For Resource Creation (Mono Record)](/versioned_docs/usercube_6.1/usercube/integration-guide/workflows/how-to/workflow-create-mono/index.md)
How to create a workflow to create a new resource with a unique record.- #### [For Resource Creation (Multi Records)](/versioned_docs/usercube_6.1/usercube/integration-guide/workflows/how-to/workflow-create-multi/index.md)
How to create a workflow to create a new resource with several records.- #### [For Resource Update (No Record)](/versioned_docs/usercube_6.1/usercube/integration-guide/workflows/how-to/workflow-update-resource/index.md)
How to create a workflow to update an existing simple resource, i.e. to update, within a given existing resource, properties that do not involve records.- #### [For Resource Update (Mono Record)](/versioned_docs/usercube_6.1/usercube/integration-guide/workflows/how-to/workflow-update-mono/index.md)
How to create a workflow to schedule the replacement of the unique record of an existing resource with a new one.- #### [For Resource Update (Multi Records)](/versioned_docs/usercube_6.1/usercube/integration-guide/workflows/how-to/workflow-update-multi/index.md)
Create a workflow to update an existing resource through its several records.- #### [Configure a Homonym Detection](/versioned_docs/usercube_6.1/usercube/integration-guide/workflows/how-to/configure-homonym-test/index.md)
How to configure the homonym search that checks if a resource already exists in the system, preventing duplicates.

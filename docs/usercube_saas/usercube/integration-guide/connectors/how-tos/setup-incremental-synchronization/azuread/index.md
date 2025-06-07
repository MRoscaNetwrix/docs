# For Microsoft Entra ID

This example is about implementing incremental synchronization for a [
Microsoft Entra ID](/docs/product_docs/usercube_saas/usercube/integration-guide/connectors/references-connectors/microsoftentraid/index.md) connector (formerly Microsoft Azure AD).

## Build the Incremental Synchronization Job

Identity Manager provides a full-written job to perform incremental synchronization through the UI.

See how to launch incremental [
Synchronize Data
](/docs/product_docs/usercube_saas/usercube/user-guide/set-up/synchronization/index.md)via the UI.

> For example:
>
>                         ```
>
>                             Conf/MicrosoftEntraID/MicrosoftEntraID Jobs.xml
>
> <Job Identifier="MicrosoftEntraID_Synchronization_Delta" DisplayName_L1="10: MicrosoftEntraID - Synchronization (delta)" Agent="Local">    ...
> </Job>
>
> ```

### Components

Identity Manager provides a [Create Connector Synchro Incremental](/docs/product_docs/usercube_saas/usercube/integration-guide/toolkit/xml-configuration/configuration/scaffoldings/jobs/createconnectorsynchroincremental/index.md) scaffolding that generates the configuration for these steps.

> For example:
>
>                         ```
>
>                             Conf/MicrosoftEntraID/MicrosoftEntraID Jobs.xml
>
> <CreateConnectorSynchroIncremental Connector="MicrosoftEntraID" DisplayName_L1="MicrosoftEntraID Synchronization (delta)">  <OpenIdIdentifier Identifier="Job"/></CreateConnectorSynchroIncremental>
>
> ```
>                     
>
> Note that the ```Job``` value in ```OpenIdIdentifier``` refers to the ```ClientId``` written to the [](/docs/product_docs/usercube_saas/usercube/integration-guide/network-configuration/agent-configuration/appsettings-agent/index.md#)[appsettings.agent](/docs/product_docs/usercube_saas/usercube/integration-guide/network-configuration/agent-configuration/appsettings-agent/index.md) file. Each task will authenticate with the profile associated with this ClientId.

### Permissions for the agent

This part is not specific to a connector type, see the [
Set Up Incremental Synchronization
](/docs/product_docs/usercube_saas/usercube/integration-guide/connectors/how-tos/setup-incremental-synchronization/index.md) topic for additional information.

### Agent's authentication to the server

This part is not specific to a connector type, see the[
Set Up Incremental Synchronization
](/docs/product_docs/usercube_saas/usercube/integration-guide/connectors/how-tos/setup-incremental-synchronization/index.md) topic for additional information.

### Permissions for users

This part is not specific to a connector type, see the[
Set Up Incremental Synchronization
](/docs/product_docs/usercube_saas/usercube/integration-guide/connectors/how-tos/setup-incremental-synchronization/index.md) topic for additional information.

## Schedule the Job

Scheduling the job execution can rely either on Identity Manager's scheduler or on an external scheduler.

### Using scheduler

> The following example uses Identity Manager's scheduler to execute the ```AzureAD_Synchronization_Delta``` job every fifteen minutes:
>
>                         ```
>
>                             Conf/MicrosoftEntraID/MicrosoftEntraID Jobs.xml
>
> <Job Identifier="MicrosoftEntraID_Synchronization_Delta" CronTabExpression="*/15 * * * *" DisplayName_L1="10: MicrosoftEntraID - Synchronization (delta)" Agent="Local">   ...
> </Job>
>
> ```

### Using an external scheduler

An external scheduler relies on the[
Usercube-Invoke-Job
](/docs/product_docs/usercube_saas/usercube/integration-guide/executables/references/invoke-job/index.md).exe.

> The following command can be scheduled. It executes the ```AzureAD_Synchronization_Delta``` job using the ```Job/secret``` authentication pair to connect to the Identity Manager Server at ```http://usercube.contoso.com```:
>
>                         ```
>
> ./Usercube-Invoke-Job.exe -j "MicrosoftEntraID_Synchronization_Delta" --api-secret secret --api-client-id Job --api-url "http://usercube.contoso.com"
>
> ```

## Validate the Job

Validate the job's execution by proceeding as follows:

1. Deploy the XML configuration to the database, by using the [
   Deploy Configuration Task
   ](/docs/product_docs/usercube_saas/usercube/integration-guide/toolkit/xml-configuration/jobs/tasks/server/deployconfigurationtask/index.md).
2. In the UI, access the __Job Execution__ page from the dashboard's __Administration__ section.
3. Find the job named with the string input in the job's ```DisplayName_Li``` property, and launch it.
4. Once the job is completed, Microsoft Entra ID objects should be synchronized to the database's ```UR_Resources``` table.

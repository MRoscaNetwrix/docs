# Toolkit for XML Configuration

The Netwrix Identity Manager (formerly Usercube) configuration is a set of XML files edited
according the Usercube schema. The [ Recommendations ](/docs/identitymanager/6.2/integration-guide/toolkit/recommendations/index.md) part of this
section explains how to set up an editing environment for the configuration.

Regardless of the editing space, the configuration persists in the Netwrix Identity Manager
(formerly Usercube) database. It's this stored configuration that is used at runtime.

The
[ Deploy Configuration Task ](/docs/identitymanager/6.2/integration-guide/toolkit/xml-configuration/jobs/tasks/server/deployconfigurationtask/index.md)tool
is used to **import** a new version of the configuration (from the XML files set).
The[ Usercube-Export-Configuration ](/docs/identitymanager/6.2/integration-guide/executables/references/export-configuration/index.md) can be
used to **export** the current configuration (to a XML files set).

The Identity Manager project's integration cycle consists in developing a configuration by
successive imports in a test instance.

![Integration cycle](/img/product_docs/identitymanager/saas/integration-guide/toolkit/configurationcycle.webp)

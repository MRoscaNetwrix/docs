# Finalize the Installation

This guide shows how finalize the installation of the agent.

## Overview

This page describes the last few steps that the production agent needs for Usercube to run correctly.

## Finalize the Installation

Finalize the installation of the agent by proceeding as follows:

1. Install [Windows' hosting bundle for ASP.Net Runtime](https://dotnet.microsoft.com/en-us/download/dotnet/8.0).

   If the bundle was installed before [IIS configuration](/versioned_docs/usercube_6.1/usercube/user-guide/deploy/production-agent-installation/iis-configuration/index.md), then IIS might not display the AspNetCore module and Usercube will not run. In this case, relaunch the bundle's installation executable to perform a repair.
2. When using a proxy, [adjust the configuration accordingly](/versioned_docs/usercube_6.1/usercube/installation-guide/reverse-proxy/index.md).

## Next Steps

To continue, follow the instructions to [verify the agent's installation](/versioned_docs/usercube_6.1/usercube/user-guide/deploy/production-agent-installation/index.md).

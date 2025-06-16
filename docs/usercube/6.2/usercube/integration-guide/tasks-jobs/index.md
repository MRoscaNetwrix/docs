# Tasks & Jobs

Identity Manager provides tasks to orchestrate together the executable files that perform IGA
actions, and jobs to orchestrate the tasks together.

See the [Tasks](tasks/index.md) topic for additional information.

See the [ Jobs ](jobs/index.md) topic for additional information.

See the [ Tasks ](../toolkit/xml-configuration/jobs/tasks/index.md) topic for additional
information.

Make sure to read how to [Build Efficient Jobs](how-tos/build-efficient-jobs/index.md).

## Overview

Netwrix Identity Manager (formerly Usercube) vision for the IGA software is a customizable solution.

The main idea of Identity Manager is to offer a software solution that you can tailor to your needs
by selecting IGA "blocks" and executing them in a specific order.

This is why Identity Manager is not built as a monolithic software. It is made of a mosaic of small
[specialized services](https://en.wikipedia.org/wiki/Microservices), cohesive independent functions,
each one materialized into a building block of your Identity Manager solution. Each building block
serves a specific and well delimited IGA function.

These building blocks are called [Tasks](tasks/index.md), and can be easily organized together and
scheduled in [ Jobs ](jobs/index.md).

This approach makes for a perfectly customizable product. It also tremendously helps our users to
ease into Identity Manager by allowing them to understand it piece by piece.

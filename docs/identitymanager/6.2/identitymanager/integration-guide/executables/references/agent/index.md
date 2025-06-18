# Identity Manager-Agent

This tool runs the Agent on a separate server instance. The Agent is able to communicate with the
[Usercube-Server ](/docs/identitymanager/6.2/identitymanager/integration-guide/executables/references/server/index.md).

## Examples

With a properly configured environment, the following command runs the agent. It listens on two
different ports:

```
./identitymanager-Agent.exe --urls "http://localhost:6001;http://localhost:6002"
```

When the Agent starts, the following log should be displayed (if the log level is set to
_Information_):

```
[xx:xx:xx INF] Now listening on: http://localhost:6001
[xx:xx:xx INF] Now listening on: http://localhost:6002

```

## Arguments

| Argument Name   | Details                                                                |
| --------------- | ---------------------------------------------------------------------- |
| --urls required | **Type** String **Description** URL(s) that the agent is listening to. |

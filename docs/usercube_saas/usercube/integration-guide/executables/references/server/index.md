# Usercube-Server

This tool runs the main Identity Manager Server.

## Examples

With a properly configured environment, the following command runs the server. It listens on two different ports:

```
./Usercube-Server.exe --urls "http://localhost:5000;http://localhost:5001"
```

When the Server starts, the following log should be displayed (if the log level is set to _Information_):

```
[xx:xx:xx INF] Now listening on: http://localhost:5000
[xx:xx:xx INF] Now listening on: http://localhost:5001

```

## Arguments

| Argument Name | Details |
| --- | --- |
| --urls   required | __Type__    String   __Description__ URL(s) that the server is listening to. |

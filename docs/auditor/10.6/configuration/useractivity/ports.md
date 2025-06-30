# User Activity Ports

Review a full list of protocols and ports required for monitoring User Activity.

- Allow outbound connections from the dynamic (1024 - 65535) local port on the computer where
  Netwrix Auditor Server resides.
- Allow outbound connections to remote ports on the source and inbound connections to local ports on
  the target.

Tip for reading the table: For example, on any monitored computer (source), allow outbound
connections to remote 9004 TCP port. On the computer where Netwrix Auditor Server resides (target),
allow inbound connections to local 9004 TCP port.

| Port                 | Protocol | Source                 | Target                 | Purpose                                                                 |
| -------------------- | -------- | ---------------------- | ---------------------- | ----------------------------------------------------------------------- |
| 9004                 | TCP      | Monitored computer     | Netwrix Auditor Server | Core Service communications                                             |
| 9003                 | TCP      | Netwrix Auditor Server | Monitored computer     | Core Service communications                                             |
| 139 445              | TCP      | Netwrix Auditor Server | Monitored computer     | Service Control Manager Remote Protocol (RPC) Remote registry           |
| Dynamic: 1024 -65535 | TCP      | Netwrix Auditor Server | Monitored computer     | Windows Management Instrumentation                                      |
| 135                  | TCP      | Netwrix Auditor Server | Monitored computer     | Service Control Manager Remote Protocol (RPC) Core Service installation |
| 137 through 139      | UDP      | Netwrix Auditor Server | Monitored computer     | Service Control Manager Remote Protocol (RPC) Core Service installation |
| 445                  | TCP      | Netwrix Auditor Server | Monitored computer     | SMB 2.0/3.0 Video files copy                                            |
| –                    | ICMP     | Netwrix Auditor Server | Monitored computer     | Core Service communications                                             |

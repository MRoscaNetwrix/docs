# Linux Agent Server Requirements

The server where the agent is deployed can be physical or virtual. The supported operating systems
are:

- Red Hat Enterprise Linux

  - V 9.x
  - V 8.x

- Activity Monitor supports RHEL kernels in FIPS mode compliant with FIPS 140-2 and FIPS 140-3.

## Target Requirements

**NOTE:** For monitoring a Linux file server, the The Linux Agent is deployed to Linux servers to be
monitored. It cannot be deployed to a proxy server.

## Supported Protocols

The following protocols are supported for the Linux agent:

- Local
- Common Internet File System (CIFS) / Server Message Block (SMB)
- Network File System (Mounted Client-Side)

**NOTE:** Server-Side NFS protocol is not supported.

## Permissions for Installation

The following permission is required by the account used to install and manage the agent:

- Root privileges with password (or SSH private key)

For integration between the Activity Monitor and Enterprise Auditor, the credential used by
Enterprise Auditor to read the activity log files must have also have this permission.

## Immutable Mode

For file activity monitoring on Linux, Activity Monitor relies on **auditd** component of the Linux
Auditing System. One of the features of auditd is the **immutable mode** or `-e 2` command, which
locks the audit configuration and protects it from being changed. When the immutable mode is
enabled, the only way to change the auditing configuration is to reboot the server.

To check if the immutable mode is enabled, use the `auditctl -s` command. If the immutable mode is
active, the command will print `enabled 2`. Alternatively, check for the `-e 2` line in the
`/etc/audit/rules.d/audit.rules` file.

Activity Monitor supports the immutable mode. It compares the current auditd configuration with the
desired one. If they differ and the immutable mode is enabled, the product displays a warning that a
server restart is required in the status section of the **Monitored Hosts** tab. After the reboot,
the changes take effect and the immutable mode is enabled.

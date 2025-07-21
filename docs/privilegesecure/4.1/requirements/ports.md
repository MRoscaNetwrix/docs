---
title: "Ports Requirements"
description: "Ports Requirements"
sidebar_position: 50
---

# Ports Requirements

Configure appropriate firewall rules to allow these connections to Privilege Secure.

## Application Server Firewall Rules

The requirements for the (Privilege Secure) application server are:

- Make sure that you have configured the Antivirus exclusions according to the following Netwrix
  knowledge base article:
  [SbPAM: Exclusions for Antivirus (AV) & Endpoint Software](https://kb.netwrix.com/5938)
- The following ports must be open for communication between Privilege Secure and Active Directory
  domain controllers:

| Port     | Protocol | Source                  | Direction                                                                                                                                   | Target            | Purpose                                                                                                                                                                                                                                                      |
| -------- | -------- | ----------------------- | ------------------------------------------------------------------------------------------------------------------------------------------- | ----------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| 135      | TCP      | Privilege Secure server | ![arrow](/img/product_docs/privilegesecure/4.1/accessmanagement/requirements/arrow.webp)                                                    | Domain Controller | MS-RPC                                                                                                                                                                                                                                                       |
| 389 636  | TCP UDP  | Privilege Secure server | ![arrow](/img/product_docs/privilegesecure/4.1/accessmanagement/requirements/arrow.webp)                                                    | Domain Controller | LDAP/LDAPS                                                                                                                                                                                                                                                   |
| 53       | TCP UDP  | Privilege Secure server | ![arrow](/img/product_docs/privilegesecure/4.1/accessmanagement/requirements/arrow.webp)                                                    | DNS Service       | DNS                                                                                                                                                                                                                                                          |
| 137 138  | UDP      | Privilege Secure server | ![arrow](/img/product_docs/privilegesecure/4.1/accessmanagement/requirements/arrow.webp)                                                    | Domain Controller | Net BIOS related                                                                                                                                                                                                                                             |
| **9389** | TCP      | Privilege Secure server | ![single_direction_arrow](/img/product_docs/privilegesecure/4.1/accessmanagement/requirements/single_direction_arrow.webp)                  | Domain Controller | Active Directory Web Services <br />**NOTE:** Make sure that you have configured the Antivirus exclusions according to the following Netwrix knowledge base article: [SbPAM: Exclusions for Antivirus (AV) & Endpoint Software](https://kb.netwrix.com/5938) |
| **88**   | UDP      | Privilege Secure server | ![arrow](/img/product_docs/privilegesecure/4.1/accessmanagement/requirements/arrow.webp)                                                    | Domain Controller | Kerberos                                                                                                                                                                                                                                                     |


:::note
Privilege Secure must be able to reach the following URLs via HTTPS (port 443)
:::


- https://login.microsoftonline.com
- https://graph.microsoft.com

## Proxy Firewall Rules

The following ports must be open for communication between the proxy and Privilege Secure.

**Proxy Server Sizing for Windows/Linux/Docker**

| Administrators | Concurrent Sessions | Memory | CPU Cores | Disk (max)    |
| -------------- | ------------------- | ------ | --------- | ------------- |
| 450            | 150                 | 16 GB  | 4 cores   | 21 GB per day |
| 900            | 300                 | 32 GB  | 8 cores   | 42 GB per day |
| 1800           | 600                 | 64 GB  | 16 cores  | 84 G per day  |

**Additional Considerations**

The following ports must be open for communication between the Client and Privilege Secure:

| Port | Protocol | Source     | Direction                                                                                                 | Target       | Purpose   |
| ---- | -------- | ---------- | --------------------------------------------------------------------------------------------------------- | ------------ | --------- |
| 4422 | TCP      | SSH Client | ![arrow](/img/product_docs/privilegesecure/4.1/accessmanagement/requirements/arrow.webp) | SbPAM server | SSH Proxy |
| 4489 | TCP      | RDP Client | ![arrow](/img/product_docs/privilegesecure/4.1/accessmanagement/requirements/arrow.webp) | SbPAM server | RDP Proxy |

## Target Environment Firewall Rules

The following ports must be open for communication between Privilege Secure and the platform:

| Port      | Protocol    | Source                  | Direction                                                                                                                                   | Target                | Purpose                                 |
| --------- | ----------- | ----------------------- | ------------------------------------------------------------------------------------------------------------------------------------------- | --------------------- | --------------------------------------- |
| 3389      | TCP         | Privilege Secure server | ![arrow](/img/product_docs/privilegesecure/4.1/accessmanagement/requirements/arrow.webp)                                   | Windows Hosts         | RDP Proxy                               |
| 5985 5986 | TCP         | Privilege Secure server | ![arrow](/img/product_docs/privilegesecure/4.1/accessmanagement/requirements/arrow.webp)                                   | Windows Hosts         | PowerShell remoting                     |
| 5985 5986 | TCP         | Privilege Secure server | ![arrow](/img/product_docs/privilegesecure/4.1/accessmanagement/requirements/arrow.webp)                                   | Windows Hosts         | Password Change via Powershell Remoting |
| 22        | TCP         | Privilege Secure server | ![single_direction_arrow](/img/product_docs/privilegesecure/4.1/accessmanagement/requirements/single_direction_arrow.webp) | Linux Hosts           | SSH Proxy / Password change             |
| 6520      | TCP         | Privilege Secure server | ![arrow](/img/product_docs/privilegesecure/4.1/accessmanagement/requirements/arrow.webp)                                   | Remote Proxy          | Register Proxy Service                  |
| 6500      | TCP         | Privilege Secure server | ![arrow](/img/product_docs/privilegesecure/4.1/accessmanagement/requirements/arrow.webp)                                   | Remote Action Service | Register Action Service                 |
| **443**   | HTTPS (TCP) | Privilege Secure Server | ![arrow](/img/product_docs/privilegesecure/4.1/accessmanagement/requirements/arrow.webp)                                   | Azure                 | Azure Graph API Access                  |

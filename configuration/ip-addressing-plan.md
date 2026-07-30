# IP Addressing Plan

## Overview

This document defines the IPv4 addressing scheme used within the Secure Enterprise Network Lab.

The laboratory uses a dedicated **10.10.10.0/24** private subnet with statically assigned IPv4 addresses for all virtual machines. Static addressing provides predictable infrastructure management, simplifies troubleshooting, and supports future Active Directory, security monitoring, and compliance activities.

---

## Network Configuration

| Setting | Value |
| -------- | ----- |
| Network Address | 10.10.10.0/24 |
| Network Type | Host-Only |
| Default Gateway | None |
| DNS Server | 10.10.10.10 (AU-SYD-DC01) |
| Active Directory Domain | banking.lab |

---

## IP Address Allocation

| IP Address | Hostname | Primary Function |
| ---------- | -------- | ---------------- |
| 10.10.10.10 | AU-SYD-DC01 | Domain Controller (DNS / Active Directory) |
| 10.10.10.20 | au-syd-siem01 | Linux Security Monitoring Server |
| 10.10.10.30 | AU-SYD-W101 | Corporate Workstation |
| 10.10.10.40 | au-syd-secops01 | Offensive Security Workstation |

---

## Address Allocation Strategy

The IPv4 address space is organised according to infrastructure role to simplify future expansion and asset management.

| Address Range | Planned Use |
| ------------- | ----------- |
| 10.10.10.1–9 | Reserved Infrastructure |
| 10.10.10.10–19 | Core Infrastructure Servers |
| 10.10.10.20–29 | Linux Servers |
| 10.10.10.30–39 | Windows Workstations |
| 10.10.10.40–49 | Security Operations Platforms |
| 10.10.10.50–254 | Future Expansion |

---

## Design Considerations

The addressing scheme was designed to support enterprise infrastructure management by:

- Using static IPv4 addresses for all virtual machines.
- Grouping systems by functional role.
- Reserving capacity for future infrastructure growth.
- Simplifying network documentation and troubleshooting.
- Supporting future Active Directory, SIEM, and compliance projects without requiring address reallocation.

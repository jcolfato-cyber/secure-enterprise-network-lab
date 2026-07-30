# Hostname Convention

## Overview

This document defines the hostname convention used throughout the Secure Enterprise Network Lab.

A consistent hostname standard simplifies infrastructure administration, asset identification, documentation, troubleshooting, and future security monitoring. It also establishes a scalable naming framework that can be reused across future enterprise cybersecurity projects within this portfolio.

---

## Naming Standard

All virtual machines follow the naming format:

`<country>-<city>-<system-role><number>`

Example:

`AU-SYD-DC01`

> **Note**
>
> The hostname structure is consistent across all virtual machines. Windows systems are displayed in uppercase (for example, `AU-SYD-DC01`), while Linux systems use lowercase hostnames (for example, `au-syd-siem01`) in accordance with common operating system conventions.

---

## Naming Components

| Component | Meaning | Example |
| --------- | ------- | ------- |
| AU | Country | Australia |
| SYD | City | Sydney |
| DC | Domain Controller | AU-SYD-DC01 |
| W | Windows Workstation | AU-SYD-W101 |
| SIEM | Security Monitoring Server | au-syd-siem01 |
| SECOPS | Offensive Security Platform | au-syd-secops01 |
| 01 | Instance Number | First deployment |

---

## Current Host Inventory

| Hostname | Operating System | Primary Role |
| -------- | ---------------- | ------------ |
| AU-SYD-DC01 | Windows Server 2022 | Domain Controller |
| AU-SYD-W101 | Windows 11 Pro | Corporate Workstation |
| au-syd-siem01 | Ubuntu Server 24.04 LTS | Linux Security Monitoring Server |
| au-syd-secops01 | Kali Linux ARM64 | Offensive Security Workstation |

---

## Design Considerations

The hostname convention supports:

- Consistent asset identification
- Simplified infrastructure documentation
- Enterprise-style system administration
- Predictable asset naming for future expansion
- Compatibility with Active Directory computer naming practices
- Improved correlation of infrastructure, documentation, and validation evidence

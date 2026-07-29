# Validation Report

## Overview

This document provides validation evidence for the Secure Enterprise Network Lab following completion of the baseline infrastructure deployment.

The purpose of this validation process was to confirm that all virtual machines were correctly deployed, configured, isolated within the host-only network, and operating according to their intended enterprise roles.

Validation activities covered:

- Virtual machine network configuration
- Static IP assignment
- Hostname verification
- Operating system validation
- Active Directory functionality
- DNS functionality
- Internal network communication
- Service availability
- Baseline system readiness

---

## Validation Scope

The validation process covered the following four virtual machines:

| Hostname | Operating System | Primary Function | IP Address |
| ---------- | ---------------- | ---------------- | ---------- |
| AU-SYD-DC01 | Windows Server 2022 | Domain Controller / DNS | 10.10.10.10 |
| au-syd-siem01 | Ubuntu Server 24.04 LTS | Security Monitoring Server | 10.10.10.20 |
| AU-SYD-W101 | Windows 11 Pro | Corporate Workstation | 10.10.10.30 |
| au-syd-secops01 | Kali Linux ARM64 | Offensive Security Workstation | 10.10.10.40 |

---

## Network Validation

### Host-Only Network Verification

The UTM virtual network configuration was validated to confirm that all virtual machines operate within the isolated laboratory segment.

| Validation Item | Expected Result | Status |
| --- | --- | --- |
| Network Type | Host-Only | Completed |
| Network Range | 10.10.10.0/24 | Completed |
| Default Gateway | None | Completed |
| External Connectivity | Disabled | Completed |

The isolated network design ensures that laboratory systems communicate internally without exposure to external production networks.

---

## Windows Server 2022 Validation

### AU-SYD-DC01

| Validation Item | Result |
| --- | --- |
| Hostname | AU-SYD-DC01 |
| Operating System | Windows Server 2022 |
| IP Address | 10.10.10.10 |
| Domain | banking.lab |
| AD DS Role | Installed |
| DNS Role | Installed |

Validation completed:

- Active Directory Domain Services installation confirmed.
- Domain Controller status verified.
- DNS functionality validated.
- Domain health checks completed.
- Active Directory Users and Computers accessibility confirmed.

Evidence location: [Windows Server 2022 AU-SYD-DC01 Validation Evidence](../screenshots/windows-server-2022-dc01/)

---

## Windows 11 Pro Validation

### AU-SYD-W101

| Validation Item | Result |
| --- | --- |
| Hostname | AU-SYD-W101 |
| Operating System | Windows 11 Pro |
| IP Address | 10.10.10.30 |
| Domain Membership | banking.lab |

Validation completed:

- Static IP configuration verified.
- Network communication with Domain Controller confirmed.
- Domain join completed successfully.
- Computer object visible within Active Directory.

Evidence location: [Windows 11 Pro AU-SYD-W101 Validation Evidence](../screenshots/windows-11-pro-w101/)

---

## Ubuntu Server Validation

### au-syd-siem01

| Validation Item | Result |
| --- | --- |
| Hostname | au-syd-siem01 |
| Operating System | Ubuntu Server 24.04 LTS |
| Architecture | ARM64 |
| IP Address | 10.10.10.20 |

Validation completed:

- Hostname verification completed.
- Static IP configuration validated.
- Connectivity with Domain Controller confirmed.
- System updates completed.
- SSH service validated.

Evidence location: [Ubuntu Server au-syd-siem01 Validation Evidence](../screenshots/ubuntu-siem01/)

---

## Kali Linux Validation

### au-syd-secops01

| Validation Item | Result |
| --- | --- |
| Hostname | au-syd-secops01 |
| Operating System | Kali Linux ARM64 |
| IP Address | 10.10.10.40 |

Validation completed:

- Hostname verification completed.
- Static IP configuration validated.
- System information verified.
- Package updates completed.
- QEMU Guest Agent validated.
- Internal network connectivity confirmed.

Evidence location: [Kali Linux au-syd-secops01 Validation Evidence](../screenshots/kali-linux-secops01/)

---

## Connectivity Validation

Internal communication testing was performed between laboratory systems.

### Validation Results

| Source | Destination | Result |
| --- | --- | --- |
| Kali Linux | AU-SYD-DC01 | Successful |
| Kali Linux | au-syd-siem01 | Successful |
| Kali Linux | AU-SYD-W101 | Successful |
| Ubuntu Server | AU-SYD-DC01 | Successful |
| Windows 11 | AU-SYD-DC01 | Successful |

All systems successfully communicated within the isolated 10.10.10.0/24 network.

---

## Service Validation

| Service | System | Status |
| --- | --- | --- |
| Active Directory Domain Services | AU-SYD-DC01 | Operational |
| DNS | AU-SYD-DC01 | Operational |
| SSH | au-syd-siem01 | Operational |
| QEMU Guest Agent | au-syd-secops01 | Operational |

---

## Baseline Readiness Assessment

Following validation, the environment was assessed against the requirements for future cybersecurity projects.

| Requirement | Status |
| --- | --- |
| Enterprise network foundation | Completed |
| Identity infrastructure foundation | Completed |
| Endpoint workstation deployment | Completed |
| Security monitoring platform foundation | Completed |
| Security testing platform foundation | Completed |
| Documentation evidence collection | Completed |

---

## Validation Outcome

The Secure Enterprise Network Lab has successfully completed baseline infrastructure validation.

The environment is now ready to support progressive enterprise security implementations including:

- Enterprise Banking IAM Architecture
- Governance, Risk & Compliance Assessment
- Cloud Security Hardening
- Microsoft Sentinel Security Monitoring

The completed validation establishes a stable and repeatable infrastructure baseline for continued cybersecurity portfolio development.

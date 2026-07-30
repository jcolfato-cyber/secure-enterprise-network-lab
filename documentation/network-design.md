# Network Design

## Overview

The Secure Enterprise Network Lab is designed as an isolated enterprise-style security environment to provide a controlled foundation for future cybersecurity projects.

The network architecture simulates a corporate banking security environment using a dedicated private IPv4 subnet hosted within UTM/QEMU. The design prioritises network isolation, predictable addressing, infrastructure validation, and future scalability for Identity & Access Management (IAM), Governance Risk & Compliance (GRC), Cloud Security, and Security Operations projects.

The laboratory uses a dedicated **10.10.10.0/24 host-only network** to allow communication between virtual machines while preventing direct connectivity to external networks after initial operating system provisioning.

---

## Network Architecture Principles

The laboratory design follows several core infrastructure principles:

### Network Isolation

The environment operates on an isolated host-only network within UTM.

Benefits:

- Prevents accidental exposure to external networks.
- Provides a safe environment for security testing.
- Allows controlled communication between laboratory systems.
- Supports repeatable cybersecurity validation activities.

---

### Static Address Management

All virtual machines use manually assigned static IP addresses.

Benefits:

- Predictable asset identification.
- Simplified troubleshooting.
- Consistent documentation.
- Easier integration with future security monitoring solutions.

---

### Enterprise Asset Naming Convention

All virtual machines follow a corporate-style hostname convention.

Format: `<country>-<city>-<system-role><number>`

Examples:

- AU-SYD-DC01
- AU-SYD-W101
- au-syd-siem01
- au-syd-secops01

The naming convention provides clear identification of:

- Geographic location
- System function
- Asset purpose

---

## Network Topology

The environment consists of four virtual machines operating within a single isolated security laboratory segment.

![Enterprise Network Topology](../diagrams/enterprise-network-topology.png)

---

## Network Segmentation Design

The laboratory uses a single private network segment:

| Network Segment | Purpose |
| --- | --- |
| 10.10.10.0/24 | Isolated enterprise security laboratory |

The subnet contains infrastructure components representing common enterprise security functions:

| Function | System |
| ---------- | -------- |
| Identity Infrastructure | Windows Server 2022 Domain Controller |
| Security Monitoring | Ubuntu Server 24.04 LTS |
| Corporate Endpoint | Windows 11 Pro Workstation |
| Security Testing | Kali Linux ARM64 |

Although the environment uses a single subnet, logical separation is maintained through:

- Role-based system design.
- Controlled administrative access.
- Future IAM implementation.
- Future security monitoring integration.

---

## IP Addressing Scheme

The laboratory uses the following static IPv4 allocation model:

| Hostname | Operating System | IP Address | Primary Function |
| ---------- | ------------------ | ------------ | ------------------ |
| AU-SYD-DC01 | Windows Server 2022 | 10.10.10.10 | Domain Controller (DNS / Active Directory) |
| au-syd-siem01 | Ubuntu Server 24.04 LTS | 10.10.10.20 | Security Monitoring Server |
| AU-SYD-W101 | Windows 11 Pro | 10.10.10.30 | Corporate Workstation |
| au-syd-secops01 | Kali Linux ARM64 | 10.10.10.40 | Offensive Security Workstation |

All virtual machines use static IPv4 addressing to provide consistent asset identification, simplify troubleshooting, and support future security monitoring and Active Directory services.

---

## Virtual Machine Network Allocation

### AU-SYD-DC01

| Configuration | Value |
| -------------- | ------- |
| Operating System | Windows Server 2022 |
| IP Address | 10.10.10.10 |
| Network Role | Domain Controller |
| Services | Active Directory Domain Services, DNS |
| Domain | banking.lab |

The domain controller hosts the banking.lab Active Directory domain and provides the identity foundation for future IAM architecture development.

---

### au-syd-siem01

| Configuration | Value |
| -------------- | ------- |
| Operating System | Ubuntu Server 24.04 LTS |
| IP Address | 10.10.10.20 |
| Network Role | Security Monitoring Server |

This system provides the Linux foundation for future logging, monitoring, and SIEM integration.

---

### AU-SYD-W101

| Configuration | Value |
| -------------- | ------- |
| Operating System | Windows 11 Pro |
| IP Address | 10.10.10.30 |
| Network Role | Corporate Workstation |

This endpoint represents a standard enterprise user workstation for future security testing and endpoint validation.

---

### au-syd-secops01

| Configuration | Value |
| -------------- | ------- |
| Operating System | Kali Linux ARM64 |
| IP Address | 10.10.10.40 |
| Network Role | Offensive Security Workstation |

This system provides controlled security testing capability for vulnerability assessment and defensive validation activities.

---

## Host-Only Network Configuration

The UTM virtual network was configured using host-only networking.

Configuration:

| Setting | Value |
| --------- | ------- |
| Network Mode | Host Only |
| Network Address | 10.10.10.0/24 |
| Default Gateway | None |
| Internet Access | Disabled after initial provisioning |
| External Connectivity | Not Available |

The absence of a gateway ensures that the laboratory remains isolated from external networks after initial system provisioning.

---

## Security Design Considerations

The network architecture incorporates several security design considerations:

### Reduced Attack Surface

The isolated network prevents unnecessary exposure of laboratory systems.

### Controlled Communication

Only authorised laboratory assets can communicate within the private subnet.

### Predictable Asset Identification

Static addressing and naming conventions simplify monitoring and investigation activities.

### Planned Security Controls

The design provides a foundation for implementing:

- Active Directory security controls.
- Role-Based Access Control (RBAC).
- Security monitoring.
- Vulnerability assessment.
- Compliance assessments.

---

## Future Expansion Capability

The current network architecture was intentionally designed to support future portfolio projects.

Planned integrations include:

| Future Project | Network Dependency |
| ---------------- | ------------------- |
| Enterprise Banking IAM Architecture | Active Directory domain expansion |
| Enterprise Banking GRC Assessment | Infrastructure security assessment |
| Cloud Banking Infrastructure Hardening | Secure cloud identity and workload integration concepts |
| Enterprise Banking SIEM Sentinel | Endpoint and server telemetry collection |

The current 10.10.10.0/24 subnet provides sufficient capacity for additional security infrastructure components while maintaining a controlled enterprise laboratory environment.

This network design intentionally separates infrastructure deployment from higher-level security projects. Future repositories build progressively on this environment by introducing enterprise identity services, governance and compliance assessments, cloud security controls, and security monitoring capabilities without requiring changes to the underlying laboratory architecture.

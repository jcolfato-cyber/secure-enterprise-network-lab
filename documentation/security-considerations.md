# Security Considerations

## Overview

This document describes the security design considerations applied during the development of the Secure Enterprise Network Lab.

The laboratory was designed as an isolated enterprise-style security environment that provides a controlled foundation for future Identity and Access Management (IAM), Governance Risk & Compliance (GRC), Cloud Security, and Security Operations projects.

Security decisions within this environment prioritise isolation, controlled communication, predictable asset management, and repeatable validation.

---

## Network Isolation

The laboratory operates using a dedicated UTM host-only network:

| Configuration | Value |
| --- | --- |
| Network Type | Host-Only |
| Network Range | 10.10.10.0/24 |
| Default Gateway | None |
| External Connectivity | Disabled after provisioning |

The isolated network design provides several security benefits:

- Prevents accidental exposure to external networks.
- Allows controlled security testing activities.
- Provides a safe environment for infrastructure experimentation.
- Reduces the risk of unintended interaction with production systems.

All communication occurs only between approved laboratory virtual machines within the private subnet.

---

## Identity and Access Foundation

Windows Server 2022 operates as the identity infrastructure foundation for the laboratory.

Implemented services:

- Active Directory Domain Services (AD DS)
- Domain Name System (DNS)
- banking.lab Active Directory domain

The current deployment establishes the foundational identity infrastructure required for future security enhancements, including:

- Role-Based Access Control (RBAC)
- Least privilege administration
- Tiered administrative architecture
- Group Policy security controls

These controls will be implemented during the Enterprise Banking IAM Architecture project.

---

## Endpoint Security Considerations

The laboratory contains multiple endpoint types representing common enterprise assets:

| System | Security Purpose |
| --- | --- |
| AU-SYD-DC01 | Identity infrastructure |
| AU-SYD-W101 | Corporate user endpoint |
| au-syd-siem01 | Security monitoring foundation |
| au-syd-secops01 | Security testing platform |

Each system uses a dedicated hostname and static IP address to support:

- Asset identification
- Documentation accuracy
- Future monitoring integration
- Security investigation workflows

---

## Administrative Access Model

Administrative access is currently managed using local administrative accounts on each virtual machine.

The current architecture provides the foundation for future implementation of:

- Dedicated administrative accounts
- Privileged access separation
- Role-based permissions
- Enterprise identity governance

A formal privileged access model will be introduced during the Enterprise Banking IAM Architecture project.

---

## Security Testing Environment

The Kali Linux security operations platform provides a controlled environment for security validation activities.

The system is isolated within the laboratory network and is intended for:

- Vulnerability assessment exercises
- Security control validation
- Defensive security testing
- Future penetration testing simulations

All testing activities are performed within the isolated laboratory environment.

---

## Current Security Limitations

The current baseline deployment intentionally focuses on infrastructure availability and network architecture.

The following security controls have not yet been implemented:

- Multi-factor authentication
- Privileged Access Management (PAM)
- Endpoint Detection and Response (EDR)
- Centralised security monitoring
- Vulnerability management platform
- Formal compliance assessment
- Security hardening baselines

These controls will be introduced progressively through future portfolio projects.

---

## Future Security Enhancements

The laboratory architecture has been designed to support progressive security maturity improvements.

Planned enhancements include:

| Future Project | Security Enhancement |
| --- | --- |
| Enterprise Banking IAM Architecture | RBAC, Tiered Administration, Group Policy security controls |
| Enterprise Banking GRC Assessment | ACSC Essential Eight, APRA CPS 234, ISO 27001 assessment |
| Cloud Banking Infrastructure Hardening | AWS security controls and CIS Benchmark implementation |
| Enterprise Banking SIEM Sentinel | Centralised logging, detection engineering and security monitoring |

---

## Security Architecture Alignment

The Secure Enterprise Network Lab has been designed in accordance with widely adopted enterprise security principles, including:

- Network segmentation
- Least privilege principles
- Defence in depth
- Secure infrastructure design
- Asset visibility
- Continuous validation

This baseline environment provides the infrastructure foundation required for future enterprise cybersecurity implementations.

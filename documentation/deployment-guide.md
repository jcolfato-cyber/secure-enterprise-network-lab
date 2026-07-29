# Deployment Guide

## Overview

This document describes the deployment methodology used to build the Secure Enterprise Network Lab.

The environment was deployed using UTM (QEMU) on an Apple Silicon MacBook Pro and consists of four virtual machines operating within an isolated host-only network. The deployment establishes the foundational infrastructure required for future Identity and Access Management (IAM), Governance, Risk and Compliance (GRC), Cloud Security, and Security Operations projects.

The deployment followed a phased approach to ensure that each system was configured, validated, and documented before progressing to the next stage.

---

## Deployment Objectives

The primary objectives of the deployment were to:

- Build a reusable enterprise virtual laboratory.
- Deploy four enterprise operating systems within an isolated network.
- Configure consistent hostname and IP addressing standards.
- Establish the banking.lab Active Directory domain.
- Validate communication between all virtual machines.
- Produce a repeatable baseline suitable for future security projects.

---

## Host Environment

| Component | Specification |
| ---------- | --------------- |
| Host Device | Apple MacBook Pro M4 |
| Host Operating System | macOS Sequoia |
| Hypervisor | UTM |
| Virtualisation Engine | QEMU |
| Guest Architecture | ARM64 |

---

## Laboratory Architecture

The laboratory consists of four virtual machines deployed within a dedicated host-only network.

| Hostname | Operating System | Role | IP Address |
| ---------- | ------------------ | ------ | ------------ |
| AU-SYD-DC01 | Windows Server 2022 | Domain Controller (DNS / Active Directory) | 10.10.10.10 |
| au-syd-siem01 | Ubuntu Server 24.04 LTS | Security Monitoring Server | 10.10.10.20 |
| AU-SYD-W101 | Windows 11 Pro | Corporate Workstation | 10.10.10.30 |
| au-syd-secops01 | Kali Linux ARM64 | Offensive Security Workstation | 10.10.10.40 |

---

## Deployment Sequence

The environment was deployed using the following implementation order.

### Phase 1 – Virtual Machine Provisioning

Four ARM64-compatible virtual machines were created within UTM using the QEMU virtualisation engine.

Each virtual machine was allocated appropriate CPU, memory, storage, and network resources according to its intended enterprise role.

---

### Phase 2 – Operating System Installation

Each operating system was installed individually.

Installed operating systems included:

- Windows Server 2022
- Windows 11 Pro
- Ubuntu Server 24.04 LTS
- Kali Linux ARM64

Following installation, each operating system was updated to the latest available baseline before further configuration, including Windows Update for Microsoft operating systems and package updates for Linux systems.

---

### Phase 3 – Network Configuration

Following initial provisioning, each virtual machine was reconfigured to use the dedicated host-only laboratory network.

Configuration activities included:

- Static IPv4 addressing
- Hostname assignment
- Network validation
- Internal connectivity testing

The laboratory operates entirely within the 10.10.10.0/24 private subnet.

---

### Phase 4 – Active Directory Deployment

Windows Server 2022 was promoted to the primary Domain Controller for the banking.lab domain.

Core services deployed included:

- Active Directory Domain Services (AD DS)
- Domain Name System (DNS)

The Domain Controller provides the identity foundation for future enterprise IAM projects.

---

### Phase 5 – System Validation

Following deployment, each system underwent validation to confirm:

- Correct hostname
- Static IP configuration
- Network communication
- Operating system health
- Service availability

Ubuntu Server additionally underwent:

- Package update verification
- SSH service validation
- Static IP validation

Kali Linux additionally underwent:

- Package update verification
- QEMU Guest Agent validation

---

## Network Configuration Standards

The laboratory follows a consistent enterprise addressing standard.

| Configuration | Value |
| -------------- | ------- |
| Network Type | Host-Only |
| IPv4 Network | 10.10.10.0/24 |
| Default Gateway | None |
| DNS Server | AU-SYD-DC01 |
| Domain | banking.lab |

The absence of a default gateway ensures that the environment remains isolated from external networks following initial provisioning.

---

## Enterprise Configuration Standards

The deployment follows several standardisation principles.

### Host Naming

Enterprise-style hostnames are used throughout the environment.

Examples include:

- AU-SYD-DC01
- AU-SYD-W101
- au-syd-siem01
- au-syd-secops01

---

### Static Addressing

Every virtual machine uses a permanently assigned IPv4 address.

This improves:

- Infrastructure documentation
- Asset identification
- Network troubleshooting
- Future monitoring

---

### Platform Roles

Each operating system performs a dedicated enterprise function.

| Platform | Responsibility |
| ---------- | ---------------- |
| Windows Server 2022 | Identity Infrastructure |
| Windows 11 Pro | Corporate Endpoint |
| Ubuntu Server | Security Monitoring |
| Kali Linux | Security Operations |

---

## Baseline Snapshot

Following successful deployment and validation, a complete baseline snapshot and backup of all four virtual machines was created.

This snapshot serves as the recovery point for subsequent portfolio projects, ensuring that future implementations can be tested without rebuilding the core infrastructure.

---

## Deployment Outcome

The deployment successfully established a reusable enterprise security laboratory capable of supporting future projects involving:

- Enterprise Identity and Access Management
- Governance, Risk and Compliance
- Cloud Security
- Microsoft Sentinel
- Security Operations
- Vulnerability Assessment
- Defensive Security Validation

### Deployment Status

| Component | Status |
| ---------- | ---------------- |
| Virtual Machine Deployment | Completed |
| Static IP Configuration | Completed |
| Host-Only Network Configuration | Completed |
| Active Directory Deployment | Completed |
| DNS Configuration | Completed |
| Operating System Updates | Completed |
| Connectivity Validation | Completed |
| Baseline Snapshot | Completed |

The completed environment forms the foundational infrastructure for the subsequent repositories within the enterprise banking cybersecurity portfolio.

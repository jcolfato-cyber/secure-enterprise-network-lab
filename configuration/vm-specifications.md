# Virtual Machine Specifications

## Overview

This document records the baseline virtual machine specifications for the Secure Enterprise Network Lab.

The environment consists of four virtual machines deployed within UTM (QEMU) to simulate a small enterprise banking infrastructure. The specifications documented here establish the baseline configuration for all subsequent portfolio projects.

---

## Virtual Machine Inventory

| Hostname | Operating System | vCPU | Memory | Storage | Architecture | Network | Primary Role |
| -------- | ---------------- | ----: | ------: | -------: | ------------ | -------- | ------------ |
| AU-SYD-DC01 | Windows Server 2022 | 4 | 6 GB | 80 GB | x86_64 | Host-Only | Domain Controller |
| AU-SYD-W101 | Windows 11 Pro | 4 | 6 GB | 80 GB | ARM64 (aarch64) | Host-Only | Corporate Workstation |
| au-syd-siem01 | Ubuntu Server 24.04 LTS | 2 | 4 GB | 64 GB | ARM64 (aarch64) | Host-Only | Linux Security Monitoring Server |
| au-syd-secops01 | Kali Linux ARM64 | 4 | 4 GB | 64 GB | ARM64 (aarch64) | Host-Only | Offensive Security Workstation |

---

## Hypervisor Configuration

| Configuration | Value |
| ------------- | ----- |
| Hypervisor | UTM |
| Virtualisation Engine | QEMU |
| Host Platform | Apple MacBook Pro M4 |
| Host Operating System | macOS Sequoia |
| Host Architecture | Apple Silicon ARM64 |
| Firmware | UEFI |
| Network Mode | Host-Only |

---

## UEFI Configuration

All virtual machines were configured to boot using UEFI firmware within UTM.

UEFI provides modern firmware functionality, improved compatibility with current operating systems, and aligns with contemporary enterprise deployment standards.

---

## Baseline Configuration

Each virtual machine was deployed with the following baseline configuration:

- Static IPv4 addressing
- Host-only networking
- Enterprise hostname
- Operating system updates
- Baseline validation
- Documentation evidence

---

## Resource Allocation Strategy

Virtual machine resources were allocated according to each system's intended enterprise role.

- **Windows Server 2022** prioritises directory services, DNS, and future Active Directory workloads.
- **Windows 11 Pro** is allocated additional compute resources to support future endpoint security tools and domain-based administration.
- **Ubuntu Server 24.04 LTS** provides sufficient capacity for future logging, monitoring, and SIEM integration.
- **Kali Linux ARM64** provides dedicated resources for security testing while maintaining efficient host utilisation.

---

## Design Considerations

The virtual machine specifications were selected to balance enterprise functionality with efficient resource utilisation on the host platform.

The baseline allocation provides sufficient capacity for future Identity and Access Management (IAM), Governance, Risk and Compliance (GRC), Cloud Security, and Security Operations projects without requiring significant changes to the underlying infrastructure.

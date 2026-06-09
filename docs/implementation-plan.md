## 🧠 Overview

This document describes the step-by-step implementation plan for building the SOC detection and response lab using Wazuh SIEM, Windows endpoints, and Kali Linux.

---

## 🏗️ Phase 1: Lab Environment Setup

### Tasks:
- Install VirtualBox / VMware
- Create virtual machines:
  - Windows Server (Active Directory)
  - Windows 10 Endpoint
  - Kali Linux Attacker
- Configure internal network (Host-only / NAT network)

---

## 🔐 Phase 2: Endpoint Security Setup

### Tasks:
- Install Sysmon on Windows machines
- Configure Sysmon logging rules
- Enable Windows Event Logging
- Install Wazuh agent on endpoints

---

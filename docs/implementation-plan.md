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

## 📡 Phase 3: SIEM Deployment

### Tasks:
- Install Wazuh Server
- Configure Wazuh Manager
- Connect agents to SIEM
- Verify log ingestion

---

## 🧪 Phase 4: Detection Engineering

### Tasks:
- Create custom Wazuh rules:
  - Brute force detection
  - Suspicious PowerShell execution
  - Registry modification detection
- Test rule triggering

---

## ⚔️ Phase 5: Attack Simulation

### Tasks:
- Simulate port scanning (Nmap)
- Perform brute force attacks (SSH / RDP)
- Execute PowerShell payloads
- Modify registry keys for persistence

---

## 📊 Phase 6: Monitoring & Dashboards

### Tasks:
- Build Wazuh dashboards
- Visualize alerts
- Monitor authentication failures
- Track suspicious activities

---

## 🚨 Phase 7: Incident Analysis

### Tasks:
- Investigate generated alerts
- Correlate logs
- Determine attack timeline
- Document findings

---


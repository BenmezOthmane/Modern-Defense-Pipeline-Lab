## 🧠 Overview

This document describes the step-by-step implementation plan for building the SOC detection and response lab using Wazuh SIEM, Windows endpoints, and Kali Linux.

---

## 🏗️ Phase 1: Lab Environment Setup

### Tasks:
- Install VMware
- Create virtual machines:
- Windows Server (Active Directory)
- Windows 10 Endpoint
- Kali Linux Attacker
- Configure internal network (Host-only / NAT network)

---

## 📡 Phase 2: SIEM Deployment (Wazuh Server)

### 🖥️ Environment
- Ubuntu Server (VM) will be used as the SIEM host
- Wazuh will be installed on this server as the central monitoring platform

---

### Tasks:

- Install Ubuntu Server (VM)
- Update system packages
- Install Wazuh Server on Ubuntu
- Configure Wazuh Manager
- Install and configure Wazuh Dashboard (Kibana/OpenSearch interface)
- Open required ports (for agent communication)
- Connect Windows and Linux agents to the SIEM
- Verify log ingestion from all endpoints

---

## 🔐 Phase 3: Endpoint Security Setup

### Tasks:
- Install Sysmon on Windows machines
- Configure Sysmon logging rules
- Enable Windows Event Logging
- Install Wazuh agent on endpoints

---

## ⚔️ Phase 4: Attack Simulation

### Tasks:
- Simulate port scanning (Nmap)
- Perform brute force attacks (SSH / RDP)
- Execute PowerShell payloads
- Modify registry keys for persistence

---

## 🧪 Phase 5: Detection Engineering

### Tasks:
- Create custom Wazuh rules:
  - Brute force detection
  - Suspicious PowerShell execution
  - Registry modification detection
- Test rule triggering

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

## 🎯 Final Outcome

A fully functional SOC home lab demonstrating:

- Log collection pipeline
- Detection engineering
- Attack simulation
- Incident response workflow

# Traffic Flow

This document describes how data flows within the SOC lab environment, including normal operations and attack scenarios.

---

## 1. Normal Traffic Flow

User authentication and system communication:

Windows 10 → Windows Server (Domain Authentication)
Windows 10 → DNS queries → Windows Server
All systems → Wazuh Agent → Wazuh SIEM (log forwarding)

---

## 2. Log Collection Flow

Windows Systems
→ Sysmon + Event Logs
→ Wazuh Agent
→ Wazuh Manager (Ubuntu Server)
→ Indexer
→ Dashboard Visualization

---

## 3. Attack Simulation Flow

Kali Linux (Attacker)
→ Target Scanning (Port Scan)
→ Credential Attacks (Brute Force RDP/SSH)
→ Execution (PowerShell Payload)
→ Persistence (Registry Modification)
→ Privilege Escalation

---

## 4. SOC Detection Flow

Logs Generated (Endpoints)
→ Wazuh Rule Matching
→ Event Correlation
→ Alert Generation
→ SOC Analyst Triage
→ Investigation & Validation
→ Incident Report

---

## Summary

This lab simulates both normal enterprise traffic and malicious attack behavior to enable realistic SOC monitoring and detection scenarios.

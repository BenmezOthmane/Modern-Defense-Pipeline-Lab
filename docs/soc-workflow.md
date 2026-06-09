# SOC Workflow

## Overview

This document describes how security events are generated, collected, analyzed, and investigated within the SOC lab environment.

---

## 1. Attack Lifecycle

The simulated attack lifecycle follows common attacker behavior:

1. Port Scanning (Reconnaissance)
2. Brute Force / Password Spraying (Initial Access)
3. Suspicious PowerShell Execution (Execution)
4. Registry Persistence (Persistence)
5. Privilege Escalation (Privilege Escalation)

---

## 2. Log Collection Workflow

Security events are collected from multiple sources:

- Windows Event Logs
- Sysmon Operational Logs
- Wazuh Agent

Workflow:

Windows Endpoint
→ Sysmon / Event Logs
→ Wazuh Agent
→ Wazuh Manager

---

## 3. Detection Workflow

Collected logs are analyzed by Wazuh.

Workflow:

Log Received
→ Rule Matching
→ Event Correlation
→ Alert Generation
→ Dashboard Visualization

---

## 4. Incident Response Workflow

Once an alert is generated, the SOC analyst follows a structured process:

1. Triage
2. Investigation
3. Validation
4. Severity Classification
5. Reporting

Workflow:

Alert
→ Triage
→ Investigation
→ Validation
→ Report

---


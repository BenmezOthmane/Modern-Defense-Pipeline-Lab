# Attack Flow - SOC Detection & Response Lab

## 🧠 Overview

This document describes the end-to-end attack flow simulated in the SOC laboratory environment.  
It explains how malicious activity is generated, detected, and analyzed using Wazuh SIEM and endpoint logging tools.

The goal is to simulate real-world attacker behavior and demonstrate how a SOC analyst detects and responds to security incidents.

---

# ⚔️ Attack Flow Scenarios

---

## 1. Credential Attack (Brute Force / Password Spraying)

### 🧭 Flow Description

1. Attacker machine (Kali Linux) initiates repeated login attempts.
2. Target system (Windows Server / SSH service) receives authentication requests.
3. Multiple failed login attempts are recorded in system logs.
4. Sysmon / Windows Event Logs capture authentication failures.
5. Wazuh agent collects logs from the endpoint.
6. Logs are forwarded to Wazuh Manager for analysis.
7. Detection rules identify abnormal authentication patterns (threshold-based).
8. Security alert is generated in Wazuh dashboard.
9. SOC analyst investigates source IP and login behavior.

### 🎯 Detection Objective

- Detect brute force and password spraying attempts
- Identify abnormal authentication patterns
- Trigger alerts based on failed login thresholds

---

## 2. Suspicious PowerShell Execution

### 🧭 Flow Description

1. Attacker executes PowerShell commands on compromised Windows machine.
2. Commands may include encoded or obfuscated scripts.
3. Windows logs record PowerShell execution events.
4. Sysmon captures process creation and command-line arguments.
5. Wazuh agent collects event logs.
6. SIEM analyzes behavior for suspicious patterns.
7. Detection rule triggers alert for abnormal PowerShell usage.
8. SOC analyst investigates command execution history.

### 🎯 Detection Objective

- Detect fileless malware techniques
- Monitor suspicious PowerShell usage
- Identify encoded or unusual command execution

---

## 3. Network Reconnaissance (Port Scanning)

### 🧭 Flow Description

1. Attacker scans target network using tools like Nmap.
2. Multiple connection attempts are made across ports.
3. Firewall / system logs record scanning behavior.
4. Logs are collected via Wazuh agent.
5. SIEM detects high-frequency connection attempts.
6. Alert is generated for potential reconnaissance activity.
7. SOC analyst reviews source IP and scan pattern.

### 🎯 Detection Objective

- Identify reconnaissance before intrusion
- Detect abnormal port scanning activity
- Provide early warning signals

---


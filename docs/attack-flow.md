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

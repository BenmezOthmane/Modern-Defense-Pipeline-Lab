# Modern SOC Detection & Response Lab (Wazuh SIEM)

## 🧠 Overview

This project is a fully simulated Security Operations Center (SOC) environment designed to demonstrate real-world security monitoring, detection engineering, and incident response workflows using open-source tools.

The lab replicates a small enterprise network where logs are collected, analyzed, and used to detect malicious activities such as brute-force attacks and system persistence techniques.

---

## 🎯 Objectives

- Build a realistic SOC home lab environment
- Centralize log collection using a SIEM (Wazuh)
- Generate and analyze security events from multiple endpoints
- Detect malicious activities using custom rules
- Simulate real attack scenarios using Kali Linux
- Practice incident detection and response workflows

---

## 🏗️ Architecture

![SOC Architecture](docs/Architecture_Diagram.png)

### Components:
- Windows Server (Active Directory Domain Controller)
- Windows 10 Endpoint (User Machine)
- Kali Linux (Attacker Machine)
- Wazuh SIEM (Monitoring & Detection Platform)
- Sysmon (Advanced Windows Logging)

---

## ⚙️ Tech Stack

- Wazuh SIEM
- Sysmon
- Windows Server / Windows 10
- Kali Linux
- VMware

---

## 🔄 Data Flow

1. Endpoints generate security logs (Windows Event Logs + Sysmon)
2. Wazuh agents collect and forward logs
3. Wazuh manager processes and normalizes events
4. Detection rules analyze suspicious behavior
5. Alerts are generated and visualized in dashboards

---

## ⚔️ Attack Scenarios

### 1. Credential Attacks (Brute Force / Password Spraying)
- Target: SSH / RDP services
- SOC Level: Tier 1 Detection
- Purpose: Detect abnormal authentication patterns

### 2. Network Reconnaissance (Port Scanning)
- Target: exposed services
- SOC Level: Early threat detection
- Purpose: Identify reconnaissance activity before intrusion

### 3. Execution of Suspicious PowerShell
- SOC Level: High-frequency Windows attack vector
- Purpose: Detect fileless malware behavior

### 4. Persistence via Registry Modification
- SOC Level: Post-compromise behavior
- Purpose: Identify malware persistence techniques

### 5. Privilege Escalation Simulation
- SOC Level: Incident Response
- Purpose: Simulate attacker gaining elevated access

---

## 🧪 Detection Engineering

This project includes custom detection rules such as:

- Brute force login detection
- Suspicious registry modification alerts
- Multiple failed authentication correlation
- Sysmon-based behavioral detection

---

## 📊 Dashboards

Wazuh dashboards are used to visualize:

- Authentication failures
- Active alerts
- Endpoint activity
- Attack patterns over time

---

## 🚨 Incident Response Workflow

1. Alert triggered by SIEM
2. Triage and severity classification
3. Log investigation (Wazuh + Sysmon)
4. Root cause analysis
5. Incident report generation

---

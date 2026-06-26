# Incident Lifecycle

## Purpose
This document describes how incidents are handled inside the Modern Defense Pipeline Lab.

## Lifecycle Stages

### 1. Detection
Security activity is detected through endpoint or network telemetry.

Examples:
- Sysmon Event ID 3
- Suricata `eve.json`
- Windows Security Event ID 4625

### 2. Alert Generation
Wazuh receives the telemetry and generates alerts based on built-in or custom detection rules.

### 3. Triage
The alert is reviewed to identify:
- Rule ID
- Severity
- Source IP
- Destination host
- Event timestamp
- MITRE ATT&CK mapping

### 4. Investigation
Related events are reviewed to understand scope and intent.

### 5. Response
The analyst determines whether the activity requires containment, monitoring, or documentation only.

### 6. Reporting
Findings are documented in scenario reports with evidence and analyst conclusions.

## Current Validated Incidents

| Scenario | Detection Source | Status |
|---|---|---|
| Port Scan | Suricata / Wazuh | Completed |
| SSH Brute Force | Windows Security Logs / Wazuh | Completed |
| Suspicious PowerShell | PowerShell Logs / Wazuh | Planned |
| Registry Persistence | Sysmon / Wazuh | Planned |
| Privilege Escalation | Windows Security Logs / Wazuh | Planned |

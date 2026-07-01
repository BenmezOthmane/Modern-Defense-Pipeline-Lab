# Incident Lifecycle

## Purpose

This document describes how incidents are handled inside the Modern Defense Pipeline Lab.

## Lifecycle Stages

### 1. Detection

Security activity is detected through endpoint or network telemetry.

Examples:

- Suricata `eve.json`
- Sysmon Event ID 13
- Windows Security Event IDs 4625, 4688, and 4732

### 2. Alert Generation

Wazuh receives telemetry and generates alerts based on built-in and custom rules.

### 3. Triage

The analyst reviews the alert to identify:

- Rule ID
- Severity
- Source IP
- Destination host
- User account
- Process or registry object
- MITRE ATT&CK mapping

### 4. Investigation

Related events are reviewed to determine whether the activity is isolated or part of a larger attack chain.

### 5. Response

The analyst performs containment and remediation when needed.

Examples:

- Remove Registry Run Key persistence.
- Revoke unauthorized administrator group membership.
- Verify no suspicious PowerShell processes remain active.
- Run Microsoft Defender checks.

### 6. Recovery

The endpoint is verified to ensure no persistence, suspicious processes, or unauthorized privileges remain.

### 7. Reporting

Findings are documented in scenario reports and final incident response reports.

## Current Validated Incidents

| Scenario | Detection Source | Status |
|---|---|---|
| Port Scan | Suricata / Wazuh | Completed |
| SSH Brute Force | Windows Security Logs / Wazuh | Completed |
| Suspicious PowerShell | Windows Event ID 4688 / Wazuh | Completed |
| Registry Persistence | Sysmon Event ID 13 / Wazuh | Completed |
| Privilege Escalation | Windows Event ID 4732 / Wazuh | Completed |

## Multi-Stage Incident

The final post-exploitation incident combined three stages:

```text
-> Suspicious PowerShell Execution
-> Registry Run Key Persistence
-> Privilege Escalation
```


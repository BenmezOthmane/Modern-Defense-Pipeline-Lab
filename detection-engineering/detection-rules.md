# Detection Engineering Rules

## Scenario 01 - Port Scan Detection

### Objective

Detect port scanning activity launched from Kali Linux against a monitored Windows 10 endpoint.

### Data Source

| Item | Value |
|---|---|
| Telemetry Source | Sysmon |
| Event Channel | Microsoft-Windows-Sysmon/Operational |
| Event ID | 3 - Network Connection |
| SIEM | Wazuh |

### Detection Logic

The detection correlates repeated Sysmon network connection alerts from the same source IP within a short time window.

| Field | Value |
|---|---|
| Rule ID | 100101 |
| Rule Level | 12 |
| Frequency | 3 |
| Timeframe | 60 seconds |
| Correlation Field | win.eventdata.sourceIp |
| MITRE ATT&CK | T1046 - Network Service Discovery |

### Detection Result

The detection was successfully validated.

Observed values:

| Field | Value |
|---|---|
| Attacker IP | 10.0.0.99 |
| Victim IP | 10.0.0.30 |
| Destination Port Observed | 135 |
| Protocol | TCP |
| Wazuh Rule ID | 100101 |
| Severity | Level 12 |
| MITRE Technique | T1046 - Network Service Discovery |

### Status

Completed and validated.


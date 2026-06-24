# Scenario 01 - Port Scan Detection Report

## Summary
A port scan was launched from Kali Linux against the Windows 10 endpoint. The activity was detected through Suricata IDS and reviewed in Wazuh.

## Details

| Item | Value |
|---|---|
| Attacker IP | 10.0.0.99 |
| Victim IP | 10.0.0.30 |
| Tool | Nmap |
| IDS | Suricata |
| SIEM | Wazuh |
| MITRE | T1046 - Network Service Discovery |

## Evidence
- Nmap scan output
- Suricata alert: PORT SCAN DETECTED
- Wazuh event fields showing source and destination details

## Analyst Conclusion
The activity matches reconnaissance behavior. The detection pipeline successfully captured network telemetry and surfaced it in Wazuh for investigation.

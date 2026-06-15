# Incident Report - Scenario 01: Port Scanning Detection

## Summary

A port scanning attempt was simulated from Kali Linux against a Windows 10 endpoint. The activity was detected using Sysmon Event ID 3 and correlated by Wazuh using a custom detection rule.

## Incident Details

| Item | Value |
|---|---|
| Scenario | Port Scanning |
| Attacker | Kali Linux |
| Attacker IP | 10.0.0.99 |
| Victim | Windows 10 |
| Victim IP | 10.0.0.30 |
| SIEM | Wazuh |
| Detection Rule | 100101 |
| Severity | Level 12 |
| MITRE ATT&CK | T1046 - Network Service Discovery |

## Evidence

The Wazuh alert confirmed:

- Rule ID: 100101
- Rule Level: 12
- Source IP: 10.0.0.99
- Destination IP: 10.0.0.30
- Destination Port observed: 135
- Protocol: TCP
- MITRE Technique: Network Service Discovery

## Analyst Triage

The alert was reviewed in Wazuh. The source IP matched the Kali attacker machine and the destination IP matched the Windows 10 endpoint. The event data confirmed inbound network connection attempts generated during the scan.

## Response

The activity was classified as reconnaissance. Active Response can be configured to temporarily block the attacking IP when rule `100101` is triggered. For this scenario, the main goal was detection validation and investigation.

## Conclusion

The port scanning scenario was successfully detected and validated. The detection pipeline worked end to end:

Kali Linux -> Windows 10 -> Sysmon -> Wazuh Agent -> Wazuh Manager -> Custom Alert

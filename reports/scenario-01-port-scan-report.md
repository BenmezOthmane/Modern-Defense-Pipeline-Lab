# Scenario 01 - Port Scan Detection Report

## Summary

A port scan was launched from Kali Linux against the Windows endpoint. The activity was detected through Suricata IDS and reviewed in Wazuh.

## Details

| Item | Value |
|---|---|
| Attacker IP | `10.0.0.99` |
| Victim IP | `10.0.0.30` |
| Attack Tool | Nmap |
| Detection Source | Suricata IDS |
| Log Source | `/var/log/suricata/eve.json` |
| SIEM | Wazuh |
| MITRE ATT&CK | T1046 - Network Service Discovery |

## Evidence

- Nmap scan output from Kali Linux.
- Suricata alert showing port scan detection.
- Wazuh event fields showing source IP, destination IP, destination port, and timestamp.

## Analyst Conclusion

The activity matches reconnaissance behavior. The detection pipeline successfully captured network telemetry and surfaced it in Wazuh for investigation.

## Status

Closed.

# Detection Engineering Rules

## Scenario 01 - Port Scan Detection

| Item | Value |
|---|---|
| Attack Tool | Nmap |
| Network Sensor | Suricata |
| Log Source | /var/log/suricata/eve.json |
| SIEM | Wazuh |
| MITRE ATT&CK | T1046 - Network Service Discovery |

### Detection Summary
Port scanning activity was detected using Suricata IDS and ingested into Wazuh for alerting and investigation.

### Validated Evidence
- Source IP: 10.0.0.99
- Destination IP: 10.0.0.30
- Alert: PORT SCAN DETECTED
- Wazuh source: Suricata / eve.json

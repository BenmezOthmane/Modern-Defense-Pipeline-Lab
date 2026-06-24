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


## Scenario 02 - Brute Force Detection

| Item | Value |
|---|---|
| Attack Tool | Hydra |
| Target Service | SSH |
| Windows Event ID | 4625 |
| SIEM | Wazuh |
| MITRE ATT&CK | T1110 - Brute Force |

### Detection Summary
Repeated failed authentication attempts were detected from the Kali attacker machine against the Windows 10 endpoint.

### Validated Evidence
- Source activity: Hydra SSH brute force
- Target IP: 10.0.0.30
- Windows Event ID: 4625
- Wazuh alert: Logon Failure - Unknown user or bad password


## Remaining Scenarios

| Scenario | Status |
|---|---|
| Suspicious PowerShell Detection | Planned |
| Registry Persistence Detection | Planned |
| Privilege Escalation Detection | Planned |

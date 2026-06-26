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
![source_IP&destination_IP](screenshots/Source&DestIP.png)


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
![agent_IP](screenshots/BruteForceEv.png)
![event_ID](screenshots/scenario02-wazuh-4625-alert-fields1.png)
![Logon_Failure](screenshots/scenario02-wazuh-4625-alert-fields3.png)


## Remaining Scenarios

| Scenario | Status |
|---|---|
| Suspicious PowerShell Detection | Planned |
| Registry Persistence Detection | Planned |
| Privilege Escalation Detection | Planned |

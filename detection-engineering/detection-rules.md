# Detection Engineering Rules

## Scenario 01 - Port Scan Detection

| Item | Value |
|---|---|
| Attack Tool | Nmap |
| Detection Source | Suricata IDS |
| Log Source | `/var/log/suricata/eve.json` |
| SIEM | Wazuh |
| MITRE ATT&CK | T1046 - Network Service Discovery |

### Detection Summary

Port scanning activity was detected through Suricata IDS and ingested into Wazuh for alerting and investigation.

![Nmap_scan_output](screenshots/scenario01-nmap-scan.png)
![Suricata_eve.json_alert](screenshots/scenario01-suricata-eve-json-alert.png)
![Wazuh_fields](screenshots/scenario01-wazuh-suricata-alert-fields1.png)


---


## Scenario 02 - SSH Brute Force Detection

| Item | Value |
|---|---|
| Attack Tool | Hydra |
| Target Service | SSH |
| Windows Event ID | 4625 |
| SIEM | Wazuh |
| MITRE ATT&CK | T1110 - Brute Force |

### Detection Summary

Repeated failed authentication attempts were detected from the Kali attacker machine against the Windows endpoint.

### Evidence To Include

![Hydra_output](screenshots/scenario02-hydra-ssh-bruteforce.png)
![Wazuh-4625-alert](screenshots/scenario02-wazuh-4625-alert-fields1.png)
![Wazuh-4625-alert](screenshots/scenario02-wazuh-4625-alert-fields2.png)


---


## Scenario 03 - Suspicious PowerShell Execution

| Item | Value |
|---|---|
| Event Source | Windows Security Logs |
| Event ID | 4688 - Process Creation |
| Command Line | `powershell.exe -ExecutionPolicy Bypass -NoProfile` |
| Wazuh Rule ID | 100201 |
| MITRE ATT&CK | T1059.001 - PowerShell |

### Detection Summary

Suspicious PowerShell execution was detected after a command was launched with execution policy bypass and no profile loading.


---



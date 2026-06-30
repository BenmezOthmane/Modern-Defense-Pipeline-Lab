# Detection Engineering Rules

This document summarizes the detection rules developed and validated throughout the Home SOC Lab.

---

# Scenario 01 - Port Scan Detection

| Item | Value |
|---|---|
| Attack Tool | Nmap |
| Network Sensor | Suricata |
| Log Source | /var/log/suricata/eve.json |
| SIEM | Wazuh |
| MITRE ATT&CK | T1046 – Network Service Discovery |

### Detection Summary

Port scanning activity was detected using Suricata IDS and forwarded to Wazuh for alert generation and investigation.

### Validated Evidence

![Source_IP&Destination_IP](screenshots/Source&DestIP.png)


---


# Scenario 02 - SSH Brute Force Detection

| Item | Value |
|---|---|
| Attack Tool | Hydra |
| Target Service | SSH |
| Windows Event ID | 4625 |
| SIEM | Wazuh |
| MITRE ATT&CK | T1110 – Brute Force |

### Detection Summary

Multiple failed authentication attempts were detected from the Kali Linux attacker against the Windows 10 endpoint.

### Validated Evidence

![Brute Force](screenshots/BruteForceEv.png)

![Event ID](screenshots/scenario02-wazuh-4625-alert-fields1.png)

![Logon Failure](screenshots/scenario02-wazuh-4625-alert-fields3.png)


---


# Scenario 03 - Suspicious PowerShell Detection

| Item | Value |
|---|---|
| Attack Tool | PowerShell |
| Windows Event ID | 4688 |
| Detection Rule | Custom Rule (100201) |
| SIEM | Wazuh |
| MITRE ATT&CK | T1059.001 – PowerShell |

### Detection Summary

A suspicious PowerShell process executed using **ExecutionPolicy Bypass** was detected through a custom Wazuh rule based on Windows Security Event ID 4688.

### Validated Evidence

![PowerShell Detection](screenshots/scenario03-powershell.png)


---


# Scenario 04 - Registry Persistence Detection

| Item | Value |
|---|---|
| Attack Tool | reg.exe |
| Log Source | Sysmon |
| Sysmon Event ID | 13 |
| Detection Rule | Wazuh Rule 92302 |
| SIEM | Wazuh |
| MITRE ATT&CK | T1547.001 – Registry Run Keys / Startup Folder |

### Detection Summary

A Registry Run Key modification was detected after creating an autorun persistence entry using **reg.exe**.

### Validated Evidence

![Registry Persistence](screenshots/scenario04-registry.png)


---

# Scenario 05 - Privilege Escalation Detection

| Item | Value |
|---|---|
| Attack Tool | net localgroup |
| Windows Event ID | 4732 |
| Detection Rule | Wazuh Built-in Rule 60154 |
| SIEM | Wazuh |
| MITRE ATT&CK | T1078.002 – Valid Accounts: Domain Accounts |

### Detection Summary

Adding **testuser** to the local **Administrators** group generated Windows Security Event ID 4732, which was successfully detected by Wazuh.

### Validated Evidence

![Privilege Escalation](screenshots/scenario05-privilege-escalation.png)

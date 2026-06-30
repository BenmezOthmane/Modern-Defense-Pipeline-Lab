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



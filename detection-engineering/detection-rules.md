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

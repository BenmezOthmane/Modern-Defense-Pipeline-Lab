# Attack Scenarios

## Scenario 01 - Port Scanning

### Objective
Simulate network reconnaissance against the Windows 10 endpoint.

### Attack Command
```bash
nmap -sS -T4 10.0.0.30
```
### Result
The scan was detected through Suricata network telemetry and Wazuh alerting.

### Evidence
![Nmap_scan_from_Kali](screenshots/scenario01-nmap-scan.png)
![Suricata_eve.json_alert](screenshots/scenario01-suricata-eve-json-alert.png)
![Wazuh_Suricata_Alert_Fields1](screenshots/scenario01-wazuh-suricata-alert-fields1.png)
![Wazuh_Suricata_Alert_Fields2](screenshots/scenario01-wazuh-suricata-alert-fields2.png)
![Wazuh_Suricata_Alert_Fields31](screenshots/scenario01-wazuh-suricata-alert-fields3.png)
![Wazuh_dashboard_overview](screenshots/scenario01-wazuh-dashboard-overview.png)

### Status
Completed


## Scenario 02 - SSH Brute Force

### Objective
Simulate repeated failed SSH login attempts against the Windows 10 endpoint.

### Attack Command

```bash
hydra -l testuser -P /home/kali/Desktop/passw.txt -v ssh://10.0.0.30
```

### Result
The brute force attempt generated multiple Windows failed logon events and Wazuh alerts.

### Evidence
![Hydra_execution_from Kali](screenshots/scenario02-hydra-ssh-bruteforce.png)
![Windows_Security_Event_ID_4625](screenshots/scenario02-wazuh-4625-alerts-overview.png)
![Wazuh_alert_showing_failed_login_activity_1](screenshots/scenario02-wazuh-4625-alert-fields2.png)
![Wazuh_alert_showing_failed_login_activity_2](screenshots/scenario02-wazuh-4625-alert-fields3.png)

### Status
Completed


## Scenario 03 - Suspicious PowerShell Execution

### Objective

Simulate suspicious PowerShell execution commonly used during the execution phase of an attack.

### Attack Command

```powershell
powershell.exe -ExecutionPolicy Bypass -NoProfile
```

### Result

The PowerShell process was detected by a custom Wazuh rule (Rule ID: 100201) based on Windows Security Event ID 4688.

### Evidence

![PowerShell Alert](screenshots/scenario03-powershell.png)

---

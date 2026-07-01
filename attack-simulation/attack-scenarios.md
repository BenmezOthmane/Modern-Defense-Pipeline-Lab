# Attack Scenarios

## Scenario 01 - Port Scanning

### Objective

Simulate network reconnaissance against the Windows endpoint.

### Attack Command

```bash
nmap -sS -T4 10.0.0.30
```
![Nmap_scan_from_Kali](screenshots/scenario01-nmap-scan.png)

### Expected Result

Suricata detects the scan and Wazuh ingests the resulting `eve.json` alert.

![Suricata_eve.json_alert](screenshots/scenario01-suricata-eve-json-alert.png)

### Status

Completed.

---

## Scenario 02 - SSH Brute Force

### Objective

Simulate repeated failed SSH login attempts against the Windows endpoint.

### Attack Command

```bash
hydra -l testuser -P /home/kali/Desktop/passw.txt -v ssh://10.0.0.30
```
![Hydra_execution_from Kali](screenshots/scenario02-hydra-ssh-bruteforce.png)

### Expected Result

Windows generates Event ID `4625` and Wazuh displays failed logon alerts.

![Windows_Security_Event_ID_4625](screenshots/scenario02-wazuh-4625-alerts-overview.png)

### Status

Completed.

---

## Scenario 03 - Suspicious PowerShell Execution

### Objective

Simulate suspicious post-compromise command execution using PowerShell.

### Simulated Command

```powershell
powershell.exe -ExecutionPolicy Bypass -NoProfile
```

### Expected Result

Wazuh detects suspicious PowerShell execution through process creation telemetry.

### Status

Completed.

### Evidence
![Wazuh_Suricata_Alert_Fields1](screenshots/scenario01-wazuh-suricata-alert-fields1.png)
![Wazuh_Suricata_Alert_Fields2](screenshots/scenario01-wazuh-suricata-alert-fields2.png)
![Wazuh_Suricata_Alert_Fields31](screenshots/scenario01-wazuh-suricata-alert-fields3.png)
![Wazuh_dashboard_overview](screenshots/scenario01-wazuh-dashboard-overview.png)

### Status
Completed

---


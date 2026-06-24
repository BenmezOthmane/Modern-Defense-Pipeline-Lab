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
![Nmap scan from Kali](screenshots/scenario01-nmap-scan.png)
![Suricata eve.json alert](screenshots/scenario01-suricata-eve-json-alert.png)
![Wazuh-Suricata-Alert-Fields1](screenshots/scenario01-wazuh-suricata-alert-fields1.png)
![Wazuh-Suricata-Alert-Fields2](screenshots/scenario01-wazuh-suricata-alert-fields2.png)
![Wazuh-Suricata-Alert-Fields31](screenshots/scenario01-wazuh-suricata-alert-fields3.png)
![Wazuh-dashboard-overview](screenshots/scenario01-wazuh-dashboard-overview.png)

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
![Hydra execution from Kali](screenshots/scenario02-hydra-ssh-bruteforce.png)
![Windows Security Event ID 4625](screenshots/scenario02-wazuh-4625-alerts-overview.png)
![Wazuh alert showing failed login activity 1](screenshots/scenario02-wazuh-4625-alert-fields2.png)
![Wazuh alert showing failed login activity 2](screenshots/scenario02-wazuh-4625-alert-fields3.png)


### Status
Completed

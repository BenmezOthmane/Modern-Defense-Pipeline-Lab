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
Nmap scan from Kali
Suricata eve.json alert
Wazuh alert showing port scan fields

### Status
Completed


## Scenario 02 - SSH Brute Force

### Objective
Simulate repeated failed SSH login attempts against the Windows 10 endpoint.

### Attack Command
```bash
hydra -l testuser -P /home/kali/Desktop/passw.txt -u ssh://10.0.0.30
```

### Result
The brute force attempt generated multiple Windows failed logon events and Wazuh alerts.

### Evidence
Hydra execution from Kali
Windows Security Event ID 4625
Wazuh alert showing failed login activity

### Status
Completed

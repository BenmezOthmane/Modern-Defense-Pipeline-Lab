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

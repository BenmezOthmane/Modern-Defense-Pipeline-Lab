# Attack Scenarios

## Scenario 01 - Port Scanning

### Objective

Simulate reconnaissance activity from Kali Linux against the Windows 10 endpoint.

### Environment

| Role | Host | IP Address |
|---|---|---|
| Attacker | Kali Linux | 10.0.0.99 |
| Victim | Windows 10 | 10.0.0.30 |
| SIEM | Ubuntu Server / Wazuh | 10.0.0.20 |

### Attack Command

```bash
nmap -sT -p 1-1000 10.0.0.30
```

### Expected Telemetry

| Source | Event |
|---|---|
| Sysmon | Event ID 3 - Network Connection |
| Wazuh | Custom alert rule 100101 |

### Result

The port scan generated Sysmon network connection events and Wazuh successfully correlated the activity into a high-severity alert.

### Status

Completed.



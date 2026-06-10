## Network Design

| Machine | OS | Role | IP |
|---|---|---|---|
| DC01 | Windows Server 2022 | Domain Controller — SOC.local | 10.0.0.10 (Host-only) |
| WORKSTATION01 | Windows 10 Pro | Domain-joined Victim Endpoint | 10.0.0.30 (Host-only) |
| SIEM01 | Ubuntu Server | Wazuh SIEM (Docker) | 10.0.0.20 (Host-only) |
| ATTACKER | Kali Linux | Red Team / Threat Actor | 10.0.0.99 (Host-only) |


## Netwok Architecture

```
                [ Kali Linux ]
                      |
                      |
        -------------------------------
        |             |              |
        |             |              |
 [Windows 10]   [Windows Server]   [Ubuntu Wazuh]
        |             |              |
        -------- Host-Only Network ------
                   (10.0.0.0/24)

```
                   

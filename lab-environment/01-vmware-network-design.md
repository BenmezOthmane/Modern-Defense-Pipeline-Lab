## Network Design

| Machine | OS | Role | IP |
|---|---|---|---|
| DC01 | Windows Server 2022 | Domain Controller — SOC.local | 10.0.0.10 |
| WORKSTATION01 | Windows 10 Pro | Domain-joined Victim Endpoint | 10.0.0.30 |
| SIEM01 | Ubuntu Server | Wazuh SIEM (Docker) | 10.0.0.20 |
| ATTACKER | Kali Linux | Red Team / Threat Actor | 10.0.0.99 |

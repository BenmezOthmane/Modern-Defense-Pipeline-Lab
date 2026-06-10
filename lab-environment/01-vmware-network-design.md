## Network Design

This design simulates an isolated enterprise internal network where all endpoints communicate through a controlled Host-Only environment monitored by a central SIEM.

| Machine | OS | Role | IP |
|---|---|---|---|
| DC01 | Windows Server 2022 | Domain Controller — SOC.local | 10.0.0.10 (Host-only) |
| WORKSTATION01 | Windows 10 Pro | Domain-joined Victim Endpoint | 10.0.0.30 (Host-only) |
| SIEM01 | Ubuntu Server | Wazuh SIEM (Docker) | 10.0.0.20 (Host-only) |
| ATTACKER | Kali Linux | Red Team / Threat Actor | 10.0.0.99 (Host-only) |

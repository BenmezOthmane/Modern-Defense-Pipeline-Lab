# Network Design

| Machine            | OS                     | Role                               | IP Address     |
|--------------------|------------------------|------------------------------------|----------------|
| DC01               | Windows Server 2022    | Domain Controller (SOC.local)      | 10.0.0.10      |
| WORKSTATION01      | Windows 10 Pro         | Domain-joined endpoint             | 10.0.0.30      |
| SIEM01             | Ubuntu Server          | Wazuh SIEM (Docker)               | 10.0.0.20      |
| ATTACKER           | Kali Linux             | Red Team / Threat Actor           | 10.0.0.99      |

---

## Design Notes

This architecture simulates an isolated enterprise internal network using a Host-Only environment.

All machines are connected within a private subnet (10.0.0.0/24), allowing full internal communication while keeping the environment isolated from external networks.

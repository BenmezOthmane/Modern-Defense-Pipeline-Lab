## Network Design

| Machine | OS | Role | IP |
|---|---|---|---|
| DC01 | Windows Server 2022 | Domain Controller — SOC.local | 10.0.0.10 (Host-only) |
| WORKSTATION01 | Windows 10 Pro | Domain-joined Victim Endpoint | 10.0.0.30 (Host-only) |
| SIEM01 | Ubuntu Server | Wazuh SIEM (Docker) | 10.0.0.20 (Host-only) |
| ATTACKER | Kali Linux | Red Team / Threat Actor | 10.0.0.99 (Host-only) |


## Netwok Architecture

       ┌────────────────────────┐
       │     LAN(Host-only)     │
       │      10.0.0.0/24       |
       └───────────┬────────────┘
                   │          
   ┌───────────────▼───────────────┐  
   │      LAN CORPORATE ZONE       │  
   │      (Internal Network)       │  
   │                               │
   │  ┌─────────────────────────┐  │  
   │  │   Windows Server 2022   │  │ 
   │  │   (Domain Controller)   │  │ 
   │  │       SOC.local         │  │  
   │  └────────────┬────────────┘  │  
   │               │               │
   │  ┌────────────▼────────────┐  │           
   │  │    Windows 10 Pro       │  │          
   │  │    (Domain Joined)      |  |
   │  └────────────┬────────────┘  │           
   │               │               │        
   │  ┌────────────▼────────────┐  │
   │  │     Ubuntu Server       │  │ 
   │  │  ┌─────────────────┐    │  │   
   │  │  │  Wazuh (Docker) │    |  |
   │  │  ├─────────────────┤    │  │    
   │  │  │ Automated Backup│    │  │
   │  │  └─────────────────┘    │  │
   │  └───────────┬─────────────┘  |
   │              │                |
   │  ┌───────────▼─────────────┐  |
   |  |       Kali Linux        |  |
   |  |     (Threat Actor)      |  |
   |  └─────────────────────────┘  | 
   └───────────────────────────────┘

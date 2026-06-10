# IP Addressing Plan

The lab uses a private network (10.0.0.0/24) to simulate an internal enterprise SOC environment.

This addressing scheme ensures clear separation between systems while maintaining full internal communication for monitoring and attack simulation.

---

## IP Allocation Table

| Machine        | OS                  | Role                                  | IP Address   |
|----------------|---------------------|---------------------------------------|--------------|
| DC01           | Windows Server 2022 | Domain Controller (SOC.local)         | 10.0.0.10    |
| SIEM01         | Ubuntu Server       | Wazuh SIEM (Docker deployment)        | 10.0.0.20    |
| WORKSTATION01  | Windows 10 Pro      | Domain-joined endpoint (Victim)       | 10.0.0.30    |
| ATTACKER       | Kali Linux          | Red Team / Attack Simulation Machine  | 10.0.0.99    |

---

## Network Design Principle

This lab follows a flat internal network architecture using a Host-Only network configuration.

All machines are placed within the same subnet (10.0.0.0/24) to simulate an enterprise internal LAN where:

- The attacker can interact with internal systems
- Endpoints generate logs for SIEM ingestion
- The SIEM collects and analyzes all security events

---

## Key Objectives of This IP Scheme

- Simplify traffic monitoring and analysis
- Enable full visibility of attack paths
- Simulate real-world internal network behavior
- Support SOC detection and incident response scenarios

---

## Summary

This IP addressing plan provides a structured and realistic foundation for simulating enterprise-level security monitoring, attack detection, and incident response within the SOC lab.

# Lab Overview

The main objective of this lab is to simulate a real-world production environment for security monitoring and incident detection.

The SOC pipeline follows this workflow:
log collection → rule matching → event correlation → alert generation → dashboard visualization.

This is achieved while applying common attack scenarios, including:
- Port scanning simulation
- Brute force attacks (SSH / RDP)
- PowerShell payload execution
- Registry modification for persistence

After detection, a structured Incident Response process is applied:
Alert → Triage → Investigation → Validation → Reporting

---

## Components

- Windows 10 Pro: Domain-joined victim endpoint
- Windows Server 2022: Active Directory Domain Controller
- Ubuntu Server: Wazuh SIEM (Docker-based deployment)
- Kali Linux: Attacker machine (Red Team simulation)

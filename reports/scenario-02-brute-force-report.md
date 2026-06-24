# Scenario 02 - SSH Brute Force Detection Report

## Summary
An SSH brute force attempt was launched from Kali Linux using Hydra against the Windows 10 endpoint. The activity generated repeated failed logon events and Wazuh alerts.

## Details

| Item | Value |
|---|---|
| Attacker | Kali Linux |
| Victim IP | 10.0.0.30 |
| Tool | Hydra |
| Target Service | SSH |
| Windows Event ID | 4625 |
| Wazuh Alert | Logon Failure - Unknown user or bad password |
| MITRE | T1110 - Brute Force |

## Evidence
- Hydra brute force execution
- Multiple Windows failed logon events
- Wazuh alert fields showing Event ID 4625 and failed authentication details

## Analyst Conclusion
The activity matches brute force behavior. Wazuh successfully detected repeated failed authentication attempts from the simulated attack.

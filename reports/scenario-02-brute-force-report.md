# Scenario 02 - SSH Brute Force Detection Report

## Summary

An SSH brute force attempt was launched from Kali Linux using Hydra against the Windows endpoint. The activity generated repeated failed logon events and Wazuh alerts.

## Details

| Item | Value |
|---|---|
| Attacker | Kali Linux |
| Victim IP | `10.0.0.30` |
| Attack Tool | Hydra |
| Target Service | SSH |
| Windows Event ID | 4625 |
| SIEM | Wazuh |
| MITRE ATT&CK | T1110 - Brute Force |

## Evidence

- Hydra brute force execution output.
- Windows Security Event ID `4625`.
- Wazuh alert fields showing failed authentication details.

## Analyst Conclusion

The activity matches brute force behavior. Wazuh successfully detected repeated failed authentication attempts from the simulated attack.

## Status

Closed.

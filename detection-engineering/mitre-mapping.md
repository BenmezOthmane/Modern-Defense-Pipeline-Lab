# MITRE ATT&CK Mapping

| Scenario | Technique ID | Technique | Tactic | Status |
|---|---|---|---|---|
| Port Scan Detection | T1046 | Network Service Discovery | Discovery | Validated |
| Brute Force Detection | T1110 | Brute Force | Credential Access | Planned |
| Suspicious PowerShell Detection | T1059.001 | PowerShell | Execution | Planned |
| Registry Persistence Detection | T1547.001 | Registry Run Keys / Startup Folder | Persistence | Planned |
| Privilege Escalation Detection | T1078.002 | Domain Accounts / Local Accounts | Privilege Escalation | Planned |

## Validated Detection

### T1046 - Network Service Discovery

A port scanning attempt was launched from Kali Linux against the Windows 10 endpoint. Sysmon Event ID 3 captured the network connections, and Wazuh generated custom alert `100101` with severity level `12`.

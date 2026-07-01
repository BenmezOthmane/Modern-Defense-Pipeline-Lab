# MITRE ATT&CK Mapping

| Scenario | Technique ID | Technique | Tactic | Status |
|---|---|---|---|---|
| Port Scan Detection | T1046 | Network Service Discovery | Discovery | Completed |
| SSH Brute Force Detection | T1110 | Brute Force | Credential Access | Completed |
| Suspicious PowerShell Detection | T1059.001 | PowerShell | Execution | Completed |
| Registry Persistence Detection | T1547.001 | Registry Run Keys / Startup Folder | Persistence | Completed |
| Privilege Escalation Detection | T1484 - Privilege Escalation | Valid Account / Administrator Group Abuse | Privilege Escalation |  Completed |

## Multi-Stage Attack Chain

The final incident report documents a post-exploitation chain consisting of:

```text
-> PowerShell Execution
-> Registry Persistence
-> Privilege Escalation
```

This chain demonstrates how separate alerts can be correlated into a single incident narrative.

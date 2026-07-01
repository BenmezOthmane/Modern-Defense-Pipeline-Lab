# Lessons Learned

## Purpose

This document tracks key lessons learned while building and validating the lab scenarios.


## Scenario 01 - Port Scan

### What i've Worked

- Suricata detected the scan at the network level.
- Wazuh successfully ingested Suricata `eve.json` alerts.
- The alert provided useful source and destination fields for investigation.

### What i've Learned

- Network IDS telemetry is valuable for reconnaissance detection.
- Port scan validation is stronger when both attacker output and SIEM evidence are documented.

---

## Scenario 02 - SSH Brute Force

### What i've Worked

- Hydra generated repeated failed authentication attempts.
- Windows Security Event ID `4625` was visible in Wazuh.
- Wazuh provided enough fields to identify failed logon activity.

### What i've Learned

- Authentication attacks require reviewing event frequency, user account, and target service.
- Failed logon events should be correlated with attacker activity and timestamps.

---

## Scenarios 03-05 - Post-Exploitation Chain

### What i've Worked

- Wazuh detected suspicious PowerShell execution.
- Sysmon detected Registry Run Key persistence.
- Windows Security auditing detected administrator group membership modification.
- Correlating alerts revealed a complete attack chain.

### What i've Learned

- PowerShell alerts should be investigated for follow-on persistence or privilege activity.
- Registry Run Key changes must be verified and remediated.
- Administrator group membership changes should always be reviewed.
- A single alert may not tell the full story; timeline-based investigation is essential.


---


## General Lessons

- Each scenario should include attack evidence, SIEM evidence, and analyst notes.
- Screenshots should show source, destination, user, rule ID, timestamp, and MITRE mapping when possible.
- MITRE ATT&CK mapping improves the clarity and professionalism of reports.
- Response documentation is as important as detection validation.


# Lessons Learned

## Purpose

This document tracks key lessons learned while building and validating the lab scenarios.

## Scenario 01 - Port Scan

### What Worked

- Suricata detected the scan at the network level.
- Wazuh successfully ingested Suricata `eve.json` alerts.
- The alert provided useful source and destination fields for investigation.

### What Was Learned

- Network IDS telemetry is valuable for reconnaissance detection.
- Port scan validation is stronger when both attacker output and SIEM evidence are documented.

## Scenario 02 - SSH Brute Force

### What Worked

- Hydra generated repeated failed authentication attempts.
- Windows Security Event ID `4625` was visible in Wazuh.
- Wazuh provided enough fields to identify failed logon activity.

### What Was Learned

- Authentication attacks require reviewing event frequency, user account, and target service.
- Failed logon events should be correlated with attacker activity and timestamps.


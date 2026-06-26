# Lessons Learned

## Purpose
This document tracks key lessons learned while building and validating the lab scenarios.

## Scenario 01 - Port Scan

### What Worked
- Suricata detected the scan at the network level.
- Wazuh successfully ingested Suricata `eve.json` alerts.
- The alert provided useful source and destination fields for investigation.

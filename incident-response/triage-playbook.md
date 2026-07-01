# Triage Playbook

## Purpose

This playbook defines the triage process used when Wazuh generates an alert during the lab scenarios.

## General Triage Workflow

1. Identify alert name, rule ID, severity, timestamp, and affected host.
2. Confirm the source IP, destination IP, user account, or process involved.
3. Review raw event fields in Wazuh.
4. Map the alert to MITRE ATT&CK.
5. Search for related events around the same timestamp.
6. Decide whether the event is isolated or part of a larger attack chain.
7. Document evidence, conclusion, and response actions.

---

## Scenario 01 - Port Scan

### Key Checks

- Confirm source IP: `10.0.0.99`
- Confirm destination IP: `10.0.0.30`
- Review Suricata `eve.json` alert fields
- Confirm alert signature: `PORT SCAN DETECTED`
- Confirm MITRE mapping: `T1046`

### Analyst Decision

Classify as reconnaissance activity.

---

## Scenario 02 - SSH Brute Force

### Key Checks

- Confirm repeated failed logon attempts.
- Confirm Windows Event ID: `4625`.
- Review target account and target host.
- Confirm Hydra activity from the attacker machine.
- Confirm MITRE mapping: `T1110`.

### Analyst Decision

Classify as brute force authentication activity.

---



# Triage Playbook

## Purpose
This playbook defines the initial triage steps used when Wazuh generates an alert during the lab scenarios.

## Triage Workflow

1. Identify the alert name, rule ID, severity, and timestamp.
2. Confirm the affected host and source IP.
3. Review raw event fields in Wazuh.
4. Map the alert to MITRE ATT&CK.
5. Check whether the activity matches the simulated scenario.
6. Determine scope by searching for related events around the same timestamp.
7. Document evidence and analyst conclusion.

## Scenario 01 - Port Scan

### Key Checks
- Confirm source IP: `10.0.0.99`
- Confirm destination IP: `10.0.0.30`
- Review Suricata alert fields
- Review Wazuh alert details
- Confirm MITRE mapping: `T1046`

### Analyst Decision
Classify as reconnaissance activity.

## Scenario 02 - SSH Brute Force

### Key Checks
- Confirm repeated failed logons
- Confirm Windows Event ID: `4625`
- Review source activity from Hydra
- Check affected account and target host
- Confirm MITRE mapping: `T1110`

### Analyst Decision
Classify as brute force authentication activity.

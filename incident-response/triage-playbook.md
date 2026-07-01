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

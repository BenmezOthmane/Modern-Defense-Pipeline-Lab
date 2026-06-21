# Suricata IDS Integration

## Purpose

Suricata was integrated into the lab to add a network-based detection layer and improve the realism of attack detection scenarios.

While Wazuh provides endpoint visibility and log analysis, Suricata enables network traffic inspection and IDS-based detection. This integration allows security events generated from network activity to be collected, correlated, and investigated within a centralized SIEM platform.

---

## Detection Pipeline

```text
Attacker
   ↓
Network Traffic
   ↓
Suricata IDS
   ↓
eve.json
   ↓
Wazuh Log Collector
   ↓
Wazuh Rules & Correlation
   ↓
Wazuh Dashboard
```

---

## Role in the Lab

Suricata monitors network traffic generated during attack simulations and records network-based security events in the EVE JSON log format.

Wazuh ingests these events, applies decoding and correlation rules, and generates alerts that can be investigated through the Wazuh Dashboard.

This architecture provides visibility into both network-level and host-level activity, creating a more realistic SOC monitoring environment.

---

## Log Source

| Item          | Value                        |
| ------------- | ---------------------------- |
| Tool          | Suricata IDS                 |
| Log File      | `/var/log/suricata/eve.json` |
| Log Format    | JSON                         |
| SIEM Platform | Wazuh                        |

---

## Wazuh Collection Configuration

To ingest Suricata alerts into Wazuh, the Suricata EVE JSON log file was configured as a local log source in the Wazuh Manager configuration.

```xml
<localfile>
  <log_format>json</log_format>
  <location>/var/log/suricata/eve.json</location>
</localfile>
```

This configuration enables Wazuh to continuously monitor Suricata events and generate corresponding alerts inside the SIEM platform.

---

## Deployment Notes

The Wazuh Manager is deployed using Docker.

To allow Wazuh to ingest Suricata events, the Suricata log directory was mounted and made accessible inside the Wazuh Manager container.

The monitored log file is:

```text
/var/log/suricata/eve.json
```

---

## Port Scan Detection Flow

The Port Scan Detection scenario uses a custom Suricata rule with Signature ID (SID) **100101** mapped to **MITRE ATT&CK T1046 – Network Service Discovery**.

When the rule is triggered, the detection follows the workflow below:

```text
Port Scan
   ↓
Suricata Detection Rule (SID 100101)
   ↓
eve.json
   ↓
Wazuh Log Collector
   ↓
Wazuh Ruleset (Rule ID 86601)
   ↓
Wazuh Dashboard Alert
```

---

## Validation

The integration was validated by executing a port scanning activity from the attacker host and confirming that:

1. Suricata generated alerts in `eve.json`.
2. Wazuh successfully ingested the events.
3. Alerts appeared in the Wazuh Dashboard.
4. Events could be queried using:

```text
data.alert.signature_id:100101
```

Example alert:

```text
Suricata: Alert - PORT SCAN DETECTED
Rule ID: 86601
Signature ID: 100101
MITRE ATT&CK: T1046
```

---

## Security Value

This integration demonstrates how IDS alerts can be centralized within a SIEM platform to provide:

* Network-based threat detection.
* Centralized alert management.
* Event correlation capabilities.
* SOC investigation workflows.
* MITRE ATT&CK aligned detections.

The integration serves as the foundation for future attack scenarios implemented in this lab environment.

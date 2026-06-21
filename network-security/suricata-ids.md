# Suricata IDS Integration

## Purpose

Suricata was added to improve the realism of the port scanning detection scenario by introducing a network-based detection layer in addition to endpoint telemetry.

## Detection Pipeline

```text
Attacker
-> Network Traffic
-> Suricata IDS
-> eve.json
-> Wazuh SIEM
-> Correlation & Alerting
-> Dashboard
```

## Role In The Lab
Suricata monitors network traffic generated during the port scanning scenario and writes IDS events to eve.json.
Wazuh collects the Suricata eve.json log and displays IDS alerts in the dashboard.

## Log Source
| Item | Value |
|---|---|
| Tool | Suricata IDS |
| Log File | /var/log/suricata/eve.json |
| Log Format | JSON |
| SIEM | Detect Wazuh |

### Wazuh Collection Configuration

To ingest Suricata alerts into Wazuh, the Suricata `eve.json` log file was configured as a local log source in the Wazuh Manager configuration.

```xml
<localfile>
  <log_format>json</log_format>
  <location>/var/log/suricata/eve.json</location>
</localfile>
```

This configuration allows Wazuh to continuously monitor Suricata EVE JSON events and generate corresponding alerts inside the Wazuh platform.

In this lab environment, Suricata logs are available inside the Wazuh Manager container at:

```text
/var/log/suricata/eve.json
```

The event flow is:

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

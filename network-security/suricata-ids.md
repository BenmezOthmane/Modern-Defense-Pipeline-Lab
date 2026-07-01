# Suricata IDS Integration

## Purpose

Suricata was integrated to add a network-based detection layer to the lab, especially for the port scanning scenario.

## Detection Pipeline

```text
Attacker
-> Network Traffic
-> Suricata IDS
-> eve.json
-> Wazuh Log Collector
-> Wazuh Rules & Correlation
-> Wazuh Dashboard
```

## Log Source

| Item | Value |
|---|---|
| Tool | Suricata IDS |
| Log File | `/var/log/suricata/eve.json` |
| Log Format | JSON |
| SIEM | Wazuh |

## Wazuh Collection Configuration

```xml
<localfile>
  <log_format>json</log_format>
  <location>/var/log/suricata/eve.json</location>
</localfile>
```

## Validation

The integration was validated by running an Nmap scan from Kali Linux and confirming that:

1. Suricata generated an alert in `eve.json`.
2. Wazuh ingested the Suricata event.
3. The alert appeared in Wazuh Dashboard.
4. Source IP, destination IP, and destination port were visible for investigation.

## Security Value

Suricata provides network-level visibility, while Sysmon and Windows Security logs provide endpoint-level visibility. Together, they make the lab closer to a realistic SOC monitoring workflow.

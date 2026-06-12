## Detection Engineering Rules

## Port Scan Detection

Objective:
Detect multiple network connections from same source in short time.

Data Source:
Sysmon Event ID 3

Logic:
- Multiple destination ports
- Same source IP
- Short time window

MITRE:
T1046 - Network Service Discovery

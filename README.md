# Modern Defense Pipeline Lab

A hands-on Security Operations Center (SOC) project focused on endpoint visibility, log collection, SIEM integration, and detection engineering.

  ATTACK SIMULATION
        │
       ▼

┌─────────────┐       ┌─────────────┐
│ Windows 10.   │────▶ │    Sysmon     │
│  Endpoint     │       │  Telemetry     │
└─────────────┘       └──────┬──────┘
                           │
                           ▼
                    ┌─────────────┐
                    │ Wazuh Agent.   │
                    └──────┬──────┘
                           │
                           ▼
      ┌──────────────────────────────────┐
      │          Ubuntu Server                 │
      │                                        │
      │  Wazuh Manager (SIEM + EDR)            │
      │                                        │
      │  • Log Collection                      │
      │  • Event Correlation                   │
      │  • Detection Rules                     │
      │  • Alert Generation                    │
      └──────────────┬───────────────────┘
                        │
                        ▼
            ┌──────────────────────┐
            │ Wazuh Dashboard          │
            │ SOC Monitoring           │
            │ Security Analytics       │
            └──────────────────────┘
          

## Project Objectives

- Deploy Wazuh as a SIEM platform
- Configure Sysmon for advanced Windows telemetry
- Collect and analyze security logs
- Build detection rules and alerts
- Simulate attacks and validate detections

## Technologies Used

- Wazuh
- Sysmon
- Ubuntu Server
- Windows 10
- VMware

## Repository Structure

```text
architecture/
environment-setup/
wazuh-siem/
endpoint-telemetry/
detection-engineering/
attack-simulation/
logs/
screenshots/
report/
```

## Project Status

🚧 In Progress

Current Phase:
- [x] Repository Created
- [ ] Environment Setup
- [ ] Wazuh Installation
- [ ] Sysmon Deployment
- [ ] Detection Engineering
- [ ] Attack Simulation
- [ ] Documentation

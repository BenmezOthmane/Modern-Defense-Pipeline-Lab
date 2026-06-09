# Architecture Design

## Overview
This lab simulates a SOC environment with a small enterprise network.

## Components
- Windows Server (Active Directory Domain Controller)
- Windows 10 Endpoint (User Machine)
- Kali Linux (Attack Machine)
- Wazuh SIEM (Monitoring & Detection)

## Data Flow
1. Windows endpoints generate logs using Sysmon.
2. Logs are collected by Wazuh agents.
3. Wazuh Manager processes and normalizes logs.
4. Alerts are generated based on detection rules.
5. Dashboards visualize security events.

## Purpose
The goal is to simulate real-world SOC monitoring, detection, and response scenarios.

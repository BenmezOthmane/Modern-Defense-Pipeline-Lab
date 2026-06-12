# Wazuh Installation And Configuration

## Purpose

Document the Wazuh SIEM deployment used in this lab.

## Deployment Overview

| Item | Value |
|---|---|
| Server | Ubuntu Server |
| IP Address | 10.0.0.20 |
| Deployment Method | Docker |
| Role | Wazuh Manager, Indexer, and Dashboard |

## Components

| Component | Purpose |
|---|---|
| Wazuh Manager | Processes logs, rules, and alerts |
| Wazuh Indexer | Stores indexed security data |
| Wazuh Dashboard | Provides UI for monitoring and investigation |

## Configuration Notes

- Wazuh is deployed on Ubuntu Server using Docker.
- The dashboard is accessed from the lab network.
- The Wazuh Manager receives logs from the Windows endpoint through the Wazuh Agent.

## Evidence

| Evidence | Screenshot |
|---|---|
| Wazuh dashboard is accessible | ![Wazuh dashboard](../screenshots/08-wazuh-dashboard-home.png) |
| Wazuh Docker containers are running | ![Wazuh Docker containers](../screenshots/09-wazuh-docker-containers.png) |

## Status

Wazuh SIEM deployment completed.

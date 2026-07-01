# Incident Lifecycle

## Purpose

This document describes how incidents are handled inside the Modern Defense Pipeline Lab.

## Lifecycle Stages

### 1. Detection

Security activity is detected through endpoint or network telemetry.

Examples:

- Suricata `eve.json`
- Sysmon Event ID 13
- Windows Security Event IDs 4625, 4688, and 4732

### 2. Alert Generation

Wazuh receives telemetry and generates alerts based on built-in and custom rules.

# Attack Scenarios

## Scenario 01 - Port Scanning

### Objective

Simulate network reconnaissance against the Windows endpoint.

### Attack Command

```bash
nmap -sS -T4 10.0.0.30
```
![Nmap_scan_from_Kali](screenshots/scenario01-nmap-scan.png)

### Expected Result

Suricata detects the scan and Wazuh ingests the resulting `eve.json` alert.

![Suricata_eve.json_alert](screenshots/scenario01-suricata-eve-json-alert.png)

### Status

Completed.

---

## Scenario 02 - SSH Brute Force

### Objective

Simulate repeated failed SSH login attempts against the Windows endpoint.

### Attack Command

```bash
hydra -l testuser -P /home/kali/Desktop/passw.txt -v ssh://10.0.0.30
```
![Hydra_execution_from Kali](screenshots/scenario02-hydra-ssh-bruteforce.png)

### Expected Result

Windows generates Event ID `4625` and Wazuh displays failed logon alerts.

![Windows_Security_Event_ID_4625](screenshots/scenario02-wazuh-4625-alerts-overview.png)

### Status

Completed.

---

## Scenario 03 - Suspicious PowerShell Execution

### Objective

Simulate suspicious post-compromise command execution using PowerShell.

### Simulated Command

```powershell
powershell.exe -ExecutionPolicy Bypass -NoProfile
```
![Suspicious_PowerShell_execution](screenshots/BypassPowershell.png)
 
### Expected Result

Wazuh detects suspicious PowerShell execution through process creation telemetry.

![PowerShell-Alert](screenshots/01-PowerShell-Alert.png)

### Status

Completed.

---

## Scenario 04 - Registry Persistence

### Objective

Simulate persistence using a Registry Run Key.

### Simulated Command

```powershell
reg add HKCU\Software\Microsoft\Windows\CurrentVersion\Run /v Updater /t REG_SZ /d C:\Windows\System32\calc.exe /f
```

### Expected Result

Sysmon Event ID `13` is generated and Wazuh alerts on Registry Run Key persistence.

![Registry-Alert](screenshots/02-Registry-Alert.png)

### Status

Completed.

---

## Scenario 05 - Privilege Escalation

### Objective

Simulate privilege escalation by adding a user to the local Administrators group.

### Simulated Command

```powershell
net localgroup Administrators testuser /add
```

### Expected Result

Windows Event ID `4732` is generated and Wazuh alerts on administrator group membership modification.

![PrivilegeEscalation-Alert](screenshots/03-PrivilegeEscalation-Alert.png)

### Status

Completed.

# Suspicious CMD Detection
## SPL Query
index=main sourcetype="xmlwineventlog" EventCode=1 Image="cmd.exe"
| stats count by CommandLine

## What it detects
CMD.exe spawning recon commands like whoami, ipconfig, net user — 
commonly used by attackers after initial access to enumerate the system.

## Event ID
Sysmon Event ID 1 — Process Creation

## Severity
Medium

## Simulated With
```powershell
cmd.exe /c whoami
cmd.exe /c ipconfig
cmd.exe /c net user
```

## Response
- Review CommandLine field for suspicious commands
- Check parent process — was cmd spawned by Office, browser, or script?
- Correlate with other alerts in the same timeframe
- If part of a chain (PowerShell → CMD → net user), escalate immediately

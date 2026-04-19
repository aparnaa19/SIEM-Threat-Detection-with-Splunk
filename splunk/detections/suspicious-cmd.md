# Suspicious CMD Process Creation

Attackers use CMD to run recon commands like whoami and ipconfig 
after gaining access to map the environment.

**MITRE ATT&CK:** T1059.003 — Command and Scripting Interpreter: Windows Command Shell

## SPL Query
index=main sourcetype="xmlwineventlog" EventCode=1 Image="*cmd.exe*"
| stats count by CommandLine

## Event ID
Sysmon Event ID 1 — Process Creation

## Severity
Medium

## Response
- Review CommandLine for suspicious commands
- Check parent process
- Correlate with other alerts in same timeframe

## Screenshot
![Suspicious CMD](/screenshots/suscmd.png)

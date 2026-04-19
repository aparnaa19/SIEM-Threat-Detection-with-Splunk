# Suspicious PowerShell Detection

Attackers use encoded or hidden PowerShell commands to download malware, 
run scripts, and evade detection.

**MITRE ATT&CK:** T1059.001 — Command and Scripting Interpreter: PowerShell

## SPL Query
index=main sourcetype="xmlwineventlog" EventCode=1
CommandLine="*hidden*" OR CommandLine="*EncodedCommand*"

## Event ID
Sysmon Event ID 1 — Process Creation

## Severity
High

## Response
- Review full CommandLine
- Decode base64 if EncodedCommand used
- Check parent process
- Isolate host if malicious payload confirmed

## Screenshot
![Suspicious PowerShell](/screenshots/suspowershell.png)

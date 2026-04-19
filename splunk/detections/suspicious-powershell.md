# Suspicious PowerShell Detection

## SPL Query
```
index=main sourcetype="xmlwineventlog" EventCode=1 
CommandLine="*hidden*" OR CommandLine="*EncodedCommand*"
```

## What it detects
PowerShell running with hidden window or encoded commands — common attacker technique to evade detection.

## Event ID
Sysmon Event ID 1 — Process Creation

## Severity
High

## Response
- Review full CommandLine
- Decode the base64 if EncodedCommand
- Check parent process
- Isolate host if malicious payload confirmed

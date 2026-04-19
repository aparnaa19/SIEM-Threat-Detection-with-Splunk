# Brute Force Detection

## SPL Query
```
index=main sourcetype="WinEventLog:Security" EventCode=4625
| stats count by Account_Name, ComputerName
| where count > 5
```

## What it detects
More than 5 failed login attempts for the same account — classic brute force pattern.

## Event ID
4625 — An account failed to log on

## Severity
Medium

## Response
- Check Account_Name — is it a real user?
- Check time window — rapid failures = automated attack
- Block the source if external

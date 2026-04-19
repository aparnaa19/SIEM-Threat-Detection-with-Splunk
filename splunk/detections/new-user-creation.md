# New User Account Created

## SPL Query
```
index=main sourcetype="WinEventLog:Security" EventCode=4720
```

## What it detects
A new local user account was created — could indicate persistence by an attacker.

## Event ID
4720 — A user account was created

## Severity
High

## Response
- Check Account_Name — was this authorized?
- Check who created it (Subject fields)
- Remove if unauthorized

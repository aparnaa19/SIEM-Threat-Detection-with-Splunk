# Privilege Escalation

## SPL Query
```
index=main sourcetype="WinEventLog:Security" EventCode=4732
```

## What it detects
A user was added to a privileged group (e.g. Administrators).

## Event ID
4732 — A member was added to a security-enabled local group

## Severity
Critical

## Response
- Identify which group was modified
- Check if the change was authorized
- Remove unauthorized members immediately

# Linux Failed Authentication

## SPL Query
```
index=main sourcetype="syslog" host="192.168.0.24" 
("failed" OR "authentication failure")
```

## What it detects
Failed login attempts on Linux host via su, SSH, or PAM.

## Severity
High

## Response
- Check frequency — repeated failures = brute force
- Identify source user/IP
- Review /var/log/auth.log for full context

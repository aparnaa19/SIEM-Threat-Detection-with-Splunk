# Linux Failed Authentication

Repeated failed login attempts on Linux via su or SSH indicating 
brute force or unauthorized access attempts.

**MITRE ATT&CK:** T1110 — Brute Force

## SPL Query
index=main sourcetype="syslog" host="192.168.0.24"
("failed" OR "authentication failure")

## Severity
High

## Response
- Check frequency of failures
- Identify source user
- Review /var/log/auth.log for full context

## Screenshot
![Linux Failed Auth](/screenshots/linuxfailed.png)

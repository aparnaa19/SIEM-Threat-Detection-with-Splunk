# Linux Sudo Abuse

## SPL Query
```
index=main sourcetype="syslog" host="192.168.0.24" "sudo"
```

## What it detects
Any sudo usage on Linux host — useful for tracking privilege use.

## Severity
Medium

## Response
- Review command run with sudo
- Check if user is authorized to use sudo
- Investigate if sensitive files accessed (e.g. /etc/shadow)

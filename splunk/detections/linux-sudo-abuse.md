# Linux Sudo Abuse

Attackers abuse sudo to run commands as root, potentially accessing 
sensitive files like /etc/shadow or installing backdoors.

**MITRE ATT&CK:** T1548.003 — Abuse Elevation Control Mechanism: Sudo and Sudo Caching

## SPL Query
index=main sourcetype="syslog" host="192.168.0.24" "sudo"

## Severity
Medium

## Response
- Review command run with sudo
- Check if user is authorized
- Investigate if sensitive files were accessed

## Screenshot
![Linux Sudo](/screenshots/inuxsudo.png)

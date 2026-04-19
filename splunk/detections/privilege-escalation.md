# Privilege Escalation

Attackers add accounts to privileged groups like Administrators 
to gain elevated access and control over the system.

**MITRE ATT&CK:** T1078.003 — Valid Accounts: Local Accounts

## SPL Query
index=main sourcetype="WinEventLog:Security" EventCode=4732

## Event ID
4732 — A member was added to a security-enabled local group

## Severity
Critical

## Response
- Identify which group was modified
- Check if the change was authorized
- Remove unauthorized members immediately

## Screenshot
![Privilege Escalation](/screenshots/privescalation.png)

# New User Account Created

Attackers create new user accounts to maintain persistent access 
to a compromised system.

**MITRE ATT&CK:** T1136.001 — Create Account: Local Account

## SPL Query
index=main sourcetype="WinEventLog:Security" EventCode=4720

## Event ID
4720 — A user account was created

## Severity
High

## Response
- Check Account_Name — was this authorized?
- Check who created it (Subject fields)
- Remove if unauthorized

## Screenshot
![New User Creation](/screenshots/newuseracc.png)

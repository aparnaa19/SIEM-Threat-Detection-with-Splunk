# Brute Force Detection

Repeated failed login attempts targeting an account to guess the password. 
Can lead to unauthorized access if successful.

**MITRE ATT&CK:** T1110 — Brute Force

## SPL Query
index=main sourcetype="WinEventLog:Security" EventCode=4625
| stats count by Account_Name, ComputerName
| where count > 5

## Event ID
4625 — An account failed to log on

## Severity
Medium

## Response
- Check Account_Name — is it a real user?
- Check time window — rapid failures = automated attack
- Block the source if external

## Screenshot
![Brute Force](/screenshots/bruteforce.png)

# Sysmon Installation

## Download
- Sysmon: https://learn.microsoft.com/en-us/sysinternals/downloads/sysmon
- Config: https://github.com/SwiftOnSecurity/sysmon-config

## Install
```powershell
.\Sysmon64.exe -accepteula -i sysmonconfig-export.xml
```

## Verify
```powershell
Get-Service Sysmon64
```

## Key Event IDs
| ID | Description |
|---|---|
| 1 | Process Creation |
| 3 | Network Connection |
| 11 | File Created |
| 22 | DNS Query |

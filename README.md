# SIEM Lab - Threat Detection with Splunk
![Splunk](https://img.shields.io/badge/Splunk-000000?style=for-the-badge&logo=splunk&logoColor=white)
![Windows](https://img.shields.io/badge/Windows-0078D6?style=for-the-badge&logo=windows&logoColor=white)
![Linux](https://img.shields.io/badge/Linux-FCC624?style=for-the-badge&logo=linux&logoColor=black)
![VirtualBox](https://img.shields.io/badge/VirtualBox-183A61?style=for-the-badge&logo=virtualbox&logoColor=white)
![MITRE ATT&CK](https://img.shields.io/badge/MITRE%20ATT%26CK-FF0000?style=for-the-badge&logoColor=white)

## Overview
A home lab simulating a real Security Operations Center (SOC) environment. 
Built using Splunk Enterprise to ingest, detect, and alert on Windows and Linux security events.

## Lab Architecture
| Component | Details |
|---|---|
| SIEM | Splunk Enterprise 10.2 |
| Windows Host | Laptop 1 (16GB RAM) — direct install |
| Linux Host | Ubuntu 25.10 VM (VirtualBox) |
| Log Forwarder | Splunk Universal Forwarder + rsyslog |

## Log Sources
- Windows Security Event Logs (EventCode 4625, 4720, 4732, 4688)
- Sysmon Telemetry (Process creation, network, file events)
- Linux Auth Logs via rsyslog UDP 514

## Attacks Simulated
| Attack | Tool Used |
|---|---|
| Brute Force | PowerShell credential loop |
| Suspicious PowerShell | Encoded commands, hidden window |
| New User Creation | net user /add |
| Privilege Escalation | net localgroup administrators /add |
| Suspicious CMD | whoami, ipconfig, net user |
| Linux Failed Auth | su - fakeuser |
| Linux Sudo Abuse | sudo cat /etc/shadow |

## Detections Built (Splunk Alerts)
1. Brute Force Detection — EventCode 4625 > 5 times
2. Suspicious PowerShell — hidden/encoded commands
3. New User Account Created — EventCode 4720
4. Privilege Escalation — EventCode 4732
5. Suspicious CMD Process Creation — cmd.exe with recon commands
6. Linux Failed Authentication — auth failure keywords
7. Linux Sudo Usage — sudo keyword in syslog

## Dashboard
SOC Monitoring Dashboard with 7 panels covering all detection categories.
[View SOC Dashboard PDF](screenshots/soc-dashboard.pdf)

## Tools Used
- Splunk Enterprise 10.2
- Splunk Universal Forwarder
- Sysmon v15 (SwiftOnSecurity config)
- VirtualBox
- Ubuntu 25.10
- rsyslog

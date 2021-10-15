# Windows Event Logs

## Useful links
- [https://www.loggly.com/ultimate-guide/windows-logging-basics/](https://www.loggly.com/ultimate-guide/windows-logging-basics/)
- Windows security log events - [https://www.ultimatewindowssecurity.com/securitylog/encyclopedia/default.aspx](https://www.ultimatewindowssecurity.com/securitylog/encyclopedia/default.aspx)

1. Location : `C:\Windows\System32\winevt\Logs` 
2. Extensions : `Logs*.evtx` `Config*.evt`
3. Accessing logs
- Event Viewer (eventvwr.msc) (GUI)
- Wevtutil.exe (CLI)
- Get-WinEvent (powershell)
4. [Types of events](https://docs.microsoft.com/en-us/windows/win32/eventlog/event-types)
- Error, Warning, Information, Sucess Audit, Failure Audit
5. Powershell logs `Applications and Services Logs > Microsoft > Windows > PowerShell > Operational`
6. Custom Views - `Event Viewer > Custom Views > Right Click > Create custom view`
7. Security Logs - `Event Viewer > Windows Logs > Security`

### wevtutil.exe
- wevtutil qe /?
- Query event logs CLI
- wevtutil.exe [Microsoft docs](https://docs.microsoft.com/en-us/windows-server/administration/windows-commands/wevtutil)
- `wevtutil qe Application /c:1 /rd:true /f:text`
  - /RD is Direction, false = most recent
  - /c is count

### Get-WinEvent
- `Get-WinEvent -LogName Application | Where-Object { $_.ProviderName -Match 'WLMS' }`
- List providers `Get-WinEvent -ListProvider *` `(Get-WinEvent -ListLog Application).ProviderNames`
- [Powershell help ms docs] (https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.diagnostics/get-winevent?view=powershell-5.1)`$Event = Get-WinEvent -LogName 'Windows PowerShell' ; $Event.Count ; `

TryHackMe [windows event logs](https://tryhackme.com/room/windowseventlogs) room

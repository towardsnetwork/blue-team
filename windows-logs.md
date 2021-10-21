* Windows Event Logs
* Syslog
  * UDP 514 (default), TCP 514
  * Generally switches, routers, firewalls, end points use this system to send event or system log to syslog server.
  * Syslog has no auth or encryption by default
  * Has 3 parts Priority Value (PRI), Header, Message
  * Available on unix based systems and web servers
* Sysmon
  * Windows event logs are a headache and sysmon is better for logging
  * Sysmon configurations [https://github.com/SwiftOnSecurity/sysmon-config](https://github.com/SwiftOnSecurity/sysmon-config)

## Windows Event Logs
- [https://www.loggly.com/ultimate-guide/windows-logging-basics/](https://www.loggly.com/ultimate-guide/windows-logging-basics/)
- Windows security log events - [https://www.ultimatewindowssecurity.com/securitylog/encyclopedia/default.aspx](https://www.ultimatewindowssecurity.com/securitylog/encyclopedia/default.aspx)

* Location : `C:\Windows\System32\winevt\Logs` 
* Extensions : `Logs*.evtx` `Config*.evt`
* Accessing logs
  * Event Viewer (eventvwr.msc) (GUI)
  * Wevtutil.exe (CLI)
  * Get-WinEvent (powershell)
*  [Types of events](https://docs.microsoft.com/en-us/windows/win32/eventlog/event-types)
  * Error, Warning, Information, Sucess Audit, Failure Audit
* Powershell logs `Applications and Services Logs > Microsoft > Windows > PowerShell > Operational`
* Custom Views - `Event Viewer > Custom Views > Right Click > Create custom view`
* Security Logs - `Event Viewer > Windows Logs > Security`

### wevtutil.exe
- wevtutil qe /?
- Query event logs CLI
- wevtutil.exe [Microsoft docs](https://docs.microsoft.com/en-us/windows-server/administration/windows-commands/wevtutil)
- `wevtutil qe Application /c:1 /rd:true /f:text`
  * /RD is Direction, false = most recent
  * /c is count

### Get-WinEvent
- `Get-WinEvent -LogName Application | Where-Object { $_.ProviderName -Match 'WLMS' }`
- List providers `Get-WinEvent -ListProvider *` `(Get-WinEvent -ListLog Application).ProviderNames`
- [Powershell help ms docs](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.diagnostics/get-winevent?view=powershell-5.1) `$Event = Get-WinEvent -LogName 'Windows PowerShell' ; $Event.Count ;`

TryHackMe [windows event logs](https://tryhackme.com/room/windowseventlogs) room

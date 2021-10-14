# Windows Event Logs

## Useful links
- [https://www.loggly.com/ultimate-guide/windows-logging-basics/](https://www.loggly.com/ultimate-guide/windows-logging-basics/)

1. Location : `C:\Windows\System32\winevt\Logs` 
2. Extensions : `Logs*.evtx` `Config*.evt`
3. Accessing logs
- Event Viewer (eventvwr.msc) (GUI)
- Wevtutil.exe (CLI)
- Get-WinEvent (powershell)
4. [Types of events](https://docs.microsoft.com/en-us/windows/win32/eventlog/event-types)
- Error, Warning, Information, Sucess Audit, Failure Audit
5. Powershell logs `Applications and Services Logs > > Microsoft > Windows > PowerShell > Operational`
TryHackMe [windows event logs](https://tryhackme.com/room/windowseventlogs) room

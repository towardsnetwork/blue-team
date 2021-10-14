# Blue Team resources
## The Defender guide

### Incident Handling and Response

### Threat Intelligence

### Digital Forensics

### Important notes
* [Splunk notes](https://towards.network/blue-team/splunk)
* [TCPDump](https://towards.network/blue-team/tcpdump)
* [Wireshark](https://towards.network/blue-team/wireshark)

### Logs
1. Windows event logs [notes](https://towards.network/blue-team/windows-event-logs)
2. Syslog
  -   UDP 514 (default), TCP 514
  - Generally switches, routers, firewalls, end points use this system to send event or system log to syslog server.
  - Syslog has no auth or encryption by default
  - Has 3 parts Priority Value (PRI), Header, Message
  - Available on unix based systems and web servers
3. Sysmon
  - Windows event logs are a headache and sysmon is better for logging
  - Sysmon configurations [https://github.com/SwiftOnSecurity/sysmon-config](https://github.com/SwiftOnSecurity/sysmon-config)
  - 

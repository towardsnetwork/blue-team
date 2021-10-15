# SIEM

# Splunk
Splunk cheatsheet and resources are at [https://towards.network/blue-team/splunk](https://towards.network/blue-team/splunk)

# Sigma
### Sigma [github](https://github.com/SigmaHQ/sigma)
### SIEM query translator (sigma -> splunk or Azure sentinel) [uncoder.io](https://uncoder.io)
- Sigma is a generic and open signature format that allows you to describe relevant log events in a straightforward way
- Sigma Format -> Sigma converter -> Splunk|Elasticsearch|QRadar|ArcSight|Logpoint quries
- Sigma rules are written in YAML 
- Few sigma rules example to get started are on github [https://github.com/SigmaHQ/sigma/tree/master/rules](https://github.com/SigmaHQ/sigma/tree/master/rules)
- Eg: Generate splunk query to log whoami execution 
  - `sigmac -t splunk -c tools/config/generic/sysmon.yml ./rules/windows/process_creation/win_susp_whoami.yml`

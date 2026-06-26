### Short overview
Unauthorized access was detected on a workstation, followed by privilege escalation, creation of a new administrative account, and persistence via scheduled task execution of a malicious executable.
### Initial access
Login from unknown device using valid credentials
### Execution
Powershell was launched after accessing
### Privilege escalation
Adding a new administrative user
### Persistence
Executing scheduled malicious file
### MITRE ATT&CK MAPPING
T1078.001 - accessing via local account
T1059.001 - commands executed through powershell
T1136.001 - local user add
T1053.005 - scheduled task created
Т1098 - privilige escalated
### Conlusion
Attack indicated with using stolen credentials and further privilege escalation and persistence via scheduling malicious excutable

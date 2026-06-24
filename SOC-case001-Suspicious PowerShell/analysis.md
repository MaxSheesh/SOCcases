### Incident analysis
## Overview
A user received a phishing email containing a malicious .docm file. After opening it and enabling macros, PowerShell was executed, which downloaded and ran a suspicious payload, leading to external network connections.

## Attack chain
- Step 1: User opened a malicious .docm file
- Step 2: The document executed a malicious macro that triggered PowerShell
- Step 3: A suspicious file (AdobeUpdater.exe) was downloaded from an external source
- Step 4: The downloaded file was executed and established persistence on the system

## Why is it malicious?

- .docm files can contain macros, which are capable of executing system commands such as PowerShell
- A suspicious file was downloaded and executed from an external source
- The system attempted connections to external IP addresses and domains, some of which were blocked (see proxy logs)
## MITRE ATTACK MAP
T1566.001 – Phishing: Spearphishing Attachment
T1204.002 – User Execution: Malicious File
T1059.001 – Command and Scripting Interpreter: PowerShell
T1059.005 – Command and Scripting Interpreter: Visual Basic (VBA macros)
T1105 – Ingress Tool Transfer
T1547.001 – Boot or Logon Autostart Execution (likely persistence method)
## Conclusion
Overall we were dealing with with .docm file,that contained dangerous macroses, which executed malicious code and downloaded suspicious file that got laucnched after and led to external connection

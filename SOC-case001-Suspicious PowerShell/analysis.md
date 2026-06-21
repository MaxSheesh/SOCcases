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

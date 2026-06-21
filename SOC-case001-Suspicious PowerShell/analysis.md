### Incident analysis
## Overview
A user received a phishing email containing a malicious .docm file. After opening it and enabling macros, PowerShell was executed, which downloaded and ran a suspicious payload, leading to external network connections.

## Attack chain
- Step 1: User opened a malicious .docm file
- Step 2: The document executed a malicious macro that triggered PowerShell
- Step 3: A suspicious file (AdobeUpdater.exe) was downloaded from an external source
- Step 4: The downloaded file was executed and established persistence on the system

## Why is it malicious?
- .docm files doesn't start shell
- suspicious file got downloaded without system log
- established connection with weird ip's and domains (check proxy.log)

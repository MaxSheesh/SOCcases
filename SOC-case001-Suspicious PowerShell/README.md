# Case-001: Suspicious PowerShell-Based Lateral Movement Detected via SMB Authentication Attempts

# Case-001: Phishing Leading to Malware Execution

## Incident Type
Phishing / Malware Infection

## Summary
A phishing email delivered a malicious .docm file that resulted in PowerShell execution and suspected malware download.

## Impact
- One workstation affected
- Suspicious process execution observed
- Possible external communication to C2 infrastructure

## Detection
Detected by Microsoft Defender for Endpoint due to abnormal PowerShell execution spawned from WINWORD.exe.

## Status
Contained and isolated by security team.

## 🧠 Attack Summary
Initial compromise appears to have been used to perform internal reconnaissance and attempt lateral movement via SMB authentication abuse.

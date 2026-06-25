# Incident Overview

## Summary
Suspicious activity was detected on endpoint J-SMITH-PC associated with user j.smith. Execution was observed via Windows Script Host (wscript.exe) running a JavaScript file, which spawned an obfuscated PowerShell process. The behavior included encoded command execution and attempted outbound communication to an external IP.

EDR detected the activity and isolated the host, preventing further propagation.

---

## Impact
- Asset: J-SMITH-PC
- User: j.smith
- Lateral Movement: None observed
- Exfiltration: None confirmed
- Status: Contained

---

## Key Observations
- Vector: Script download/execution (JavaScript via wscript.exe)
- Process chain: explorer.exe → wscript.exe → powershell.exe
- Behavior: encoded PowerShell execution (obfuscation detected)
- Network: outbound connection attempt to 185.220.101.45
- Artifacts: temporary file created in AppData\Local\Temp

---

## Response
- EDR: endpoint isolated automatically
- SIEM: alert triggered and correlated (script execution + network anomaly)
- Firewall: outbound connection flagged and blocked after detection
- Session: active session terminated after containment

---

## Status
Contained****

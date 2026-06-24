## Incident Summary

An endpoint compromise was detected on workstation J-SMITH-PC following execution of a JavaScript file via Windows Script Host. The script spawned PowerShell with obfuscated commands, resulting in suspicious outbound network activity.

EDR telemetry confirmed malicious behavior and successfully contained the host before further propagation.

## Impact
- Single endpoint compromised
- No confirmed lateral movement completed
- External communication attempt blocked/contained

## Key Observations
- Script-based execution chain (wscript → powershell)
- Obfuscated PowerShell payload
- Beaconing to external IP

## Outcome
Incident contained via EDR isolation. No further spread detected.

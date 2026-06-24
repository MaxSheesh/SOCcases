### TIMELINE OF EVENTS
1. 03:41:12 – User login detected: j.smith from 10.0.0.15
2. 03:41:50 – ALLOW 10.0.0.15 → INTERNET TCP/443
3. 03:42:09 – Obfuscated PowerShell command detected
4. 03:42:10 – PowerShell spawned from abnormal parent process (wscript.exe)
5. 03:42:50 – DNS query: cdn-update[.]net
6. 03:42:52 – ALLOW OUTBOUND 91.219.236.44 TCP/443
7. 03:43:02 – ALERT: Outbound connection to suspicious IP 91.219.236.44
8. 03:43:07 – RESPONSE: Endpoint isolated
9. 03:43:10 – ALERT: Repeated outbound beaconing pattern detected
10. 03:43:12 – BLOCK enforced after EDR containment signal
11. 03:43:20 – DNS query: telemetry-check[.]org
12. 03:44:10 - ALERT Similar behavior detected on additional endpoint HR-PC-02
### INITIAL ACCESS VECTOR
10.0.0.15 started the attack
### EXECUTION CHAIN
Connection to j.smith from 10.0.0.15 > obsufucated powershell command > created wscript.exe > dns query cdn-update.net > connection to suspicious IP 91.219.236.44 > endpoint isolated > repeated outbound beaconing > blocked > dns query telemetry-check.org > File Create
TargetFilename: C:\Users\j.smith\AppData\Roaming\update.dat > alert similar behavior detected on additional endpoint
### Indicators of Compromise (IOCs) 
- New login detected from 10.0.0.15
- Obsufucated powershell command
- suspicious payload wscript.exe
- Connection to 91.219.236.44 (cdn-update.net)
- failed connection telemetry-check.org (host isolated)
- SIEM alert similar behavior on additional endpoint
### Detection logic
Log of obsufucated powershell command detection, spawning abnormal process wscript.exe, connection to external ip helped me to detect it
### Conclusion
So overall we dealt with a hacker that executed malicious code through powershell and persistened in system, tried to connect to exeternal ip, but host got isolated by edr and connection was failed and probably hacker also tried to lateral movement through the system, because SIEM detected simillar behaviour on another host

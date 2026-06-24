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

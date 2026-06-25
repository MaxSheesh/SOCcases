### Timeline of Events

1. 14:17:50 - Browser session detected accessing "Work Account - a.ivanov" in Chrome. Cookie exported, session reused outside managed device.
2. 14:17:55 - Firewall allowed connection to Microsoft 365.
3. 14:18:02 - Impossible Travel detected (Kyiv → Frankfurt).
4. 14:18:06 - DNS query to api.sharepoint.com.
5. 14:18:10 - DNS query to outlook.office365.com.
6. 14:18:15 - SharePoint file access spike. User downloaded .pdf, .xlsx, and .docx files.
7. 14:18:20 - Excessive SharePoint File Access alert (1,240 files accessed in 3 minutes).
8. 14:18:40 - Mailbox access pattern changed.
9. 14:18:42 - DNS query to sync-storage[.]com (suspicious domain).
10. 14:19:01 - Suspicious Mailbox Enumeration alert (18,000 mailbox items scanned).
## Initial access vector
Initiator of attack is 185.192.34.77
## Execution chain
1.New session detected from Frankfurt
2.Accesing sharepoint
3.User downloaded sensitive files
4.Excessive sharepoint access detected
5.Pattern changed
6.Dns query to suspicious domain
7.Mailbox scanning
## MITRE ATT&CK MAPPING
T1078.004 – Valid Accounts (Cloud Account compromise via session reuse)
T1134.001 – Token manipulation (optional / low confidence)
T1087.004 – Account Discovery (Cloud)
T1213 – Data from Information Repositories (SharePoint access)
T1114.002 – Email Collection
T1041 – Exfiltration Over C2 Channel (suspected)
## Indicators of Compromise
- User accessed SharePoint and performed bulk download of files
- High volume of file access activity detected
- DNS query to a suspicious domain (sync-storage[.]com)
- Suspicious mailbox enumeration activity observed (large-scale item scanning)
## Conclusion
Overall, this incident is consistent with session/token reuse leading to unauthorized access to Microsoft 365 services. The attacker accessed SharePoint data and performed large-scale mailbox enumeration to identify sensitive information.
Data exfiltration is suspected based on download behavior and interaction with a suspicious external domain, however it is not fully confirmed.

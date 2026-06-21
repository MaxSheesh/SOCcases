# SOCcases
My soc cases, which i solve
TEMPLATE FOR ANALYSIS.MD
# Incident Analysis

## 🧠 Overview
Briefly describe what happened.

Example:
This incident involves a suspected malware infection initiated via a phishing email containing a malicious .docm attachment, leading to PowerShell execution and possible command-and-control (C2) communication.

---

## 🔗 Attack Chain
Describe the sequence of attacker actions step by step:

- [Step 1: Initial access]
- [Step 2: Execution]
- [Step 3: Payload delivery]
- [Step 4: Persistence]
- [Step 5: Lateral movement / C2 communication (if applicable)]

Example:
- Phishing email delivered to user
- User opened malicious .docm file
- Macros executed inside Microsoft Word
- WINWORD.exe spawned PowerShell
- PowerShell downloaded payload from external server
- Malware executed and established persistence

---

## ⚠️ Why This is Malicious
Explain suspicious behavior and why it indicates compromise:

- Unusual process chain (e.g., WINWORD.exe → powershell.exe)
- Execution of macros from Office document
- Encoded or obfuscated PowerShell commands
- Suspicious outbound network connections
- File execution from user-writable directories
- Registry or startup modifications

---

## 🧬 MITRE ATT&CK Mapping
Map observed behavior to MITRE techniques:

- T1566 — Phishing
- T1204 — User Execution
- T1059 — Command and Scripting Interpreter (PowerShell)
- T1105 — Ingress Tool Transfer
- T1547 — Persistence (Registry Run Keys / Startup Folder)

---

## 🌐 Network Activity
Describe network behavior:

- Connections to external IP addresses
- Communication with suspicious or unknown domains
- Possible C2 (Command-and-Control) traffic
- File downloads via HTTP/HTTPS

---

## 🧪 Hypothesis
Explain your interpretation of what likely happened:

Based on the available evidence, the system was likely compromised through a phishing email. The malicious document executed macros, which triggered PowerShell. This resulted in payload download, execution, and potential persistence setup, along with possible external communication.

---

## 📌 Conclusion
Short final summary:

The incident shows clear indicators of malicious activity including phishing, code execution, and potential C2 communication. Further investigation and containment are required.

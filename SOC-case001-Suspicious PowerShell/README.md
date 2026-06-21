# Case-002: Suspicious PowerShell-Based Lateral Movement Detected via SMB Authentication Attempts

## 🧾 Summary
A suspicious PowerShell process was detected executing network discovery and authentication attempts across multiple internal hosts via SMB. The activity originated from a previously compromised workstation and indicated potential lateral movement within the internal network.

---

## 🎯 Incident Type
- Lateral Movement
- Credential Access Attempt
- Internal Reconnaissance

---

## 📊 Impact
- One workstation confirmed as initial compromise point
- Multiple internal hosts targeted via SMB
- Suspicious authentication attempts detected
- Potential credential misuse suspected

---

## 🔍 Detection Method
The incident was detected by Microsoft Defender for Endpoint and SIEM correlation rules identifying:

- PowerShell executing network enumeration commands
- Multiple failed SMB login attempts across internal IP range
- Abnormal process chain involving PowerShell and net commands
- Lateral network scanning behavior

---

## 🛠 Tools Used
- Microsoft Defender for Endpoint
- Microsoft Sentinel (SIEM)
- Windows Security Logs (Event ID 4625 / 4624)
- PowerShell Logging (Script Block Logging)
- Network telemetry (SMB traffic analysis)

---

## 📌 Key Findings
- PowerShell executed network discovery commands
- Multiple internal IP addresses scanned over SMB (port 445)
- Repeated failed authentication attempts observed
- Execution originated from compromised workstation
- Suspicious process chain: powershell.exe → cmd.exe → net.exe
- Possible credential harvesting or reuse attempt

---

## 🖥 Affected Assets

| Asset Type | Value |
|------------|------|
| Source Host | WS-ACC-07 |
| User | john.doe |
| Target Range | 10.0.1.0/24 |
| Suspicious Process | powershell.exe |
| Protocol Used | SMB (port 445) |

---

## 🧠 Attack Summary
Initial compromise appears to have been used to perform internal reconnaissance and attempt lateral movement via SMB authentication abuse.

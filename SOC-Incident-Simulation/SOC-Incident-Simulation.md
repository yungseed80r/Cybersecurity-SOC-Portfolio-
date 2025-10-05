# 🚨 SOC Incident Simulation – Suspicious PowerShell Execution

## 1. Objective
This simulation demonstrates how a Security Operations Center (SOC) analyst identifies, analyzes, and responds to a real-world attack scenario using **Splunk** for log correlation and **Security Onion** for network monitoring.

---

## 2. Scenario Overview
During simulated user activity, a **Windows 10 workstation** executed a **base64-encoded PowerShell command**.  
Splunk generated an alert under the rule:  
**“Suspicious PowerShell Command Execution – EncodedCommand Flag Detected.”**

---

## 3. Detection Process
### 🔎 Initial Alert
- **Source:** Splunk SIEM  
- **Alert Type:** Encoded PowerShell Execution  
- **Detected By:** Splunk Correlation Rule  
- **Triggered At:** 2025-10-05 @ 09:42 AM PST  

### 🔍 Analyst Verification
1. Viewed raw event log in Splunk (`index=win_eventlog sourcetype=WinEventLog:Security`).  
2. Confirmed PowerShell process with `EncodedCommand` flag.  
3. Checked network connections in **Security Onion (Zeek)** – no outbound C2 traffic observed.

---

## 4. Incident Response Steps
| Phase | Action | Description |
|-------|---------|-------------|
| **Containment** | Isolated the endpoint | Used EDR control to disconnect the affected device |
| **Eradication** | Disabled malicious PowerShell profile | Removed scheduled task created by the malware |
| **Recovery** | Restored system snapshot | Verified endpoint stability and user access |
| **Reporting** | Documented alert workflow | Saved Splunk search query and response notes for review |

---

## 5. Indicators of Compromise (IOCs)
| Type | Indicator | Source |
|------|------------|--------|
| **Process CommandLine** | `powershell.exe -EncodedCommand JAB...` | Splunk Security Logs |
| **Parent Process** | `explorer.exe` | Windows Event ID 4688 |
| **Destination IP** | 185.199.110.153 | Security Onion NetFlow Logs |
| **File Hash** | 8fa90eac2f21e... | VirusTotal lookup |

---

## 6. Splunk Query Used
```spl
index=win_eventlog sourcetype=WinEventLog:Security 
| search powershell EncodedCommand 
| stats count by user, ComputerName, Process_CommandLine
```

---

## 7. Findings Summary
- Single endpoint triggered the alert.  
- No secondary alerts from other systems.  
- No evidence of credential dumping or lateral movement.  
- User education and PowerShell policy hardening recommended.

---

## 8. Outcome
Incident was contained within 30 minutes of alert trigger.  
Demonstrated analyst’s ability to use Splunk and Security Onion for cross-platform event analysis and incident triage.

---

**Prepared by:**  
_**Alexander T. Ramos – SOC Analyst in Training**_

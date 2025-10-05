# ⚙️ Incident Response Technical Simulation

## 1. Scenario Overview
**Incident Type:** Phishing email leading to credential theft and malware installation  
**Date/Time:** October 4, 2025  
**Environment:** Windows 10 endpoint connected to corporate domain  
**Detection Source:** Splunk SIEM alert triggered by unusual PowerShell activity (Event ID 4104)

---

## 2. Initial Detection
At 09:13 AM, a Splunk alert flagged suspicious PowerShell execution under user `jsmith@corp.local`.  
Correlated events indicated a base64-encoded command attempting to connect to an external IP (45.199.200.32) over HTTPS.

**Indicators of Compromise (IOCs):**
| Type | Value | Description |
|------|--------|--------------|
| URL | `https://microsoft-update-checks.com` | Fake Microsoft update domain |
| File Hash | `6acb82e2f92e3...` | Dropped payload (malware executable) |
| IP | `45.199.200.32` | C2 Server (Command & Control) |

---

## 3. Triage & Analysis
- Pulled endpoint event logs from affected machine (`WIN10-ENG-JSMITH`).  
- Verified user received a phishing email with spoofed Microsoft subject line.  
- PowerShell transcript revealed encoded command fetching a payload from the malicious site.  
- Confirmed outbound connection to C2 IP via proxy logs.  
- Sandbox detonation classified payload as **AgentTesla (Keylogger/Stealer)**.

---

## 4. Containment Actions
1. Disconnected endpoint from corporate network (via EDR command).  
2. Disabled compromised AD account.  
3. Blocked IP `45.199.200.32` and domain at the firewall and proxy layers.  
4. Quarantined infected files for forensics.

---

## 5. Eradication & Recovery
- Ran full Defender AV scan and removed residual malicious artifacts.  
- Verified PowerShell execution policies were reverted to defaults.  
- Rotated user and service account credentials.  
- Reimaged endpoint and restored from backup.  
- Applied OS and software patches post-cleanup.

---

## 6. Lessons Learned
- Implement stricter PowerShell logging and constrained language mode.  
- Improve phishing simulation training across departments.  
- Enable real-time alerting on encoded PowerShell command usage.  
- Add automatic blocking of known malicious domains in EDR.

---

## 7. Outcome Summary
**Incident Contained:** Yes  
**Data Exfiltration:** None detected  
**Root Cause:** User opened phishing attachment (malicious PowerShell dropper)  
**Duration from Detection to Recovery:** ~5 hours  
**Severity Level:** High  

---

**Prepared by:**  
_**Alexander T. Ramos – Cybersecurity Analyst**_  


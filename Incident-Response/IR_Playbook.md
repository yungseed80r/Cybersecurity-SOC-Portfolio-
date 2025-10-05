# 🚨 Incident Response Playbook

## 1. Objective
To provide a structured framework for responding to cybersecurity incidents efficiently and consistently, minimizing damage and recovery time.

---

## 2. Incident Response Framework (NIST 800-61)

| Phase | Objective | Key Activities |
|-------|------------|----------------|
| **Preparation** | Ensure readiness through planning and resources. | Develop IR policy, define roles, train staff, and configure monitoring tools. |
| **Identification** | Detect and validate potential security incidents. | Monitor SIEM alerts, verify IOCs, collect system and network logs. |
| **Containment** | Limit the scope and impact of the incident. | Isolate affected systems, disable compromised accounts, block malicious IPs. |
| **Eradication** | Eliminate the root cause and related artifacts. | Remove malware, patch systems, update signatures, harden configurations. |
| **Recovery** | Restore affected systems to normal operation. | Reimage systems, restore from clean backups, validate normal operations. |
| **Lessons Learned** | Improve future responses. | Conduct after-action review, document findings, update playbook. |

---

## 3. Roles and Responsibilities
| Role | Responsibility |
|------|----------------|
| **Incident Commander** | Oversees the entire incident response lifecycle. |
| **SOC Analyst (Tier 1–2)** | Detects, investigates, and escalates security alerts. |
| **Forensics Lead** | Performs evidence collection and malware analysis. |
| **IT/System Admin** | Restores systems, applies patches, and validates fixes. |
| **Communications Lead** | Coordinates updates to management and legal teams. |

---

## 4. Communication Procedures
- Use a **dedicated incident channel** (Slack/Teams) for real-time coordination.  
- Escalate according to severity:
  - Tier 1 Analyst → SOC Lead → IR Manager → Executive Management.  
- Notify external parties (Legal, Law Enforcement, Regulators) as required.

---

## 5. Incident Severity Classification
| Severity | Description | Response Time |
|-----------|--------------|----------------|
| **Critical (P1)** | Active exploitation or data breach. | Immediate |
| **High (P2)** | Widespread infection or privilege escalation. | Within 2 hours |
| **Medium (P3)** | Contained malware or limited unauthorized access. | Within 24 hours |
| **Low (P4)** | Suspicious event with low impact. | Within 48 hours |

---

## 6. Tools & Data Sources
- SIEM: Splunk / Sentinel  
- EDR: CrowdStrike / Defender ATP  
- Forensics: FTK Imager, Autopsy, Wireshark  
- Threat Intelligence: AlienVault OTX, VirusTotal  
- Ticketing: ServiceNow / Jira  

---

## 7. Post-Incident Review Checklist
- ✅ Verify eradication and recovery steps are complete  
- ✅ Conduct lessons-learned session  
- ✅ Archive evidence securely  
- ✅ Update detection rules and signatures  
- ✅ Revise playbook as necessary  

---

**Prepared by:**  
_**Alexander T. Ramos – Cybersecurity Analyst**_  

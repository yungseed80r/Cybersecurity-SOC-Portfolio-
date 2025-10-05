## 🧰 Home Security Lab Setup Guide

## 1. Objective
This lab replicates a small-scale corporate network to safely practice cybersecurity operations — including penetration testing, vulnerability management, and SOC monitoring.  
It demonstrates both **technical implementation** and **defensive response workflows** that align with real-world job responsibilities.

---

## 2. Host & Hardware Overview
| Component | Specification |
|------------|---------------|
| **Primary Host Machine** | 2015 iMac 27” (macOS Ventura) |
| **Secondary System** | Windows 10 Professional Laptop |
| **Virtualization Tool** | Oracle VirtualBox 7.0 |
| **Display Setup** | Dual monitor with Thunderbolt connection |
| **External Tools** | USB storage for snapshots, Conroe HD 13” tablet for monitoring dashboards |

---

## 3. Virtual Machine Environment
| VM | OS | Function | Key Tools |
|----|----|-----------|-----------|
| **Kali Linux** | Debian | Offensive testing & ethical hacking | Metasploit, Nmap, Wireshark, Burp Suite |
| **Metasploitable 2** | Ubuntu | Vulnerable target for pentesting | FTP, Telnet, MySQL, Apache (intentionally vulnerable) |
| **Windows 10 Lab** | Windows 10 | SOC simulation & malware analysis | Sysinternals Suite, Splunk Forwarder, Wireshark |
| **Security Onion** | Ubuntu | IDS/IPS & SIEM platform | Zeek, Suricata, Wazuh, Elastic Stack |
| **Ubuntu Server (DVWA)** | Ubuntu 22.04 | Web app testing | DVWA, Apache2, OpenVAS, Nikto |

---

## 4. Network Topology
- **NAT Network:** Internet access for updates and research  
- **Internal Network:** Isolated testing network for safe attack simulation  
- **Host-Only Adapter:** Enables VM-to-host monitoring without external exposure  

🗺️ *See accompanying `Network_Topology.png` for a visual layout.*

---

## 5. Tools Installed
- **VirtualBox 7.0** – Virtualization platform  
- **Splunk Free / ELK Stack** – Log collection and visualization  
- **Security Onion** – Network monitoring and intrusion detection  
- **Nessus Essentials / OpenVAS** – Vulnerability scanning  
- **Metasploit Framework** – Exploit testing and payload simulation  
- **Wireshark / Zeek** – Deep packet inspection  
- **DVWA** – Web application testing sandbox  

---

## 6. Lab Scenarios
| Scenario | Description |
|-----------|-------------|
| **Phishing Simulation** | Simulate malicious email delivery and analyze logs in Security Onion |
| **Brute Force Attack** | Launch controlled brute force attempts from Kali to Metasploitable |
| **Malware Analysis** | Detonate sample malware on Windows Lab using Sysinternals tools |
| **Vulnerability Scan** | Perform network scanning with Nessus/OpenVAS and document findings |
| **SIEM Log Correlation** | Ingest event logs from all systems into Splunk dashboards for alert correlation |

---

## 7. Security Controls
- VLAN isolation for internal testing  
- Strict host-only network policies  
- Regular snapshots before high-risk testing  
- Centralized logging via Splunk  
- EDR/AV monitoring on host systems  

---

## 8. Maintenance
- Perform monthly OS updates for each VM.  
- Revert to clean snapshot after every experiment.  
- Maintain documented changelog in GitHub for reproducibility.  
- Regularly test logging pipelines and alert rules.

---

## 9. Outcome
This lab demonstrates practical security competencies such as:
- Threat detection and log correlation  
- Vulnerability analysis  
- Network forensics and intrusion detection  
- Ethical hacking techniques  
- Report documentation and remediation planning  

---

**Prepared by:**  
_**Alexander T. Ramos – Cybersecurity Analyst**_


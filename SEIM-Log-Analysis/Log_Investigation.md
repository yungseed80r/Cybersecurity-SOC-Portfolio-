# SIEM Log Analysis: Brute Force Investigation  
**Analyst:** Alexander T. Ramos  
**Date:** 09-17-2025  

---

## 🧠 Objective  
Investigate a series of failed login attempts detected on a Windows Server and determine if a brute force attack occurred.  

---

## 🧩 Data Source  
- **SIEM Platform:** Splunk (simulated data)
- **Log Type:** Windows Event Logs  
- **Event IDs Analyzed:**  
  - 4625 (Failed logon)  
  - 4624 (Successful logon)  
  - 4720 (User account created)  

---

## 🧰 Investigation Steps  

1. **Query Construction**  


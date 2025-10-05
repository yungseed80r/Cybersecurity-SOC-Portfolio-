# 🧩 Phishing Email Analysis

## Overview
A suspicious email was reported by a company employee claiming to come from the IT department. The message urged the user to “reset their password” using a provided link. The purpose of this analysis is to review the email header, identify malicious indicators, and provide mitigation recommendations.

---

## Email Header Analysis
| Field | Observed Data | Notes |
|-------|----------------|-------|
| From | IT Support <ithelpdesk@securehelpdesk.info> | Sender domain does not match internal IT domain. |
| Reply-To | ithelpdesk@securehelpdesk.info | Suspicious – not a corporate address. |
| Return-Path | ithelpdesk@securehelpdesk.info | Same as “From,” indicates spoofing attempt. |
| Subject | "Password Expiration Notice - Action Required" | Common phishing subject line. |
| Received IP | 185.244.25.101 | Foreign IP address, not associated with company servers. |

---

## Suspicious Link Observed
The phishing email contained the following URL:

https://securehelpdesk.info/login/update-password



**Analysis:**
- Domain `securehelpdesk.info` is newly registered (checked via WHOIS).
- URL path mimics a legitimate IT helpdesk login portal.
- VirusTotal scan shows the domain flagged for phishing.

---

## Indicators of Compromise (IOCs)

| Type | Indicator | Description |
|------|------------|--------------|
| Domain | securehelpdesk.info | Fake IT domain used in phishing. |
| IP | 185.244.25.101 | Hosting server for phishing page. |
| URL | https://securehelpdesk.info/login/update-password | Redirect link for credential harvesting. |
| Email Address | ithelpdesk@securehelpdesk.info | Spoofed sender identity. |

---

## Recommended Mitigations
1. Block listed IOCs at the email and network gateway.
2. Alert employees via security awareness channels.
3. Check logs for any user who accessed the phishing URL.
4. Enforce MFA (Multi-Factor Authentication) across all user accounts.
5. Report domain to hosting provider and phishing database.

---

## Summary
The phishing email was a credential-harvesting attempt using a fake IT Helpdesk pretext. Indicators confirm a malicious domain and spoofed sender identity.  
**Result:** Blocked at gateway; no user compromise detected.

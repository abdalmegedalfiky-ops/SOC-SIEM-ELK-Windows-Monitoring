# 🛡️ MITRE ATT&CK Mapping

This document maps the detection rules in this SIEM project 
to the MITRE ATT&CK Framework.

---

## 🔴 Brute Force — T1110
**Tactic:** Credential Access  
**Detection:** Event ID 4625 (Failed Logon)  
**Query:**
```kql
event.code: "4625"
```
**Response:** Block IP after 5 failed attempts in 1 minute.

---

## 🟢 Valid Accounts — T1078
**Tactic:** Defense Evasion / Persistence  
**Detection:** Event ID 4624 (Successful Logon)  
**Query:**
```kql
event.code: "4624"
```
**Response:** Monitor for logins outside business hours.

---

## 🟡 Privilege Escalation — T1068
**Tactic:** Privilege Escalation  
**Detection:** Event ID 4672 (Special Privileges Assigned)  
**Query:**
```kql
event.code: "4672"
```
**Response:** Alert on unexpected privilege assignments.

---

## 🔵 Create Account — T1136
**Tactic:** Persistence  
**Detection:** Event ID 4720 (User Account Created)  
**Query:**
```kql
event.code: "4720"
```
**Response:** Immediate alert — verify with HR/IT team.

---

## ⚫ Account Lockout — T1531
**Tactic:** Impact  
**Detection:** Event ID 4740 (Account Locked Out)  
**Query:**
```kql
event.code: "4740"
```
**Response:** Investigate source IP for brute force activity.

---

## 📊 ATT&CK Coverage Summary

| Tactic | Technique | Event ID | Status |
|--------|-----------|----------|--------|
| Credential Access | T1110 - Brute Force | 4625 | ✅ Detected |
| Defense Evasion | T1078 - Valid Accounts | 4624 | ✅ Detected |
| Privilege Escalation | T1068 | 4672 | ✅ Detected |
| Persistence | T1136 - Create Account | 4720 | ✅ Detected |
| Impact | T1531 - Account Access Removal | 4740 | ✅ Detected |

---

## 🔗 References
- [MITRE ATT&CK Framework](https://attack.mitre.org)
- [Windows Security Event IDs](https://docs.microsoft.com/en-us/windows/security/threat-protection/auditing/security-auditing-overview)

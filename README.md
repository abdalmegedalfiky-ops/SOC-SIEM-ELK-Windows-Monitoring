# 🔐 ELK SIEM Project – Real-Time Security Monitoring & Threat Detection

## 📌 Overview

This project demonstrates the design and implementation of a fully functional SIEM solution using the ELK Stack. It simulates a real Security Operations Center (SOC) environment by collecting, analyzing, and detecting security events from Windows endpoints in real time.

The system leverages Filebeat and Elastic Agent to ingest logs, enabling continuous monitoring, threat detection, and basic incident investigation.

---

## 🏗️ Architecture

Endpoint (Windows) → Filebeat / Elastic Agent → Elasticsearch → Kibana

---

## ⚙️ Components

* Elasticsearch 9.3.3 – Data storage and indexing
* Kibana 9.3.3 – Visualization and analysis
* Filebeat 9.3.3 – Log shipping agent
* Elastic Agent 9.3.3 – Unified data collection

---

## 🚀 Key Capabilities

* Real-time log ingestion and indexing
* Security event monitoring from Windows systems
* Detection of suspicious and malicious activities
* Interactive dashboards and visualizations
* Basic alerting and incident investigation

---

## 📸 Screenshots

### Kibana Login
![Kibana Login](screenshots/Screenshot%202026-04-26%20070650.png)

### Kibana Home
![Kibana Home](screenshots/Screenshot%202026-04-26%20070820.png)

### Discover - Live Logs (16,858 Documents)
![Discover](screenshots/Screenshot%202026-04-26%20071118.png)

### Alerts - Brute Force Detection
![Alerts](screenshots/Screenshot%202026-04-26%20071205.png)


---

## 🔴 Detection Rules & Logic

### 1. Brute Force Detection

* Event ID: 4625
* Logic: Multiple failed login attempts within a short time window
* Detection Goal: Identify password guessing attacks

---

### 2. Successful Login Monitoring

* Event ID: 4624
* Logic: Track user authentication activity
* Detection Goal: Detect unusual login behavior

---

### 3. Privilege Escalation Detection

* Event ID: 4672
* Logic: Monitor assignment of administrative privileges
* Detection Goal: Identify unauthorized privilege elevation

---

### 4. New Account Creation

* Event ID: 4720
* Logic: Detect creation of new user accounts
* Detection Goal: Identify persistence mechanisms

---

### 5. Account Lockout Monitoring

* Event ID: 4740
* Logic: Detect locked accounts after multiple failures
* Detection Goal: Identify attack impact or brute force success

---

## 🛡️ Use Cases

### 🔴 Brute Force Attack Simulation

Simulated repeated failed login attempts to validate detection capabilities using Event ID 4625.

### 🟡 Lateral Movement Monitoring

Tracked authentication events across users and systems to identify suspicious movement.

### 🔵 Privilege Abuse Detection

Monitored high-privilege logins and admin privilege assignments.

---

## 🧠 Threat Hunting Queries (KQL)

```kql
event.code:4625
```

```kql
event.code:4624 AND NOT winlog.event_data.LogonType:5
```

```kql
event.code:4672
```

```kql
event.code:4720
```

```kql
event.code:4740
```

---

## 🛡️ MITRE ATT&CK Mapping

| Tactic               | Technique               | Event ID | Detection |
| -------------------- | ----------------------- | -------- | --------- |
| Credential Access    | T1110 - Brute Force     | 4625     | ✅         |
| Defense Evasion      | T1078 - Valid Accounts  | 4624     | ✅         |
| Privilege Escalation | T1068                   | 4672     | ✅         |
| Persistence          | T1136 - Create Account  | 4720     | ✅         |
| Impact               | T1531 - Account Lockout | 4740     | ✅         |

📁 Full mapping available in: `docs/mitre-attack-mapping.md`

---

## 📊 Dashboards & Visualizations

* Failed login attempts over time
* Top targeted usernames
* Source IP analysis
* Privileged account activity
* Event distribution by type

---

## 🚨 Alerts & Monitoring

Configured detection rules to trigger alerts based on:

* High frequency of failed logins
* Privileged access events
* Suspicious account behavior

---

## 🔍 Incident Scenario (SOC Simulation)

### Scenario: Brute Force Attack

* Multiple failed login attempts detected (Event ID 4625)
* Alert triggered in Kibana
* Correlated with account lockout event (4740)
* Investigation performed via Discover and dashboards

---

## 🎯 Key Learnings

* SIEM architecture design and implementation
* Log ingestion and normalization
* Detection engineering fundamentals
* Threat hunting using KQL
* Security monitoring and analysis

---

## 🚀 Future Improvements

* Integrate threat intelligence feeds
* Add automated alerting workflows
* Implement advanced correlation rules
* Deploy SIEM in cloud environment
* Integrate with SOAR for automation

---

## 👨‍💻 Author

Abdalmegeed Alfiky

---

## 🏷️ Tags

SIEM • ELK Stack • SOC • Cybersecurity • Threat Detection • Log Analysis

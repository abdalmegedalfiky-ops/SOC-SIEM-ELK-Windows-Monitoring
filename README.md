# 🔐 ELK SIEM Project

A fully functional SIEM built with ELK Stack to detect and analyze security events in real time.

## 🏗️ Architecture
Filebeat → Elasticsearch → Kibana

## ⚙️ Components
- Elasticsearch 9.3.3
- Kibana 9.3.3
- Filebeat 9.3.3
- Elastic Agent 9.3.3

## 📸 Screenshots

### Kibana Login
![Kibana Login](screenshots/Screenshot%202026-04-26%20070650.png)

### Kibana Home
![Kibana Home](screenshots/Screenshot%202026-04-26%20070820.png)

### Discover - Live Logs (16,858 Documents)
![Discover](screenshots/Screenshot%202026-04-26%20071118.png)

### Alerts - Brute Force Detection
![Alerts](screenshots/Screenshot%202026-04-26%20071205.png)

## 🔴 Detection Rules
| Event ID | Description          |
|----------|----------------------|
| 4625     | Failed Login         |
| 4624     | Successful Login     |
| 4672     | Privilege Escalation |
| 4720     | New User Created     |
| 4740     | Account Lockout      |

## 🛡️ Use Cases
- Brute Force Detection
- Lateral Movement Monitoring
- Privilege Escalation Alerts

## 🏷️ Tags
`SIEM` `ELK Stack` `Cybersecurity` `SOC` `Log Analysis`

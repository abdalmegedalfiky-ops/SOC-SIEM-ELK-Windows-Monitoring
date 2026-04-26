# 🔐 ELK SIEM Project

A fully functional SIEM built with ELK Stack to detect and analyze security events in real time.

## 🏗️ Architecture
Filebeat → Elasticsearch → Kibana

## ⚙️ Components
- Elasticsearch 9.3.3
- Kibana 9.3.3
- Filebeat 9.3.3
- Elastic Agent 9.3.3

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

## 🚀 Setup
1. Install ELK Stack
2. Configure Elasticsearch
3. Configure Filebeat
4. Open Kibana Dashboard

## 🏷️ Tags
`SIEM` `ELK Stack` `Cybersecurity` `SOC` `Log Analysis`

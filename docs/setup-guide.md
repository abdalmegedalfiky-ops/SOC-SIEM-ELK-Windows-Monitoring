# 📖 ELK SIEM Setup Guide

## Prerequisites
- Ubuntu 20.04 or later
- Minimum 8GB RAM
- Java 11+

## 1. Install Elasticsearch
```bash
wget -qO - https://artifacts.elastic.co/GPG-KEY-elasticsearch | sudo apt-key add -
sudo apt install elasticsearch
sudo systemctl enable elasticsearch
sudo systemctl start elasticsearch
```

## 2. Install Kibana
```bash
sudo apt install kibana
sudo systemctl enable kibana
sudo systemctl start kibana
```

## 3. Install Filebeat
```bash
sudo apt install filebeat
sudo systemctl enable filebeat
sudo systemctl start filebeat
```

## 4. Verify Installation
```bash
# Check Elasticsearch
curl -X GET "localhost:9200"

# Check services
sudo systemctl status elasticsearch
sudo systemctl status kibana
sudo systemctl status filebeat
```

## 5. Access Kibana
Open browser: `http://localhost:5601`

## 🔴 Detection Rules Setup
In Kibana → Security → Rules → Create Rule

| Rule | Query |
|------|-------|
| Brute Force | `event.code:4625` |
| Successful Login | `event.code:4624` |
| Privilege Escalation | `event.code:4672` |
| New User Created | `event.code:4720` |
| Account Lockout | `event.code:4740` |

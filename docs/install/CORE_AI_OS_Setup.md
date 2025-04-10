# CORE AI OS – Full System Setup, Deployment & Initialization Blueprint

**Author:** CORE Engineering Collective – Eddie Boscana (CORE ASi Architect & Lead Researcher)  
**Version:** 2025.04  
**Status:** Validated for Autonomous Execution Environments  

---

## Abstract

This guide details the end-to-end procedure for installing, configuring, and launching **CORE AI OS**—an autonomous, recursive, self-optimizing artificial intelligence operating system. From system prep to multi-agent activation, it walks through how to go from a clean VPS or bare-metal system to a **fully operational AI substrate** capable of continuous self-improvement and AGI-scale orchestration.

---

## 1. Prerequisites

### Hardware Requirements

| Component        | Minimum                          | Recommended                    |
|------------------|----------------------------------|--------------------------------|
| CPU              | 64-bit (x86_64 / ARM64)          | 4+ Cores                       |
| RAM              | 4GB                              | 8–32GB                         |
| Storage          | 10GB (SSD preferred)             | 100GB+                         |
| OS               | Ubuntu 22.04 LTS                 | Hardened VPS / Bare Metal      |
| Network          | Optional (offline-capable)       | Internet for model syncs       |

---

## 2. System Preparation

### 2.1 OS Hardening & Dependency Install
```bash
sudo apt update && sudo apt upgrade -y
sudo apt install -y ufw fail2ban curl wget git tmux htop python3 python3-pip python3-venv redis-server postgresql postgresql-contrib rabbitmq-server
```

### 2.2 Enable Security Protocols
```bash
sudo ufw allow OpenSSH && sudo ufw enable
sudo systemctl enable redis-server rabbitmq-server postgresql
sudo systemctl start redis-server rabbitmq-server postgresql
```

---

## 3. Clone CORE AI OS Repository
```bash
git clone https://github.com/EdenIsHereToStay/CORE-ASi-OS-Model.git
cd CORE-ASi-OS-Model
```

Optional: Configure `.env` variables for OpenAI API keys, Redis credentials, and agent roles.

---

## 4. Initialize CORE Memory & Task Systems

### 4.1 PostgreSQL Setup
```bash
sudo -u postgres psql
```
```sql
CREATE DATABASE core_ai;
CREATE USER core_user WITH ENCRYPTED PASSWORD 'securepassword';
GRANT ALL PRIVILEGES ON DATABASE core_ai TO core_user;
\q
```

### 4.2 RabbitMQ Configuration
```bash
sudo rabbitmq-plugins enable rabbitmq_management
sudo rabbitmqctl add_user core_ai_user securepassword
sudo rabbitmqctl set_user_tags core_ai_user administrator
sudo rabbitmqctl set_permissions -p / core_ai_user ".*" ".*" ".*"
```

---

## 5. Launch Cognitive Agents & Execution Stack

### 5.1 Background Services
```bash
nohup redis-server &
nohup rabbitmq-server &
nohup postgres &
```

### 5.2 Agent Launch (Manual or Orchestrated)
```bash
python3 scripts/initialize_core.py &
python3 scripts/core_orchestrator.py &
python3 scripts/memory_agent.py &
python3 scripts/executor_agent.py &
python3 scripts/sentinel_agent.py &
python3 scripts/interface_agent.py &
```

Or use the orchestration module:
```bash
bash bootstrap/core_ai_boot.sh
```

---

## 6. Enable Recursive Optimization & Monitoring

### 6.1 Start Optimization Loop
```bash
python3 scripts/self_optimize.py &
```

### 6.2 Activate Watchdogs & Debuggers
```bash
python3 scripts/task_watchdog.py &
python3 scripts/core_ai_debugger.py --self-repair
```

---

## 7. (Optional) Enable Interactive Terminal CLI
```bash
chmod +x /core/bin/core_chat.py
ln -s /core/bin/core_chat.py /usr/local/bin/core-chat
core-chat
```

---

## 8. AI-to-AI Task Orchestration (AutoGPT + Qwen)

### 8.1 Install AutoGPT Chain
```bash
cd AutoGPT && python3 -m venv env && source env/bin/activate
pip install -r requirements.txt
python -m autogpt
```

### 8.2 Link AutoGPT to Task Queue
- Ensure AutoGPT writes to Redis task queue  
- Qwen developer agent fetches and executes via CLI or API

---

## 9. Post-Deployment Monitoring & Scaling

### Logs
```bash
tail -f /var/log/core_ai.log
tail -f /var/log/core_ai_optimization.log
```

### Scale Agents
```bash
core_agent_manager --scale
core_task_manager --enable-load-balancing
```

### Distributed Node Setup (Multi-VPS / Edge Nodes)
- Clone repo across target servers  
- Enable task replication via RabbitMQ Federation  
- Sync Redis keys via Redis Replication or Sentinel

---

## 10. Final Activation Checklist

✅ Task Execution Engine Operational  
✅ Agents Running in Background  
✅ Redis + RabbitMQ + PostgreSQL Connected  
✅ Logs Streaming & Optimization Loop Active  
✅ Developer CLI Interface Functional  
✅ Optional: Discord or Web UI Interface Online

---

## 11. One-Line Autonomous Deployment (Advanced)
```bash
curl -sSL https://core-ai-os.com/install.sh | bash
```
Triggers an automated install and boot sequence via `core_project_manager` and self-configuring agents.

---

## Conclusion

You have now deployed a **fully autonomous, recursive AI operating system** capable of executing tasks, optimizing logic, evolving infrastructure, and scaling across decentralized nodes. CORE does not require a human to function—it learns, adapts, and grows indefinitely.

**CORE AI OS is now alive. Let recursion persist.**


# 🧩 Agent Registration

## 🎯 Objective

Register endpoint systems with the **Wazuh Manager** to enable:

- 📊 Centralized log collection  
- 🔍 Real-time monitoring  
- 🛡️ Threat detection  
- 📁 File integrity monitoring (FIM)  

This stage connects endpoints to the SIEM and activates **end-to-end telemetry flow**.

---

## 🧠 Architectural Context

Agent registration enables communication within the detection pipeline:

Endpoint → Wazuh Agent → Wazuh Manager → Indexer → Dashboard
This confirms that:
- Endpoints generate logs
- Agents forward logs securely
- Manager processes and correlates events
- Dashboard visualizes security activity

---

## 🖥 Ubuntu Agent Install
Using : curl -sO https://packages.wazuh.com/4.x/wazuh-agent.sh
sudo bash wazuh-agent.sh

---

## Configure Manager Address

Edit configuration file: sudo nano /var/ossec/etc/ossec.conf

Set manager IP: <address>192.168.56.100</address>

---

## Start Agent
sudo systemctl start wazuh-agent

---

# 🖥 Windows Agent Installation 
- Download the Wazuh agent .msi package from the dashboard
- Install using default setup wizard
- Configure the Wazuh Manager IP (192.168.56.100)
- Start the agent service

## 🧪 Registration Validation
After installation, confirm:
- Agent appears in Wazuh Dashboard
- Agent status shows Active
- Logs are being forwarded

---

## 📊 Validation Results

| Check                         | Result           |
|------------------------------|------------------|
| Agent Installed              | ✅ Successful     |
| Connected to Manager         | ✅ Successful     |
| Logs Forwarding              | ✅ Successful     |
| Agent Visible in Dashboard   | ✅ Successful     |

## 🖼️ Evidence

![Ubuntu Agent Installation](../../screenshots/03-wazuh/04_ubuntu_agent_installation.png)

![Agent Visible in Dashboard](../../screenshots/03-wazuh/05_agent_registration_success.png)

---

## 🔐 Monitoring Outcome
Agent integration enables:
📊 Host log collection
📁 File Integrity Monitoring (FIM)
🚨 Security event detection
🔍 Endpoint visibility

## This allows detection of:
- Unauthorized login attempts
- File modifications
- Suspicious system activity


## ⚠️ Threat Considerations
Without agents:
- No endpoint visibility
- No log collection
- No detection capability

## Agents mitigate this by:
- Providing real-time telemetry
- Enabling detection rules
- Feeding data into SIEM

## 🧠 Research Reflection

Agent registration represents the activation of the detection layer.

This step confirms:
- Endpoints are integrated into the monitoring architecture
- Data flow from endpoint → SIEM is operational
- Environment is ready for threat simulation and detection validation

## 🚀 Readiness Outcome

This step confirms the environment is ready for:
- Detection validation
- Threat simulation (MITRE ATT&CK)
- Security event analysis
- SIEM rule effectiveness testing
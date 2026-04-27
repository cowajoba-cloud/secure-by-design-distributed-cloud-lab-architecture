# 🛡 Wazuh Manager Installation

## 🎯 Objective

Deploy centralized SIEM for log aggregation, alerting, and security monitoring.

---

## 🧩 Installation Method

On Ubuntu Server:

```bash
curl -sO https://packages.wazuh.com/4.x/wazuh-install.sh
sudo bash wazuh-install.sh -a

# 📷 Installation Completion

screenshots/03-wazuh/01_wazuh_installation_success.png

Capture:
Terminal output showing successful installation message.

# 🔐 Security Impact

- Centralized log management

- Threat detection engine

- Real-time alerting capability

# ✅ Validation
sudo systemctl status wazuh-manager

## 🖼️ Evidence

![Wazuh Installation Success](../../screenshots/03-wazuh/01_wazuh_installation_success.png)

![Wazuh Service Running](../../screenshots/03-wazuh/02_wazuh_service_running.png)
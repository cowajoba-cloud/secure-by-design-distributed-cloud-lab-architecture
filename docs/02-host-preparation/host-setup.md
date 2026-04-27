# 🖥️ Host Preparation

## 🎯 Objective
Prepare the host system for secure virtualization.

---

## 🔧 Configuration Steps

### 1️⃣ System Hardening

- Enable firewall
- Enable OS updates
- Restrict unnecessary services

---

### 2️⃣ Secure Access

- Install OpenSSH server
- Configure remote access securely

---

### 3️⃣ Disk Protection

- Enable encryption (BitLocker / equivalent)

---

## 🔐 Security Rationale

Host is the **root trust anchor** of the lab.

If compromised → entire environment compromised.

---

## 🖼️ Evidence

**Figure S06: Windows Firewall Enabled**  
![Firewall](../../screenshots/02-host-preparation/S06_windows_firewall_enabled.png)

**Figure S08: OpenSSH Service Running**  
![SSH](../../screenshots/02-host-preparation/S08_openssh_server_running.png)
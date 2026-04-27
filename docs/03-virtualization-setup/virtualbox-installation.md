# 🧰 Virtualization Setup

## 🎯 Objective
Establish a secure and isolated virtualization layer using VirtualBox.

---

## ⚙️ Installation Steps

### 1️⃣ Install VirtualBox
- Download from official source
- Install on host system

---

### 2️⃣ Configure Networking

- Create Host-Only Adapter
- Enable NAT Adapter for internet access

---

## 🌐 Adapter Configuration

| Adapter | Purpose |
|--------|--------|
| NAT | Internet access |
| Host-Only | Internal lab communication |

---

## 🔐 Security Consideration

- Host-only network prevents external exposure
- Controlled NAT ensures limited outbound access

---

## 🖼️ Evidence

**Figure S10: VirtualBox Installation Complete**  
![VBox](../../screenshots/03-virtualization/S10_virtualbox_installation_complete.png)

**Figure S11: Host-Only Adapter Configured**  
![Adapter](../../screenshots/03-virtualization/S11_host_only_network_adapter.png)
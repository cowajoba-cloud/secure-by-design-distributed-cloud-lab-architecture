# 🌐 Static IP Configuration

## 🎯 Objective
Assign fixed IP addresses to all VMs.

---

## ⚙️ Implementation

Edit Netplan: sudo nano /etc/netplan/*.yaml
sudo netplan apply

## 📊 Example Configuration
addresses:
  - 192.168.56.10/24
gateway4: 192.168.56.1

## 🔐 Security Rationale
Enables predictable communication
Supports SIEM correlation
Ensures reproducibility

## 🖼️ Evidence

Figure S21: Ubuntu Server Static IP


Figure S22: Ubuntu Desktop Static IP

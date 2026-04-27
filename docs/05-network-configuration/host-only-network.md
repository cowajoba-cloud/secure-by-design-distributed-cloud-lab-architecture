
# 📁 05-network-configuration / `host-only-network.md`

```markdown
# 🌐 Host-Only Network Configuration

## 🎯 Objective
Create a fully isolated internal network.

---

## ⚙️ Steps

- Configure VirtualBox host-only adapter
- Assign subnet: 192.168.56.0/24
- Attach all VMs to adapter

---

## 🔐 Security Rationale

- Prevents exposure to external networks
- Enables safe attack simulation
- Supports Zero Trust segmentation

---

## 🖼️ Evidence

**Figure S20: Host-Only Network Settings**  
![Network](../../screenshots/05-network-validation/S20_host_only_network_settings.png)
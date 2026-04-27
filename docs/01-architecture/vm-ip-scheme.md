# 🖧 VM IP Scheme

## 🎯 Objective
Define consistent addressing across all lab systems.

---

## 📊 IP Allocation

| VM | IP |
|----|----|
| Ubuntu Server | 192.168.56.10 |
| Kali Linux | 192.168.56.20 |
| Ubuntu Desktop | 192.168.56.30 |
| Wazuh Manager | 192.168.56.100 |

---

## 🔐 Security Consideration

Static IPs ensure:

- Predictable communication
- Reliable logging and detection
- Consistent threat simulation

---

## 🖼️ Evidence

**Figure S03: VM Segmentation Overview**  
![VM](../../screenshots/01-architecture/S03_vm_roles_and_segmentation.png)
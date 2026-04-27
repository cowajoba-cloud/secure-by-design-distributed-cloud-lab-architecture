# 🧱 Architecture Overview

## 🎯 Purpose
This section defines the **secure-by-design distributed architecture** used throughout the lab.

---

## 🧠 Design Philosophy

The architecture is built on:

- 🔒 Zero Trust principles  
- 🧱 Defense-in-Depth  
- 🌐 Network segmentation  
- 👁️ Observability-first design  
- 🔑 Least privilege enforcement  

---

## 🏗️ System Components

| Component | Role |
|----------|------|
| Ubuntu Server | Core infrastructure + Wazuh SIEM |
| Ubuntu Desktop | CI/CD runner |
| Kali Linux | Adversary simulation |
| Windows Endpoint | Monitored endpoint |
| Docker Registry | Secure artifact storage |

---

## 🖼️ Evidence

**Figure S01: Secure Architecture Overview**  
![Architecture](../screenshots/01-architecture/S01_architecture_overview_diagram.png)

---

## 📌 Research Reflection

Security is embedded at the architectural layer, reducing reliance on reactive controls.
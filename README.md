# 🛡️ Secure-by-Design Distributed Cloud Lab Architecture

> A production-style Security Engineering lab demonstrating secure architecture design, centralized monitoring, system hardening, DevSecOps automation, threat simulation, and compliance alignment.

---

# **📌 Executive Summary**

This project simulates a secure distributed enterprise environment built using a **Secure-by-Design methodology**.

It demonstrates:

- 🏗️ Security architecture planning  
- 🌐 Network segmentation  
- 🖥️ Virtual infrastructure deployment  
- 📊 SIEM implementation (Wazuh)  
- 🔐 System & endpoint hardening  
- 🚀 CI/CD security automation  
- 🎯 MITRE ATT&CK threat simulation  
- 📑 ISO 27001 & NIST control mapping  

The lab mirrors real-world Security Engineering and SOC workflows.

---

# **🧠 Architecture Overview**

The environment consists of:

| Component | Role |
|------------|------|
| macOS Host | Management Layer |
| Ubuntu Server | Wazuh Manager (SIEM) |
| Ubuntu Desktop | Monitored Endpoint |
| Windows 10 | Monitored Endpoint |
| Kali Linux | Adversary Simulation |

### **🔎 Core Security Principles**

- Zero Trust mindset  
- Defense-in-depth  
- Network segmentation  
- Centralized visibility  
- Least privilege enforcement  
- Compliance alignment  

---

# **🗂️ Repository Structure (Lifecycle Ordered)**

This repository follows the actual build sequence of the environment.

docs
├── 01-architecture
├── 02-host-preparation
├── 03-virtualization-setup
├── 04-vm-deployment
├── 05-network-configuration
├── 06-wazuh-manager-deployment
├── 07-agent-deployment
├── 08-security-hardening
├── 09-ci-cd-security
├── 10-threat-simulation
├── 11-compliance-alignment
└── 12-baseline-snapshots

---


Each stage builds logically on the previous one.

---

# **📘 Section Breakdown**

## **01️⃣ Architecture**

- System architecture overview  
- Network topology design  
- IP allocation scheme  
- STRIDE-based threat modeling  

---

## **02️⃣ Host Preparation**

- macOS host configuration  
- Firewall enforcement  
- Secure management setup  

---

## **03️⃣ Virtualization Setup**

- VirtualBox installation  
- Environment isolation preparation  

---

## **04️⃣ VM Deployment**

Creation and configuration of:

- Ubuntu Server (Wazuh Manager)  
- Ubuntu Desktop (Endpoint)  
- Windows 10 (Endpoint)  
- Kali Linux (Adversary)  

Includes static IP configuration.

---

## **05️⃣ Network Configuration**

- Host-only segmentation  
- Port forwarding rules  
- SSH configuration  
- VM communication validation  

---

## **06️⃣ Wazuh Manager Deployment**

- Wazuh installation  
- Service verification  
- Dashboard configuration  

---

## **07️⃣ Agent Deployment**

- Ubuntu & Windows agent registration  
- Log forwarding validation  
- Detection testing  
- File Integrity Monitoring validation  

---

## **08️⃣ Security Hardening**

- SSH lockdown  
- UFW firewall enforcement  
- Endpoint security configuration  
- Docker container hardening  

---

## **09️⃣ CI/CD Security**

- GitHub Actions pipeline  
- Trivy vulnerability scanning  
- Secure Docker build process  
- Automated security validation  

---

## **10️⃣ Threat Simulation**

- MITRE ATT&CK mapping  
- SSH brute force detection (T1110)  
- Command execution testing  
- Alert validation workflow  

---

## **11️⃣ Compliance Alignment**

- ISO 27001 control mapping  
- NIST Cybersecurity Framework alignment  
- Control validation matrix  
- Risk register summary  

---

## **12️⃣ Baseline Snapshots**

- Secure baseline documentation  
- Versioned environment state (v1.0)  

---

# **🔐 Security Capabilities Demonstrated**

| Capability | Implemented |
|------------|------------|
| Centralized Log Aggregation | ✅ |
| Real-Time Threat Detection | ✅ |
| File Integrity Monitoring | ✅ |
| SSH Hardening | ✅ |
| Firewall Enforcement | ✅ |
| Container Security Controls | ✅ |
| DevSecOps Automation | ✅ |
| MITRE ATT&CK Mapping | ✅ |
| Compliance Traceability | ✅ |

---

# **🛠️ Technologies Used**

- VirtualBox  
- Ubuntu Server & Desktop  
- Windows 10  
- Kali Linux  
- Wazuh SIEM  
- Docker  
- GitHub Actions  
- Trivy  
- OpenSSH  
- UFW Firewall  

---

# **🎯 Learning & Engineering Outcomes**

This lab demonstrates practical capability in:

- Secure system architecture design  
- Threat modeling using STRIDE  
- SIEM deployment & validation  
- Detection engineering fundamentals  
- Infrastructure hardening  
- DevSecOps security integration  
- Risk & compliance alignment  

It bridges technical implementation with governance awareness.

---

# **🚀 Why This Project Matters**

This is not just a lab build.

It represents:

- Security architecture thinking  
- Operational monitoring deployment  
- Threat validation discipline  
- Governance traceability  
- Secure engineering execution  

It showcases real-world, end-to-end security lifecycle capability.

---

# **📌 Future Enhancements**

- IDS/IPS integration  
- Automated adversary simulation scripts  
- Infrastructure as Code (Terraform)  
- Custom detection rule engineering  
- Detection response playbooks  

---

# **👤 Author**
# Charles Owajoba 
Security Engineering | Cloud Security | DevSecOps | Secure Architecture | Compliance Mapping  

---


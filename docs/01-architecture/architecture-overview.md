# 🧱 Architecture Overview

## 🎯 Purpose

This section defines the **secure-by-design distributed architecture** used throughout the lab.

The architecture was designed to demonstrate how security can be embedded into infrastructure, monitoring, software delivery, and threat validation from the earliest design stage.

Rather than treating security as an after-deployment activity, this lab positions security as a foundational design requirement.

---

## 🧠 Design Philosophy

The architecture is built on the following principles:

- 🔒 **Zero Trust** — no system, user, or network path is trusted by default  
- 🧱 **Defense-in-Depth** — multiple layers of protection are applied across the environment  
- 🌐 **Network Segmentation** — systems are separated using controlled host-only networking  
- 👁️ **Observability-First Design** — logs, alerts, and telemetry are collected centrally  
- 🔑 **Least Privilege** — access is restricted to what is required for each system role  
- 🧪 **Validation-Driven Security** — controls are tested using real lab evidence  

---

## 🏗️ Architecture Scope

The lab simulates a secure distributed enterprise-style environment containing:

- Infrastructure systems  
- Monitored endpoints  
- Attack simulation nodes  
- SIEM/XDR monitoring  
- Secure CI/CD pipeline  
- Private container registry  
- Compliance mapping and evidence collection  

The goal is to validate whether a secure-by-design architecture can support real monitoring, threat detection, and DevSecOps workflows inside a controlled lab environment.

---

## 🧩 System Components

| Component | Role | Security Purpose |
|----------|------|------------------|
| Ubuntu Server | Core infrastructure + Wazuh SIEM | Central monitoring and detection layer |
| Ubuntu Desktop | CI/CD runner + monitored endpoint | Secure build execution and endpoint telemetry |
| Kali Linux | Adversary simulation | Controlled attack generation |
| Windows Host | Virtualization host and access bridge | Lab control plane |
| Docker Registry | Secure artifact storage | Internal container image distribution |
| GitHub Actions Runner | CI/CD automation | Controlled pipeline execution |
| Wazuh Dashboard | Security visibility layer | Alert review and investigation |

---

## 🌐 High-Level Architecture Flow


Developer / GitHub
        ↓
Self-hosted GitHub Actions Runner
        ↓
Docker Build + Security Validation
        ↓
Private Docker Registry
        ↓
Monitored Infrastructure
        ↓
Wazuh Agent → Wazuh Manager → Dashboard Alert

---

## 🖼️ Evidence

**Figure S01: Secure Architecture Overview**  
![Architecture](../../screenshots/01-architecture/S01_architecture_overview_diagram.png)
![Trust Boundaries Mapping](../../screenshots/01-architecture/S04_trust_boundaries_mapping.png)

---
## 🔐 Security Assumptions
The architecture assumes:
- All lab systems operate inside a controlled virtualized environment
- Internal communication occurs over the host-only network
- Internet access is limited to systems that require updates or package downloads
- Wazuh is the central source of detection visibility
- The CI/CD runner is trusted but must be hardened and monitored
- Vulnerable systems are isolated and not exposed to the wider network

---

## ⚠️ Architectural Risk Considerations

| Risk | Mitigation |
|---|---|
| Excessive lateral movement | Host-only segmentation and firewall rules |
| Unmonitored endpoint activity | Wazuh agent deployment |
| Insecure artifact distribution | Private Docker registry |
| Pipeline compromise | Self-hosted runner hardening |
| Weak visibility | Centralized SIEM dashboard |
| Attack simulation escaping lab | No bridged networking for attack systems |

---

## 📊 Architecture Validation Summary

| Validation Area | Result |
|---|---|
| Architecture design completed | ✅ Successful |
| Network segmentation defined | ✅ Successful |
| Trust boundaries identified | ✅ Successful |
| SIEM monitoring layer designed | ✅ Successful |
| CI/CD security layer integrated | ✅ Successful |
| Threat simulation path defined | ✅ Successful |
| Compliance evidence structure prepared | ✅ Successful |


## 🧠 Research Reflection

This architecture supports the central research idea that many security failures begin with weak design decisions rather than advanced exploits.

Poor segmentation, unclear trust boundaries, excessive privileges, and weak observability often create the conditions attackers exploit.

By designing the lab around segmentation, monitoring, DevSecOps, and validation, the project demonstrates how secure-by-design principles can be translated into a practical, testable architecture.

## 🚀 Readiness Outcome

This architecture overview confirms that the lab is ready for:
- Network design validation
- Static IP scheme documentation
- Wazuh deployment
- Agent monitoring
- Security hardening
- CI/CD security automation
- Threat simulation
- Compliance alignment

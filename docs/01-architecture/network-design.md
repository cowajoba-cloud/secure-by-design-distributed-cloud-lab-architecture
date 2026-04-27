# 🌐 Network Design

## 🎯 Objective

Design a **segmented and controlled network environment** that supports secure communication, monitoring, threat simulation, and DevSecOps validation.

This network design provides the foundation for:

- Controlled VM communication  
- Wazuh agent-to-manager telemetry  
- Safe adversary simulation  
- Private registry access  
- CI/CD runner connectivity  
- Reduced exposure to external networks  

---

## 🧠 Design Philosophy

The network follows a **segmentation-first security model**.

Instead of allowing open communication between all systems, the lab uses controlled internal networking to define how systems communicate and where trust boundaries exist.

The design prioritizes:

- 🌐 Internal segmentation  
- 🔐 Controlled access paths  
- 🧱 Reduced attack surface  
- 👁️ Visibility into monitored traffic  
- 🧪 Safe attack simulation  

---

## 🧩 Network Design Approach

| Network Element | Purpose |
|---|---|
| Host-only network | Internal lab communication |
| NAT adapter | Controlled internet access for updates and package downloads |
| Static IP addressing | Predictable routing and monitoring |
| Firewall rules | Restrict unnecessary traffic |
| SSH tunnel | Secure dashboard access from management host |
| Private registry port | Internal container image distribution |

---

## 🖧 Lab Network Range

The internal lab network uses:
Bash 
192.168.56.0/24

This range supports predictable addressing for:
- Wazuh Manager
- Ubuntu Desktop runner
- Kali attack machine
- Target systems
- Private registry

---

## 🧱 Network Segmentation Model
Management Host
      ↓
Windows VirtualBox Host
      ↓
Host-Only Network: 192.168.56.0/24
      ↓
Ubuntu Server / Wazuh / Registry
Ubuntu Desktop / Runner
Kali Linux / Attack Simulation
Target Systems

This model allows internal systems to communicate while limiting exposure to the wider network.

## 📊 Network Role Mapping

| System | Network Role | Security Purpose |
|---|---|---|
| Ubuntu Server | Wazuh Manager + Registry | Central monitoring and artifact storage |
| Ubuntu Desktop | CI/CD runner + endpoint | Build execution and telemetry source |
| Kali Linux | Attack simulation | Controlled adversary traffic generation |
| Windows Host | Virtualization host | Lab control plane |
| macOS Host | Management access | Remote administration and documentation |

## 🔐 Trust Boundary Definition
The main trust boundaries are:
## 🔐 Trust Boundary Definition

| Boundary | Description | Security Concern |
|---|---|---|
| Internet → NAT VM | Controlled outbound access | Package download exposure |
| Host → VirtualBox Network | Host-to-lab access | Administrative access risk |
| Kali → Target VM | Attack simulation path | Controlled adversary traffic |
| Endpoint → Wazuh Manager | Telemetry forwarding | Log integrity and availability |
| Runner → Registry | CI/CD artifact flow | Image tampering or leakage |


## 🛡️ Security Rationale
The network design reduces risk by:
- Preventing unnecessary external exposure
- Isolating vulnerable targets inside the lab
- Keeping attack traffic controlled
- Enabling Wazuh to monitor defined systems
- Supporting repeatable validation
- Restricting dashboard and registry access to internal systems

## 🧪 Validation Methods

The network design was validated using:
- ping 192.168.56.10
- curl -k https://192.168.56.100:5000/v2/_catalog
- ssh -L 5602:192.168.56.100:443 <windows-user>@<windows-host-ip>

These tests confirm:
- Internal VM reachability
- Registry connectivity
- Secure dashboard access path
- Controlled communication across the lab
---

## 📊 Network Validation Summary
| Validation Area | Result |
|---|---|
| Host-only network configured | ✅ Successful |
| NAT access available where required | ✅ Successful |
| Static IP range defined | ✅ Successful |
| Inter-VM communication validated | ✅ Successful |
| Wazuh dashboard reachable internally | ✅ Successful |
| Private registry reachable internally | ✅ Successful |
| Attack simulation path controlled | ✅ Successful |

## 🖼️ Evidence
![Network Connectivity Test](../../screenshots/03-wazuh/figure8-network-connectivity-test.png)

![Wazuh Dashboard Reachable Internally](../00-research-assets/screenshots/week7-8-detection-validation/figure1-wazuh-dashboard-overview.png)

## ⚠️ Network Risk Considerations
| Risk | Mitigation |
|---|---|
| Attack VM exposed to external network | Keep Kali off bridged mode |
| Vulnerable targets reachable from LAN | Host-only network only |
| Dashboard exposed publicly | Restrict Wazuh access to internal network |
| Registry exposed externally | Bind registry to internal lab access only |
| Uncontrolled lateral movement | Firewall rules and segmentation |
| Broken telemetry flow | Static IPs and validation checks |


## 🧠 Research Reflection

Network design is the first major security control in this architecture.

A poorly designed network can undermine strong tooling, monitoring, and hardening. In contrast, a segmented network creates predictable trust boundaries and supports measurable security validation.

This lab demonstrates that secure-by-design architecture begins with clear communication paths, defined trust zones, and controlled exposure.

## 🚀 Readiness Outcome
The network design confirms that the environment is ready for:
- Static IP assignment
- Wazuh deployment
- Agent communication
- Private registry validation
- CI/CD pipeline execution
- Threat simulation
- Compliance mapping
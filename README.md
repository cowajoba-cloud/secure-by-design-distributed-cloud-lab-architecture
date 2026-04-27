# **Author: Charles Owajoba**
**MSc Computer Science (Software Engineering)**

**GitHub:** https://github.com/cowajoba-cloud  
**LinkedIn:** https://www.linkedin.com/in/charlesowajoba/  
**ORCID:** https://orcid.org/0009-0005-5558-9558

# 🛡️ Secure-by-Design Distributed Cloud Lab Architecture

> A production-style Security Engineering lab demonstrating secure architecture design, centralized monitoring, system hardening, DevSecOps automation, threat simulation, and compliance alignment.

---

# **📌 Executive Summary**

This project simulates a secure distributed enterprise environment built using a **Secure-by-Design methodology**.

It demonstrates:

- 🏗️ Security architecture planning  
- 🌐 Network segmentation  
- 🖥️ Virtual infrastructure deployment  
- 📊 SIEM implementation with Wazuh  
- 🔐 System, VM, and container hardening  
- 🚀 CI/CD security automation using GitHub Actions  
- 🐳 Secure Docker build and private registry workflow  
- 🎯 MITRE ATT&CK threat simulation  
- 📑 ISO 27001 and NIST control mapping  
- 🧾 Secure baseline snapshot documentation  

The lab mirrors real-world Security Engineering, SOC, Cloud Security, and DevSecOps workflows.

---

# **🧠 Architecture Overview**

The environment consists of multiple systems working together to support secure monitoring, controlled adversary simulation, and software delivery validation.

| Component | Role |
|---|---|
| macOS Host | Management and documentation layer |
| Windows Host | VirtualBox host and lab control plane |
| Ubuntu Server | Core infrastructure, Wazuh Manager, and private registry |
| Ubuntu Desktop | CI/CD runner and monitored endpoint |
| Kali Linux | Controlled adversary simulation |
| Wazuh Manager | SIEM / XDR monitoring layer |
| Docker Registry | Internal secure artifact storage |
| GitHub Actions Runner | Secure CI/CD execution node |

---

## **🔎 Core Security Principles**

- 🔒 Zero Trust mindset  
- 🧱 Defense-in-depth  
- 🌐 Network segmentation  
- 👁️ Centralized visibility  
- 🔑 Least privilege enforcement  
- 🧪 Validation-driven security  
- 📑 Compliance traceability  

---

## **🖼️ Architecture Evidence**

![Architecture Overview](screenshots/01-architecture/S01_architecture_overview_diagram.png)

---

# **🗂️ Repository Structure**

The repository is organised according to the **secure-by-design lab lifecycle**.

Each documentation folder represents a major phase of the architecture, from initial design through deployment, hardening, CI/CD security, threat simulation, compliance mapping, and final secure baseline snapshot.

```text
.
├── 📄 README.md
├── 📄 LICENSE
├── 🐳 Dockerfile
├── 🌐 index.html
│
├── 🐳 docker
│   └── secure-app
│       └── Dockerfile
│
├── 📚 docs
│   ├── 01-architecture
│   │   ├── architecture-overview.md
│   │   ├── network-design.md
│   │   ├── threat-model-summary.md
│   │   └── vm-ip-scheme.md
│   │
│   ├── 02-host-preparation
│   │   └── host-setup.md
│   │
│   ├── 03-virtualization-setup
│   │   └── virtualbox-installation.md
│   │
│   ├── 04-vm-deployment
│   │   ├── vm-creation.md
│   │   └── static-ip-configuration.md
│   │
│   ├── 05-network-configuration
│   │   ├── host-only-network.md
│   │   ├── mac-to-windows-ssh.md
│   │   ├── port-forwarding.md
│   │   └── vm-communication-validation.md
│   │
│   ├── 06-wazuh-manager-deployment
│   │   ├── wazuh-installation.md
│   │   └── dashboard-access.md
│   │
│   ├── 07-agent-deployment
│   │   ├── agent-registration.md
│   │   └── validation-checks.md
│   │
│   ├── 08-security-hardening
│   │   ├── server-hardening.md
│   │   ├── vm-hardening.md
│   │   └── docker-hardening.md
│   │
│   ├── 09-ci-cd-security
│   │   ├── pipeline-architecture.md
│   │   ├── github-actions-runner.md
│   │   ├── docker-build-secure.md
│   │   └── trivy-integration.md
│   │
│   ├── 10-threat-simulation
│   │   └── mitre-attack-mapping.md
│   │
│   ├── 11-compliance-alignment
│   │   ├── control-validation-matrix.md
│   │   ├── iso27001-mapping.md
│   │   ├── nist-mapping.md
│   │   └── risk-register-summary.md
│   │
│   └── 12-baseline-snapshots
│       └── snapshot-v1.0-secure-baseline.md
│
├── 🖼️ screenshots
│   ├── 01-architecture
│   │   └── S01_architecture_overview_diagram.png
│   ├── 01-vm-creation
│   ├── 02-network-validation
│   ├── 03-wazuh
│   ├── 04-hardening
│   ├── 05-ci-cd
│   └── 06-snapshots
│
└── 🧰 scripts
```

---

# **📘 Documentation Lifecycle**

| Phase | Folder | Purpose |
|---|---|---|
| 01 | `docs/01-architecture` | Secure architecture design, network model, STRIDE threat model, and IP scheme |
| 02 | `docs/02-host-preparation` | Host system preparation and security readiness |
| 03 | `docs/03-virtualization-setup` | VirtualBox installation and isolation setup |
| 04 | `docs/04-vm-deployment` | VM creation and static IP configuration |
| 05 | `docs/05-network-configuration` | Host-only networking, SSH tunneling, port forwarding, and connectivity validation |
| 06 | `docs/06-wazuh-manager-deployment` | Wazuh SIEM installation and dashboard validation |
| 07 | `docs/07-agent-deployment` | Wazuh agent registration and detection validation |
| 08 | `docs/08-security-hardening` | Server, VM, and Docker hardening |
| 09 | `docs/09-ci-cd-security` | Secure CI/CD pipeline, GitHub Actions runner, Docker build, and Trivy integration |
| 10 | `docs/10-threat-simulation` | MITRE ATT&CK-aligned threat simulation and detection proof |
| 11 | `docs/11-compliance-alignment` | ISO 27001, NIST, risk register, and control validation mapping |
| 12 | `docs/12-baseline-snapshots` | Final secure baseline snapshot and validated system state |

---

# **🧭 Research Flow**

```text
Architecture Design
        ↓
Virtual Lab Build
        ↓
Network Segmentation
        ↓
Wazuh Monitoring
        ↓
Agent Telemetry
        ↓
System Hardening
        ↓
Secure CI/CD Pipeline
        ↓
Threat Simulation
        ↓
Compliance Mapping
        ↓
Secure Baseline Snapshot
```

---

# **📘 Section Breakdown**

## **01️⃣ Architecture**

Covers:

- System architecture overview  
- Network topology design  
- VM role definition  
- IP allocation scheme  
- STRIDE-based threat modeling  
- Trust boundary identification  

---

## **02️⃣ Host Preparation**

Covers:

- Host operating system preparation  
- Firewall enforcement  
- Secure management access  
- Host security readiness  

---

## **03️⃣ Virtualization Setup**

Covers:

- VirtualBox installation  
- Host-only adapter configuration  
- NAT adapter configuration  
- Virtual lab isolation model  

---

## **04️⃣ VM Deployment**

Covers:

- Ubuntu Server deployment  
- Ubuntu Desktop deployment  
- Kali Linux deployment  
- Vulnerable target preparation  
- Static IP configuration  

---

## **05️⃣ Network Configuration**

Covers:

- Host-only segmentation  
- NAT connectivity  
- SSH tunneling  
- Port forwarding  
- VM communication validation  

---

## **06️⃣ Wazuh Manager Deployment**

Covers:

- Wazuh installation  
- Service verification  
- Dashboard access  
- SIEM visibility validation  

---

## **07️⃣ Agent Deployment**

Covers:

- Endpoint agent registration  
- Agent status validation  
- Log forwarding validation  
- Detection readiness checks  

---

## **08️⃣ Security Hardening**

Covers:

- Ubuntu Server hardening  
- Ubuntu Desktop hardening  
- Kali Linux controlled hardening  
- Docker runtime hardening  
- Private registry security  

---

## **09️⃣ CI/CD Security**

Covers:

- GitHub Actions self-hosted runner  
- Secure Docker build process  
- Private registry push  
- Pipeline validation  
- Trivy integration planning  

---

## **🔟 Threat Simulation**

Covers:

- MITRE ATT&CK mapping  
- SSH brute-force simulation  
- Authentication log validation  
- Wazuh detection and correlation  
- Alert investigation workflow  

---

## **1️⃣1️⃣ Compliance Alignment**

Covers:

- ISO 27001 control mapping  
- NIST cybersecurity function mapping  
- Control validation matrix  
- Risk register summary  

---

## **1️⃣2️⃣ Baseline Snapshots**

Covers:

- Final secure state documentation  
- Validated system baseline  
- VirtualBox snapshot evidence  
- v1.0 secure baseline reference  

---

# **🔐 Security Capabilities Demonstrated**

| Capability | Implemented |
|---|---|
| Secure architecture planning | ✅ |
| Network segmentation | ✅ |
| Static IP scheme | ✅ |
| Centralized log aggregation | ✅ |
| Real-time threat detection | ✅ |
| File Integrity Monitoring | ✅ |
| SSH brute-force detection | ✅ |
| Firewall enforcement | ✅ |
| Docker hardening | ✅ |
| Private registry validation | ✅ |
| Self-hosted CI/CD runner | ✅ |
| Secure Docker build pipeline | ✅ |
| MITRE ATT&CK mapping | ✅ |
| ISO 27001 alignment | ✅ |
| NIST framework mapping | ✅ |
| Compliance traceability | ✅ |
| Secure baseline snapshot | ✅ |

---

# **🛠️ Technologies Used**

- VirtualBox  
- Ubuntu Server  
- Ubuntu Desktop  
- Kali Linux  
- Wazuh SIEM / XDR  
- Docker  
- Docker Registry  
- GitHub Actions  
- Self-hosted GitHub Runner  
- Trivy  
- OpenSSH  
- UFW Firewall  
- MITRE ATT&CK  
- ISO 27001  
- NIST Cybersecurity Framework  

---

# **🎯 Learning & Engineering Outcomes**

This lab demonstrates practical capability in:

- Secure system architecture design  
- Threat modeling using STRIDE  
- Network segmentation and trust boundary definition  
- SIEM deployment and validation  
- Detection engineering fundamentals  
- Infrastructure and endpoint hardening  
- Secure CI/CD pipeline implementation  
- Docker and registry security  
- Threat simulation and alert validation  
- Risk and compliance alignment  

It bridges technical implementation with governance awareness.

---

# **🚀 Why This Project Matters**

This is not just a lab build.

It represents:

- Security architecture thinking  
- Operational monitoring deployment  
- Threat validation discipline  
- Secure software delivery  
- Governance traceability  
- Research-driven security engineering  

The project demonstrates how secure-by-design principles can be implemented, tested, evidenced, and documented across an end-to-end lab environment.

---

# **📌 Future Enhancements**

- IDS/IPS integration  
- Automated adversary simulation scripts  
- Infrastructure as Code using Terraform  
- Kubernetes-based deployment model  
- Custom Wazuh detection rules  
- Detection latency benchmarking  
- Automated compliance evidence collection  
- Security response playbooks  
- Stronger registry authentication  
- Full Trivy policy gate enforcement  

---

# **👤 Author**

## Charles Owajoba

Security Engineering | Cloud Security | DevSecOps | Secure Architecture | Compliance Mapping | Detection Engineering
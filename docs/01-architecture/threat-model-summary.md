# ⚠️ Threat Model Summary

## 🎯 Objective

Identify and categorize key threats against the **Secure-by-Design Distributed Cloud Lab Architecture** using the **STRIDE threat modeling methodology**.

This section evaluates how threats may emerge across:

- Network boundaries  
- Identity and access points  
- Wazuh monitoring flow  
- CI/CD pipeline execution  
- Docker registry operations  
- Attack simulation paths  

The goal is to ensure that security risks are identified early and mapped to practical mitigations.

---

## 🧠 Threat Modeling Approach

The threat model follows the **STRIDE methodology**:

| STRIDE Category | Meaning | Example in This Lab |
|---|---|---|
| Spoofing | Impersonating a user, system, or service | Unauthorized SSH login attempt |
| Tampering | Unauthorized modification of data or configuration | Modified system files or altered Docker image |
| Repudiation | Lack of proof or traceability | Missing logs for administrative actions |
| Information Disclosure | Exposure of sensitive information | Dashboard, logs, or registry data exposed |
| Denial of Service | Disruption of service availability | Attack traffic affecting SSH, Wazuh, or registry |
| Elevation of Privilege | Gaining higher access than intended | Misuse of Docker, SSH, or runner permissions |

---

## 🏗️ Architecture Threat Surface

The lab contains several security-relevant components:

| Component | Threat Exposure | Security Concern |
|---|---|---|
| Ubuntu Server | Wazuh Manager, Registry, Core Services | High-value infrastructure node |
| Ubuntu Desktop | CI/CD Runner and Endpoint | Pipeline execution and telemetry source |
| Kali Linux | Attack Simulation | Controlled adversary activity |
| Wazuh Dashboard | Security Visibility Layer | Sensitive alert and log data |
| Docker Registry | Artifact Storage | Image tampering or unauthorized access |
| GitHub Actions Runner | Build Execution Node | Workflow misuse or runner compromise |

---

## 🔐 Trust Boundary Mapping

The architecture contains multiple trust boundaries that define where security controls must be enforced.

| Trust Boundary | Description | Security Concern | Mitigation |
|---|---|---|---|
| Internet → NAT VM | Controlled outbound package access | Exposure during updates/downloads | NAT-only access and firewall rules |
| Host → VirtualBox Network | Host-to-lab management path | Administrative misuse or unauthorized access | Controlled SSH and local access only |
| Kali → Target VM | Controlled attack simulation path | Attack traffic must remain contained | Host-only network and no bridged mode |
| Endpoint → Wazuh Manager | Security telemetry forwarding | Log integrity and availability | Agent registration and validation |
| Runner → Registry | CI/CD artifact flow | Image tampering or registry misuse | Private registry and internal access |
| Dashboard → Analyst | Security visibility layer | Exposure of sensitive alerts/logs | HTTPS and restricted access |

---

## 🧩 STRIDE Threat Analysis

| STRIDE Threat | Lab Scenario | Potential Impact | Mitigation |
|---|---|---|---|
| Spoofing | Unauthorized SSH login or fake agent identity | Unauthorized access or false telemetry | SSH hardening, Wazuh agent validation |
| Tampering | Modification of files, logs, or container images | Loss of integrity | File Integrity Monitoring, private registry |
| Repudiation | Actions performed without traceable logs | Weak investigation evidence | Wazuh logging and GitHub Actions logs |
| Information Disclosure | Dashboard or registry exposed outside lab | Sensitive data leakage | Host-only network and HTTPS |
| Denial of Service | Excessive attack traffic or pipeline overload | Service disruption | Controlled attack scope and firewall rules |
| Elevation of Privilege | Docker or runner misuse | Host compromise | Docker hardening and non-root runner execution |

---

## ⚙️ CI/CD Threat Surface

The CI/CD pipeline is treated as part of the attack surface because it can build, tag, and push software artifacts.

Pipeline-related risks include:

- Malicious workflow modification  
- Insecure Dockerfile instructions  
- Unauthorized image push  
- Runner compromise  
- Registry tampering  
- Vulnerable image distribution  

---

## 🔐 CI/CD Threat Controls

| CI/CD Risk | Mitigation |
|---|---|
| Malicious build instructions | Git version control and workflow review |
| Runner compromise | Self-hosted runner hardening |
| Insecure image distribution | Private Docker registry |
| Vulnerable container image | Trivy scanning integration |
| Unauthorized artifact push | Internal registry access controls |
| Pipeline misconfiguration | Workflow validation and controlled testing |

---

## 🛡️ Detection and Monitoring Controls

The architecture uses Wazuh to validate and monitor security-relevant behavior.

| Detection Area | Monitoring Mechanism |
|---|---|
| SSH brute-force activity | Wazuh authentication log monitoring |
| File modification | File Integrity Monitoring |
| Endpoint telemetry | Wazuh agent forwarding |
| Alert investigation | Wazuh Dashboard |
| Pipeline visibility | GitHub Actions logs |
| Registry validation | Registry API checks |

---

## 📊 Threat Model Validation Summary

| Validation Area | Result |
|---|---|
| Trust boundaries identified | ✅ Successful |
| STRIDE categories applied | ✅ Successful |
| CI/CD threat surface documented | ✅ Successful |
| Detection controls mapped | ✅ Successful |
| Wazuh monitoring path defined | ✅ Successful |
| Threat simulation path identified | ✅ Successful |
| Mitigations aligned to architecture | ✅ Successful |

---

## 🖼️ Evidence

![Trust Boundary Mapping](../../screenshots/01-architecture/S04_trust_boundaries_mapping.png)

![Threat Model Attack Surface](../../screenshots/01-architecture/S79_stride_threat_model_diagram.png)

![Attack Surface Visualization](../../screenshots/01-architecture/S83_attack_surface_visualization.png)

---

## 🔐 Security Significance

This threat model strengthens the architecture by ensuring that security risks are identified before validation and simulation.

It supports:

- Secure architecture design  
- Controlled adversary simulation  
- Detection engineering  
- DevSecOps security  
- Compliance evidence mapping  

The threat model confirms that the lab is not simply a technical build. It is a structured security architecture with identifiable risks and controls.

---

## ⚠️ Residual Risks

Some risks remain for future improvement:

| Residual Risk | Future Action |
|---|---|
| Detection latency not yet measured | Introduce timestamp benchmarking |
| Registry authentication can be improved | Add stronger registry access control |
| Runner compromise risk remains | Apply stricter runner isolation |
| Trivy gate not fully enforced | Enable fail-on-critical vulnerability mode |
| Custom Wazuh rules not yet tuned | Add detection engineering rules |

---

## 🧠 Research Reflection

This threat model supports the central research argument of the project:

> Many security failures begin with weak architecture, unclear trust boundaries, and poor validation.

By applying STRIDE to the lab, the architecture becomes more than a diagram. It becomes a testable security model.

The threat model provides the foundation for:

- Wazuh validation  
- CI/CD security  
- Threat simulation  
- Compliance mapping  
- Baseline snapshot creation  

---

## 🚀 Readiness Outcome

This section confirms that the lab is ready for:

- VM IP scheme documentation  
- Network validation  
- Wazuh deployment  
- Security hardening  
- CI/CD security validation  
- MITRE ATT&CK threat simulation  
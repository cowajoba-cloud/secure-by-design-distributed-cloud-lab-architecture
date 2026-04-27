# 📑 ISO 27001 Control Mapping

## 🎯 Objective

Map the lab’s implemented technical controls to relevant ISO 27001 control areas.

This mapping is not a certification claim.  
It is an evidence-based alignment exercise showing how the lab supports information security management principles.

---

## 🧠 ISO 27001 Alignment Context

ISO 27001 emphasizes risk-based information security management.

This lab supports that principle by demonstrating:

- Secure architecture design  
- Access restriction  
- Logging and monitoring  
- Vulnerability awareness  
- Secure software delivery  
- Incident detection  
- Evidence collection  

The mapping below connects lab activities to relevant ISO control themes.

---

## 📋 ISO 27001 Mapping Table

| ISO 27001 Control Theme | Lab Implementation | Evidence | Status |
|---|---|---|---|
| Access Control | Host-only network, restricted SSH, internal-only dashboard | S20–S28, S39 | ✅ Aligned |
| Identity & Authentication | Wazuh dashboard login, SSH authentication, GitHub runner registration | S31, S55 | ✅ Aligned |
| Logging | Wazuh log collection and dashboard visibility | S29–S38 | ✅ Aligned |
| Monitoring Activities | Wazuh detection alerts and brute-force monitoring | S65–S68 | ✅ Aligned |
| Network Security | Host-only segmentation and controlled VM communication | S20–S26 | ✅ Aligned |
| Segregation of Networks | Lab subnet isolation using `192.168.56.0/24` | S20–S26 | ✅ Aligned |
| Configuration Management | Static IP design, firewall rules, Docker setup | S21–S23, S39–S48 | ✅ Aligned |
| Technical Vulnerability Management | Trivy planned/integrated for container scanning | S58–S59 | ⏳ In Progress |
| Secure Development Lifecycle | CI/CD pipeline and secure Docker build | S51–S60 | ✅ Aligned |
| Use of Cryptography | HTTPS dashboard and TLS registry configuration | S31–S33, S48 | ✅ Aligned |
| Incident Management Support | Alert investigation and SIEM event visibility | S65–S68 | ✅ Aligned |
| Backup / Recovery Readiness | Baseline snapshot process | S77–S78 | ⏳ Pending Final Snapshot |

---

## 🖼️ Evidence

![ISO 27001 Control Mapping](../../screenshots/11-compliance/S69_iso27001_control_mapping.png)

![Control Validation Matrix](../../screenshots/11-compliance/S71_control_validation_matrix.png)

---

## 🔐 Key ISO-Aligned Security Capabilities

| Capability | Lab Evidence |
|---|---|
| Centralized monitoring | Wazuh Manager + Dashboard |
| Controlled access | Host-only network + SSH restrictions |
| Security event visibility | Wazuh alerts |
| Configuration control | Static IPs + firewall rules |
| Secure delivery | CI/CD pipeline + private registry |
| Detection validation | Brute-force simulation and alerting |

---

## ⚠️ Scope Clarification

This mapping is designed for lab-based alignment only.

It does not represent:

- Formal ISO 27001 certification  
- Full ISMS implementation  
- Organizational policy maturity  
- External audit completion  

Instead, it demonstrates practical technical control implementation relevant to ISO 27001 security objectives.

---

## 🧠 Research Reflection

ISO 27001 alignment helps translate technical lab work into governance language.

This is important because security architecture must be understood by both:

- Engineers implementing controls  
- Leaders evaluating risk  

The lab demonstrates how technical evidence can support governance traceability.

---

## 🚀 Readiness Outcome

This section prepares the project for:

- Security control evidence reporting  
- Audit-style documentation  
- Risk register integration  
- Governance-aware research presentation  
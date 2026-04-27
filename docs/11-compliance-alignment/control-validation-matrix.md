# 📊 Control Validation Matrix

## 🎯 Objective

Provide a structured validation matrix showing how the lab’s security controls were implemented, tested, and evidenced.

This section connects the technical implementation to measurable security outcomes.

The goal is to demonstrate that controls were not only designed, but also validated through practical evidence.

---

## 🧠 Compliance Context

The secure-by-design lab architecture includes controls across:

- Network segmentation  
- Endpoint monitoring  
- Centralized logging  
- Threat detection  
- System hardening  
- Secure CI/CD  
- Private artifact storage  
- Threat simulation and validation  

This matrix acts as the bridge between:

```text
Technical Implementation → Security Control → Evidence → Compliance Alignment
```

---

## 📋 Control Validation Matrix

| Control Area | Implemented Control | Validation Method | Evidence | Status |
|---|---|---|---|---|
| Network Segmentation | Host-only network | Ping and connectivity validation | S20–S26 | ✅ Validated |
| Static IP Allocation | Fixed VM addressing | `ip a`, ping tests | S21–S23 | ✅ Validated |
| SIEM Deployment | Wazuh Manager installed | Service status check | S29–S33 | ✅ Validated |
| Dashboard Access | Wazuh dashboard over HTTPS | Browser access validation | S31–S32 | ✅ Validated |
| Agent Monitoring | Wazuh agents registered | Dashboard agent status | S34–S38 | ✅ Validated |
| Firewall Hardening | UFW enabled | `sudo ufw status` | S39–S41 | ✅ Validated |
| Kernel Hardening | Sysctl rules applied | `sysctl --system` | S42–S43 | ✅ Validated |
| Audit Logging | Auditd enabled | Service validation | S44 | ✅ Validated |
| Docker Hardening | Rootless / controlled Docker | Docker info validation | S46–S48 | ✅ Validated |
| Private Registry | TLS-enabled registry | Registry API test | S48, S60 | ✅ Validated |
| CI/CD Pipeline | Self-hosted runner | GitHub Actions run | S55–S59 | ✅ Validated |
| Secure Docker Build | Image build and push | Build logs + registry check | S51–S54 | ✅ Validated |
| Threat Simulation | SSH brute-force simulation | Hydra + Wazuh alert | S61–S68 | ✅ Validated |
| MITRE Mapping | Brute Force mapped to T1110 | Detection mapping | S66 | ✅ Validated |
| Baseline Snapshot | Final secure state | Snapshot evidence | S73–S78 | ⏳ Pending / Final Stage |

---

## 🖼️ Evidence

![ISO 27001 Control Mapping](../../screenshots/11-compliance/S69_iso27001_control_mapping.png)

![NIST Control Mapping](../../screenshots/11-compliance/S70_nist_control_mapping.png)

![Control Validation Matrix](../../screenshots/11-compliance/S71_control_validation_matrix.png)

![Risk Register Summary](../../screenshots/11-compliance/S72_risk_register_summary.png)

---

## 📊 Validation Summary

| Category | Result |
|---|---|
| Architecture Controls | ✅ Validated |
| Monitoring Controls | ✅ Validated |
| Hardening Controls | ✅ Validated |
| CI/CD Controls | ✅ Validated |
| Threat Detection Controls | ✅ Validated |
| Compliance Evidence | ✅ Established |
| Baseline Snapshot | ⏳ Pending Final Capture |

---

## 🔐 Security Significance

This matrix demonstrates that the architecture has moved beyond configuration into validation.

Each control is supported by:

- A technical implementation  
- A validation method  
- Screenshot evidence  
- Compliance relevance  

This supports auditability, traceability, and research-grade documentation.

---

## ⚠️ Limitations

The current matrix validates implementation and functional effectiveness.

Further work should include:

- Quantitative detection latency measurement  
- Control maturity scoring  
- Automated compliance evidence generation  
- Continuous control monitoring  

---

## 🧠 Research Reflection

Control validation is essential because secure-by-design architecture must be measurable.

A control that is not validated remains an assumption.

This matrix turns assumptions into evidence by linking implementation to observable outcomes.

---

## 🚀 Readiness Outcome

This section confirms the lab is ready for:

- ISO 27001 alignment  
- NIST framework mapping  
- Risk register development  
- Final secure baseline documentation  
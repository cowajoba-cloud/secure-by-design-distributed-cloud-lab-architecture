# ⚠️ Risk Register Summary

## 🎯 Objective

Summarize key risks identified during the secure-by-design lab build and map them to implemented or planned controls.

The risk register supports governance traceability by connecting:

```text
Risk → Impact → Control → Evidence → Status
```

---

## 🧠 Risk Context

The lab contains multiple technical layers:

- Virtualization  
- Networking  
- Wazuh monitoring  
- Endpoint agents  
- Docker runtime  
- Private registry  
- GitHub Actions runner  
- Threat simulation environment  

Each layer introduces risk that must be documented and controlled.

---

## 📋 Risk Register

| Risk ID | Risk Description | Impact | Control / Mitigation | Evidence | Status |
|---|---|---|---|---|---|
| R01 | Dashboard exposed beyond lab network | Unauthorized SIEM access | Host-only access, HTTPS | S31–S33 | ✅ Controlled |
| R02 | Weak SSH access | Brute-force compromise | SSH monitoring, firewall rules | S39, S63–S65 | ✅ Controlled |
| R03 | Agent not forwarding logs | Loss of visibility | Agent validation checks | S34–S38 | ✅ Controlled |
| R04 | Registry exposed insecurely | Image tampering or leakage | TLS registry, internal-only access | S48, S60 | ✅ Controlled |
| R05 | Docker daemon misuse | Host compromise | Rootless Docker, restricted access | S46–S47 | ✅ Controlled |
| R06 | CI/CD runner compromise | Pipeline abuse | Self-hosted runner control | S55–S59 | ⚠️ Monitor |
| R07 | Vulnerable image pushed | Supply-chain risk | Trivy scanning | S58–S59 | ⏳ In Progress |
| R08 | Vulnerable targets exposed | External compromise | Host-only containment | S20–S26 | ✅ Controlled |
| R09 | Detection latency unknown | Delayed incident awareness | Future benchmarking | S67 | ⏳ Research Gap |
| R10 | No automated response | Manual triage dependency | Future playbooks/SOAR | S68 | ⏳ Future Work |
| R11 | Duplicate or broken workflows | CI/CD reliability issue | Workflow cleanup and validation | S57–S59 | ✅ Controlled |
| R12 | DNS instability in runner VM | Pipeline dependency failure | Local pipeline adjustment and troubleshooting | S58–S59 | ✅ Controlled |

---

## 📊 Risk Priority Summary

| Risk Level | Count | Notes |
|---|---|---|
| High | 3 | Runner compromise, registry exposure, SSH compromise |
| Medium | 6 | Visibility, vulnerable images, workflow reliability |
| Low | 3 | Documentation and future measurement gaps |

---

## 🖼️ Evidence

![Risk Register Summary](../../screenshots/11-compliance/S72_risk_register_summary.png)

![Control Validation Matrix](../../screenshots/11-compliance/S71_control_validation_matrix.png)

---

## 🔐 Security Significance

The risk register demonstrates that the lab follows a risk-aware design model.

It shows that risks were:

- Identified  
- Mapped to controls  
- Validated through evidence  
- Tracked for improvement  

This improves the credibility of the project as both an engineering build and research artifact.

---

## ⚠️ Residual Risks

Residual risks remain in the following areas:

- CI/CD runner hardening  
- Automated vulnerability gate enforcement  
- Detection latency measurement  
- Incident response automation  
- Long-term key and credential management  

These are planned future improvements.

---

## 🧠 Research Reflection

The risk register connects hands-on engineering to governance thinking.

This matters because secure-by-design architecture must answer two questions:

1. What did we build?  
2. What risk does it reduce?

The lab now provides evidence for both.

---

## 🚀 Readiness Outcome

This section confirms that the compliance layer is ready for:

- Baseline snapshot finalization  
- Research paper evidence mapping  
- LinkedIn/GitHub publication  
- Future security maturity scoring  
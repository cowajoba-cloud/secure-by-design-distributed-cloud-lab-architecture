# 🏛️ NIST Framework Mapping

## 🎯 Objective

Map the lab’s security architecture and validation evidence to NIST cybersecurity functions.

This section demonstrates how the lab supports structured cybersecurity capability across:

- Govern  
- Identify  
- Protect  
- Detect  
- Respond  
- Recover  

---

## 🧠 NIST Alignment Context

The NIST framework provides a practical model for organizing cybersecurity outcomes.

This lab aligns to NIST by demonstrating:

- Asset identification  
- Risk-aware architecture  
- Protective controls  
- Monitoring and detection  
- Incident analysis  
- Baseline recovery planning  

---

## 📋 NIST Mapping Table

| NIST Function | Lab Implementation | Evidence | Status |
|---|---|---|---|
| Govern | Compliance mapping, risk register, control validation | S69–S72 | ✅ Aligned |
| Identify | VM inventory, IP scheme, architecture documentation | S01–S04, S21–S23 | ✅ Aligned |
| Protect | Firewall hardening, segmentation, SSH restriction, Docker hardening | S20–S28, S39–S48 | ✅ Aligned |
| Detect | Wazuh SIEM, agents, brute-force detection, FIM alerts | S29–S38, S63–S68 | ✅ Aligned |
| Respond | Alert investigation and incident dashboard review | S65–S68 | ✅ Partially Aligned |
| Recover | Baseline snapshots and rollback planning | S73–S78 | ⏳ Pending Final Snapshot |

---

## 🔍 Detailed Mapping

### 🧭 Govern

Governance is represented through:

- ISO 27001 mapping  
- NIST mapping  
- Risk register summary  
- Control validation matrix  

This shows that the lab connects technical work to structured oversight.

---

### 🧩 Identify

The lab identifies critical assets through:

- Architecture diagrams  
- VM roles  
- IP allocation scheme  
- Network topology  

---

### 🛡️ Protect

Protective controls include:

- Host-only network segmentation  
- Firewall rules  
- System hardening  
- Docker hardening  
- TLS-enabled registry  

---

### 👁️ Detect

Detection capability includes:

- Wazuh Manager  
- Endpoint agents  
- Security event ingestion  
- SSH brute-force alerts  
- File Integrity Monitoring  

---

### 🚨 Respond

Response capability is demonstrated through:

- Alert investigation  
- Dashboard-based triage  
- MITRE mapping  
- Detection timeline analysis  

---

### 🔁 Recover

Recovery readiness is supported by:

- VirtualBox snapshots  
- Secure baseline documentation  
- Versioned lab state  

This is completed in the baseline snapshot section.

---

## 🖼️ Evidence

![NIST Control Mapping](../../screenshots/11-compliance/S70_nist_control_mapping.png)

![Control Validation Matrix](../../screenshots/11-compliance/S71_control_validation_matrix.png)

---

## 📊 NIST Alignment Summary

| Function | Alignment Level |
|---|---|
| Govern | ✅ Strong |
| Identify | ✅ Strong |
| Protect | ✅ Strong |
| Detect | ✅ Strong |
| Respond | ✅ Developing |
| Recover | ⏳ Pending Snapshot Completion |

---

## 🔐 Security Significance

NIST mapping helps show that the lab is not a collection of tools.

It is a structured cybersecurity capability model.

Each function demonstrates how the architecture supports practical security outcomes.

---

## ⚠️ Limitations

Current limitations include:

- Response workflows are not fully automated  
- Recovery is based on snapshot readiness, not full disaster recovery testing  
- Detection performance metrics are not yet quantitatively benchmarked  

---

## 🧠 Research Reflection

NIST alignment positions the lab as a full security lifecycle environment.

It demonstrates that secure-by-design work must include:

- Governance  
- Asset awareness  
- Protection  
- Detection  
- Response  
- Recovery planning  

This supports both technical and strategic security thinking.

---

## 🚀 Readiness Outcome

This section prepares the lab for:

- Risk register development  
- Compliance evidence packaging  
- Incident response playbook creation  
- Baseline snapshot validation  
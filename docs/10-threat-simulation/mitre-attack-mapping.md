# ⚔️ MITRE ATT&CK Threat Simulation & Detection Validation

## 🎯 Objective

Validate the secure-by-design architecture by simulating controlled adversary activity and mapping the observed behavior to the **MITRE ATT&CK framework**.

This section demonstrates that the lab can:

- Generate controlled attack activity  
- Capture local system logs  
- Forward telemetry through Wazuh agents  
- Detect malicious behavior using SIEM rules  
- Correlate events into alerts  
- Support investigation-ready evidence  

The goal is not only to prove that the environment works, but to prove that it can **detect, evidence, and explain attacker behavior**.

---

## 🧠 Threat Simulation Context

The lab architecture supports the following detection flow:

```text
Kali Linux → Target VM → System Logs → Wazuh Agent → Wazuh Manager → Dashboard Alert
```

This validates that the architecture supports:

- Controlled adversary simulation  
- Endpoint telemetry collection  
- SIEM-based detection  
- Alert visibility  
- Security investigation  

---

## 🧩 Simulation Environment

| Component | Role |
|---|---|
| Kali Linux | Attack simulation machine |
| Ubuntu Server / Target VM | Monitored target system |
| Wazuh Agent | Endpoint telemetry collector |
| Wazuh Manager | Event processing and correlation |
| Wazuh Dashboard | Alert visualization and investigation |

---

## 🎯 MITRE ATT&CK Mapping

| Activity | MITRE Technique | Technique ID |
|---|---|---|
| SSH brute-force attempt | Brute Force | T1110 |
| Repeated authentication failures | Valid Accounts / Credential Access Indicator | T1110-related |
| Log-based detection | Security Event Monitoring | Detection control |
| Alert correlation | SIEM detection engineering | Detection control |

---

## 🧪 1. Attack Environment Validation

## 🎯 Objective

Confirm that the Kali attack machine is ready and can communicate with the target system before attack execution.

---

## ⚙️ Validation Commands

Check IP address:

```bash
ip a
```

Confirm target reachability:

```bash
ping 192.168.56.10
```

---

## 🖼️ Evidence

![Kali Attack Environment Ready](../../screenshots/10-threat-simulation/S61_kali_attack_environment_ready.png)

![Target Reachability From Kali](../../screenshots/10-threat-simulation/S62_target_reachability_from_kali.png)

---

## 📌 Observation

- Kali Linux was active inside the controlled lab network  
- Target system was reachable  
- Attack path was validated before simulation  

---

## 🧪 2. SSH Brute Force Attack Simulation

## 🎯 Objective

Simulate SSH brute-force behavior against the monitored target system.

This test validates whether repeated failed authentication attempts are captured and detected.

---

## ⚙️ Attack Command

```bash
hydra -l ubuntu -P passwords.txt ssh://192.168.56.10
```

Alternative format:

```bash
hydra -l <username> -P <password-list> ssh://<target-ip>
```

---

## 🔐 Controlled Testing Note

This simulation was executed only inside the isolated lab environment.

The purpose was to generate controlled authentication failure events for detection validation.

---

## 🖼️ Evidence

![SSH Brute Force Execution](../../screenshots/10-threat-simulation/S63_ssh_bruteforce_execution.png)

---

## 📌 Attack Outcome

- Brute-force activity was generated  
- SSH authentication failures were produced  
- Target system logs recorded failed attempts  

---

## 🧪 3. Local Authentication Log Validation

## 🎯 Objective

Confirm that the target system locally recorded the failed SSH authentication attempts.

This validates that the attack generated observable system-level evidence before SIEM ingestion.

---

## ⚙️ Log Review Command

```bash
sudo tail -f /var/log/auth.log
```

or:

```bash
sudo grep "Failed password" /var/log/auth.log
```

---

## 🖼️ Evidence

![Authentication Log Failed Attempts](../../screenshots/10-threat-simulation/S64_auth_log_failed_attempts.png)

---

## 📌 Validation Outcome

- Failed SSH attempts appeared in local authentication logs  
- Timestamped evidence was generated  
- The Wazuh agent had source telemetry to forward  

---

## 🧪 4. Wazuh Brute Force Detection

## 🎯 Objective

Validate that Wazuh ingests the authentication logs and triggers brute-force detection alerts.

---

## 🧠 Detection Flow

```text
Failed SSH Login → /var/log/auth.log → Wazuh Agent → Wazuh Manager → Alert
```

---

## 🖼️ Evidence

![Wazuh Brute Force Alert](../../screenshots/10-threat-simulation/S65_wazuh_bruteforce_alert.png)

---

## 📌 Detection Outcome

- SSH failure logs were ingested  
- Wazuh correlation rules were triggered  
- Alert was visible in the dashboard  
- Detection pipeline functioned correctly  

---

## 🧪 5. MITRE ATT&CK Classification

## 🎯 Objective

Map the observed brute-force behavior to MITRE ATT&CK.

---

## 📊 MITRE Mapping

| Field | Value |
|---|---|
| Tactic | Credential Access |
| Technique | Brute Force |
| Technique ID | T1110 |
| Data Source | Authentication logs |
| Detection Tool | Wazuh SIEM |
| Detection Evidence | Repeated SSH authentication failures |

---

## 🖼️ Evidence

![MITRE T1110 Mapping](../../screenshots/10-threat-simulation/S66_mitre_attack_mapping_t1110.png)

---

## 📌 Interpretation

This confirms that the simulated attack aligns with a recognized adversary behavior pattern.

Mapping the alert to MITRE ATT&CK improves:

- Threat understanding  
- Detection documentation  
- Incident analysis  
- Compliance evidence  
- Research traceability  

---

## 🧪 6. Detection Timeline Analysis

## 🎯 Objective

Establish a timeline between attack execution, local log creation, SIEM ingestion, and dashboard alert visibility.

---

## 🧠 Timeline Model

```text
T1: Hydra attack launched
T2: Target records failed SSH login attempts
T3: Wazuh agent forwards logs
T4: Wazuh manager processes events
T5: Alert appears in dashboard
```

---

## 🖼️ Evidence

![Attack Detection Timeline](../../screenshots/10-threat-simulation/S67_attack_detection_timeline.png)

---

## 📌 Timeline Insight

The timeline confirms that detection is not theoretical.

The architecture produced a traceable chain of evidence from attacker activity to SIEM alert.

---

## 🧪 7. Incident Analysis Dashboard

## 🎯 Objective

Review the detected brute-force event from an investigation perspective.

---

## 🔍 Investigation Focus

The alert was reviewed for:

- Source IP address  
- Target host  
- Rule name  
- Severity level  
- Timestamp  
- Authentication failure pattern  
- MITRE mapping  

---

## 🖼️ Evidence

![Incident Analysis Dashboard](../../screenshots/10-threat-simulation/S68_incident_analysis_dashboard.png)

---

## 📌 Investigation Outcome

The alert provided enough context to support incident triage and analysis.

This confirms that the SIEM output is not only visible, but also operationally useful.

---

## 📊 Threat Simulation Validation Results

| Validation Area | Result |
|---|---|
| Kali attack machine ready | ✅ Successful |
| Target reachable from attacker machine | ✅ Successful |
| SSH brute-force executed | ✅ Successful |
| Authentication failures logged locally | ✅ Successful |
| Wazuh ingested authentication events | ✅ Successful |
| Brute-force alert generated | ✅ Successful |
| MITRE ATT&CK mapping completed | ✅ Successful |
| Detection timeline established | ✅ Successful |
| Incident dashboard reviewed | ✅ Successful |

---

## 🔐 Security Significance

This simulation confirms that the architecture can detect credential-based attacks through:

- Endpoint log visibility  
- Centralized SIEM ingestion  
- Detection rule correlation  
- MITRE ATT&CK mapping  
- Alert investigation  

The lab therefore demonstrates operational detection capability, not just tool installation.

---

## ⚠️ Threat Considerations

Brute-force attacks remain a common real-world threat because weak credentials, exposed SSH services, and insufficient monitoring can allow attackers to gain access.

Relevant risks include:

- Credential guessing  
- Unauthorized remote access  
- Account compromise  
- Privilege escalation after login  
- Persistence using valid credentials  

Mitigations include:

- Strong password policy  
- SSH hardening  
- Account lockout controls  
- Network restriction  
- SIEM monitoring  
- Alert investigation workflow  

---

## 🧠 Research Reflection

This simulation validates a key secure-by-design principle:

> Security architecture must be tested against realistic adversary behavior.

The lab confirms that:

- Attack activity can be generated safely  
- Logs are created at the endpoint  
- Telemetry flows into the SIEM  
- Alerts are generated  
- Evidence supports investigation  

This transforms the environment from a static lab into an empirical validation platform.

---

## 🚀 Readiness Outcome

This section confirms the lab is ready for:

- Advanced MITRE ATT&CK simulations  
- Detection rule tuning  
- Detection latency measurement  
- High-volume attack testing  
- Compliance evidence mapping  
- Research-grade benchmarking  

---

## 🎯 Long-Term Direction

The next stage is to move from:

> Functional detection validation

to:

> Measurable detection performance benchmarking

Future work should include:

- Detection latency measurement  
- False-positive analysis  
- Alert severity evaluation  
- Multi-node attack simulation  
- Automated detection reporting  
- CI/CD-triggered security validation  
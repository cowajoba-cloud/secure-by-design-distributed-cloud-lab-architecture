# 🎯 MITRE ATT&CK Threat Simulation & Mapping

---

# **📌 Objective**

Validate detection capability by simulating controlled adversary behavior and mapping alerts to MITRE ATT&CK techniques.

---

# **🧠 Methodology**

1. Execute controlled attack scenario
2. Observe Wazuh alert generation
3. Map alert to MITRE technique
4. Document detection effectiveness

---

# **🧪 Scenario 1 — SSH Brute Force**

### Technique
T1110 – Brute Force

### Execution
Multiple failed SSH login attempts from Kali Linux to Ubuntu Server.

```bash
hydra -l user -P passwords.txt ssh://192.168.56.10


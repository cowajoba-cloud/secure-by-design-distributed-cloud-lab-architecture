
# 📊 Wazuh Dashboard Access & Validation

## 🎯 Objective

Validate **dashboard accessibility, authentication, and operational integrity** of the Wazuh SIEM interface.

This step confirms that:

- The dashboard is reachable  
- Authentication is functioning  
- Backend services are connected  
- Security telemetry is visible  

---

## 🌐 Access Configuration

Access the Wazuh Dashboard via HTTPS: https://192.168.56.100
Note: The dashboard is exposed only within the host-only network, ensuring restricted accessibility and preventing external internet exposure.

---
## 🔐 Authentication & Access Control

Access to the Wazuh Dashboard requires:

- Valid credentials generated during Wazuh installation  
- HTTPS-secured browser session  
- Network-level access to the Wazuh Manager host  
- Access from approved lab systems (Ubuntu Desktop, Kali Linux, Windows host, or macOS SSH tunnel)

The dashboard is **not publicly exposed**. Access is restricted to the internal lab network to reduce attack surface and protect sensitive security telemetry.

---

## 🧠 Architectural Context

The Wazuh Dashboard sits at the top of the detection pipeline:

Endpoint → Wazuh Agent → Wazuh Manager → Indexer → Dashboard
This confirms that:

- Logs are collected from monitored endpoints
- Events are processed by the Wazuh Manager
- Alerts are indexed for search and correlation
- Security data is visualized through the dashboard

The dashboard is therefore not only a user interface. It is evidence that the detection pipeline is functioning end-to-end.

---

## 🧪 Validation Procedure
1️⃣ Open Dashboard
https://192.168.56.100
Access: https://<server-ip>:5601

---

## 📷 Dashboard Login Screen

Save as:  
`screenshots/03-wazuh/03_dashboard_login.png`

![Dashboard Login](../../screenshots/03-wazuh/03_dashboard_login.png)

---

## 📷 Dashboard Home

Save as:  
`screenshots/03-wazuh/04_dashboard_home.png`

![Dashboard Home](../../screenshots/03-wazuh/04_dashboard_home.png)

---

## 2️⃣ Authenticate
Enter valid credentials
Confirm successful login

---

## 3️⃣ Verify System State

Check that:
- Dashboard loads successfully
- System overview panels are visible
- No major backend service errors are displayed
- Wazuh Manager, Indexer, and Dashboard components are functioning

---

## 4️⃣ Confirm Data Ingestion

Validate that:
- Registered agents appear in the dashboard
- Events are being logged
- Alerts are visible
- Endpoint telemetry is searchable


## 📊 Validation Results
## 📊 Validation Results

| Check                         | Result           |
|------------------------------|------------------|
| Dashboard Accessible         | ✅ Successful     |
| Authentication Working       | ✅ Successful     |
| HTTPS Session Active         | ✅ Successful     |
| Data Visualization Active    | ✅ Successful     |
| Backend Services Connected   | ✅ Successful     |
| Agent Visibility Confirmed   | ✅ Successful     |

--- 

## 🔐 Security Considerations

The following controls were applied or validated:

- 🔒 Default credentials changed or secured
- 🌐 Access restricted to host-only network
- 🔐 HTTPS enforced for dashboard communication
- 🚫 No public exposure of dashboard endpoint
- 🧱 Dashboard access limited to controlled lab systems
- 👁️ Dashboard used as central visibility point for detection engineering
- ⚠️ Threat Considerations

---

## Potential risks include:
- Unauthorized access to security telemetry
- Credential compromise
- Exposure of sensitive endpoint logs
- Dashboard misuse after internal compromise

## Mitigations include:
- Network isolation
- Strong authentication
- Internal-only dashboard access
- Controlled administrative access
- Continuous monitoring of endpoint activity

## 🧠 Research Reflection
The dashboard serves as the observable layer of the security architecture.

Its successful operation confirms:
- End-to-end telemetry flow
- Integrity of the detection pipeline
- Security event visibility
- Readiness for threat simulation and alert validation

---

From a secure-by-design perspective, this validates that visibility is embedded into the architecture -before attack simulation begins.

## 🚀 Readiness Outcome
This step confirms the environment is ready for:

- Agent registration
- Endpoint monitoring
- Threat simulation using MITRE ATT&CK
- Detection validation workflows
- Compliance evidence collection

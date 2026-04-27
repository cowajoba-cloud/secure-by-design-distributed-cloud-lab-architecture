# 🔍 VM Communication Validation

## 🎯 Objective

Validate **internal network segmentation, controlled connectivity, and communication integrity** across all virtual machines.

This step confirms that the lab environment is:

- Functionally connected
- Properly segmented
- Ready for secure operations and threat simulation

---

## 🧩 Validation Scope

The following communication paths were tested:

| Source | Destination | Purpose |
|------|------------|--------|
| Ubuntu Desktop | Ubuntu Server | Internal service validation |
| Kali Linux | Ubuntu Server | Attack path validation |
| Windows Host | Ubuntu Server | Cross-platform validation |
| Ubuntu Desktop | Docker Registry | CI/CD validation |

---

## 🧪 Tests Performed

### 1️⃣ Ubuntu Desktop → Ubuntu Server

bash
ping 192.168.56.10

---

## 2️⃣ Kali Linux → Ubuntu Server
ping 192.168.56.10

---

3️⃣ Windows Host → Ubuntu Server
ping 192.168.56.10

---

4️⃣ CI/CD VM → Private Registry
curl -k https://192.168.56.100:5000/v2/_catalog

---

## 📊 Validation Results
## 📊 Validation Results

| Test                         | Result           |
|------------------------------|------------------|
| Internal VM Communication     | Successful ✅     |
| Cross-platform Communication  | Successful ✅     |
| Registry Connectivity         | Successful ✅     |
| Packet Loss                   | None observed ❌  |

## 🖼️ Evidence

![Figure S24](../../screenshots/05-network-validation/S24_ping_test_desktop_to_server.png)

![Figure S25](../../screenshots/05-network-validation/S25_ping_test_kali_to_server.png)

![Figure S26](../../screenshots/05-network-validation/S26_inter_vm_connectivity_validation.png)
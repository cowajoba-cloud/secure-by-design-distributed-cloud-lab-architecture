# 🔍 Trivy Integration for Container Security Scanning

## 🎯 Objective

Integrate Trivy vulnerability scanning into the CI/CD pipeline to detect known vulnerabilities in container images before registry publication.

This strengthens the DevSecOps pipeline by adding security validation before artifact distribution.

---

## 🧠 Architectural Context

Trivy belongs in the security validation stage of the pipeline.

```text
Docker Build → Trivy Scan → Tag Image → Push to Registry
```

The scan step helps shift security left by identifying vulnerabilities before deployment.

---

## 🔐 Why Trivy Matters

Container images can contain:

- Vulnerable packages  
- Outdated dependencies  
- Insecure base images  
- Misconfigured software components  

Trivy helps identify these issues early in the delivery lifecycle.

---

## ⚙️ Installation

Install Trivy on the self-hosted runner VM:

```bash
sudo apt update
sudo apt install wget apt-transport-https gnupg -y
wget -qO - https://aquasecurity.github.io/trivy-repo/deb/public.key | sudo apt-key add -
echo deb https://aquasecurity.github.io/trivy-repo/deb $(lsb_release -sc) main | sudo tee /etc/apt/sources.list.d/trivy.list
sudo apt update
sudo apt install trivy -y
```

Verify installation:

```bash
trivy --version
```

---

## 🧪 Manual Scan Validation

Scan the local image:

```bash
trivy image secure-app:v1
```

Security-focused scan:

```bash
trivy image --severity HIGH,CRITICAL secure-app:v1
```

---

## ⚙️ Pipeline Integration

Recommended workflow step:

```yaml
- name: Scan Image with Trivy
  run: |
    trivy image --severity HIGH,CRITICAL secure-app:v1
```

During initial validation, this may be run in observation mode:

```yaml
- name: Scan Image with Trivy
  run: |
    trivy image --severity HIGH,CRITICAL secure-app:v1 || true
```

Observation mode allows the pipeline to complete while scan results are reviewed.

After validation, remove `|| true` to enforce policy-based failure.

---

## 📊 Validation Results

| Check | Result |
|---|---|
| Trivy installed | ⏳ Pending / To Validate |
| Image scan executed | ⏳ Pending / To Validate |
| High/Critical vulnerabilities identified | ⏳ Pending / To Validate |
| Pipeline security gate configured | ⏳ Pending / To Validate |
| Policy failure mode enabled | ⏳ Future Enhancement |

---

## 🖼️ Evidence

![Pipeline Execution Logs](../../screenshots/09-ci-cd/S58_pipeline_execution_logs.png)

![Pipeline Success](../../screenshots/09-ci-cd/S59_pipeline_success.png)

---

## 🔐 Security Significance

Trivy integration supports:

- Early vulnerability detection  
- Build-time security assurance  
- Secure SDLC alignment  
- Reduced risk of vulnerable images entering registry  
- Stronger DevSecOps maturity  

---

## ⚠️ Threat Considerations

Without image scanning:

- Vulnerable images may be pushed into trusted registry  
- Known CVEs may remain undetected  
- Pipeline may validate functionality but not security  
- Supply-chain risk increases  

Trivy mitigates this by introducing vulnerability detection before image distribution.

---

## 🧠 Research Reflection

Trivy integration represents the transition from automation to security automation.

A CI/CD pipeline is not secure simply because it runs successfully.

It becomes secure when it validates the artifact before release.

---

## 🚀 Readiness Outcome

This section prepares the pipeline for:

- Vulnerability scanning  
- Security gate enforcement  
- Secure SDLC evidence  
- Compliance mapping  
- Future policy-as-code integration  
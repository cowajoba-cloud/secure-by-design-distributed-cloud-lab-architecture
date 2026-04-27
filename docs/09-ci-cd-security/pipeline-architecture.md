# ⚙️ Secure CI/CD Pipeline Architecture

## 🎯 Objective

Design and validate a secure CI/CD pipeline that supports controlled software delivery within the lab architecture.

This pipeline demonstrates how DevSecOps practices can be embedded into the secure-by-design environment by connecting:

- GitHub repository changes  
- Self-hosted runner execution  
- Docker image build  
- Private registry push  
- Registry validation  

---

## 🧠 Architectural Context

The CI/CD pipeline sits inside the software delivery layer of the lab.

```text
Developer Commit → GitHub Repository → Self-hosted Runner → Docker Build → Private Registry → Validation
```

This design avoids reliance on public runners and keeps build execution inside the controlled lab environment.

---

## 🔐 Security Design Rationale

The pipeline was designed to support:

- Controlled build execution  
- Internal artifact handling  
- Reduced public exposure  
- Repeatable validation  
- Stronger supply-chain visibility  

The pipeline is not only an automation mechanism. It is part of the architecture’s security boundary.

---

## 🔄 Pipeline Flow

| Stage | Purpose |
|---|---|
| Repository Push | Trigger workflow execution |
| Self-hosted Runner | Execute job inside controlled lab |
| Docker Build | Build application container |
| Image Tagging | Prepare image for registry storage |
| Registry Push | Store artifact internally |
| Registry Validation | Confirm image availability |

---

## 🧪 Workflow Logic

The workflow follows this structure:

```yaml
name: Secure CI/CD Pipeline

on:
  push:
    branches:
      - main

jobs:
  build-scan-push:
    runs-on: [self-hosted, Linux, X64, docker]

    steps:
      - name: Check Docker
        run: |
          docker ps
          docker version

      - name: Build Image
        run: |
          docker build -t secure-app:v1 /home/charlie/secure-by-design-distributed-cloud-lab-architecture/docker/secure-app

      - name: Tag Image
        run: |
          docker tag secure-app:v1 192.168.56.100:5000/secure-app:v1

      - name: Push Image to Private Registry
        run: |
          docker push 192.168.56.100:5000/secure-app:v1

      - name: Validate Registry Push
        run: |
          curl -k https://192.168.56.100:5000/v2/_catalog
```

---

## 📊 Validation Results

| Validation Area | Result |
|---|---|
| Runner registered | ✅ Successful |
| Runner listening for jobs | ✅ Successful |
| Pipeline triggered | ✅ Successful |
| Docker build executed | ✅ Successful |
| Image tagged | ✅ Successful |
| Image pushed to private registry | ✅ Successful |
| Registry validation completed | ✅ Successful |

---

## 🖼️ Evidence

![CI VM Docker Ready](../../screenshots/09-ci-cd/S49_ci_vm_docker_ready.png)

![Registry Connectivity Test](../../screenshots/09-ci-cd/S50_registry_connectivity_test.png)

![Pipeline Triggered](../../screenshots/09-ci-cd/S57_pipeline_triggered.png)

![Pipeline Execution Logs](../../screenshots/09-ci-cd/S58_pipeline_execution_logs.png)

![Pipeline Success](../../screenshots/09-ci-cd/S59_pipeline_success.png)

![Registry Catalog Validation](../../screenshots/09-ci-cd/S60_registry_catalog_validation.png)

---

## 🔐 Security Significance

The CI/CD pipeline strengthens the architecture by introducing:

- Controlled automation  
- Internal build execution  
- Private artifact storage  
- Traceable software delivery  
- Reduced exposure to public execution environments  

This supports secure software engineering principles by validating software delivery inside the trusted lab boundary.

---

## ⚠️ Threat Considerations

Potential CI/CD risks include:

- Pipeline misconfiguration  
- Runner compromise  
- Malicious build instructions  
- Insecure image distribution  
- Unauthorized registry push  

Mitigations include:

- Self-hosted runner inside controlled VM  
- Private registry access  
- Internal-only registry communication  
- Workflow visibility through GitHub Actions logs  
- Future integration of Trivy security scanning  

---

## 🧠 Research Reflection

This pipeline demonstrates that secure architecture must include the software delivery process.

A system may be well segmented and monitored, but insecure software delivery can still introduce risk.

This lab shows that secure-by-design thinking extends beyond infrastructure into CI/CD automation.

---

## 🚀 Readiness Outcome

The CI/CD architecture is now ready for:

- Docker build validation  
- Security scanning integration  
- Registry-based artifact control  
- DevSecOps evidence collection  
- Compliance mapping  
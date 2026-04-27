# 🚀 GitHub Actions Self-Hosted Runner

## 🎯 Objective

Deploy and validate a GitHub Actions self-hosted runner inside the lab environment.

The runner enables GitHub workflows to execute directly on the Ubuntu Desktop CI/CD VM instead of relying on public hosted runners.

---

## 🧠 Architectural Context

The runner acts as the bridge between GitHub and the internal lab infrastructure.

```text
GitHub Actions → Self-hosted Runner → Docker Engine → Private Registry
```

This allows the pipeline to interact with internal services such as:

- Docker Engine  
- Private registry  
- Local secure app build context  
- Internal network resources  

---

## 🔐 Security Rationale

Using a self-hosted runner provides:

- Control over execution environment  
- Internal access to private registry  
- Visibility into build activity  
- Reduced dependence on external infrastructure  

However, it also introduces risk because workflows execute commands on the runner VM.

Therefore, the runner must be treated as a sensitive system.

---

## ⚙️ Runner Installation

Create runner directory:

```bash
mkdir ~/actions-runner
cd ~/actions-runner
```

Download runner package:

```bash
wget -4 https://github.com/actions/runner/releases/download/v2.317.0/actions-runner-linux-x64-2.317.0.tar.gz
```

Extract package:

```bash
tar xzf actions-runner-linux-x64-2.317.0.tar.gz
```

---

## 🔗 Runner Registration

From GitHub:

```text
Repository → Settings → Actions → Runners → New self-hosted runner
```

Run the generated configuration command:

```bash
./config.sh --url https://github.com/cowajoba-cloud/secure-by-design-distributed-cloud-lab-architecture --token <TOKEN>
```

Recommended runner name:

```text
ubuntu-secure-runner
```

Recommended labels:

```text
self-hosted, Linux, X64, docker
```

---

## ▶️ Start Runner

```bash
cd ~/actions-runner
./run.sh
```

Expected output:

```text
Listening for Jobs
```

---

## 🧪 Validation Procedure

Confirm runner registration in GitHub:

```text
Repository → Settings → Actions → Runners
```

Confirm the runner appears as:

```text
ubuntu-secure-runner — Online
```

Confirm terminal output shows:

```text
Listening for Jobs
```

---

## 📊 Validation Results

| Check | Result |
|---|---|
| Runner downloaded | ✅ Successful |
| Runner extracted | ✅ Successful |
| Runner registered with GitHub | ✅ Successful |
| Runner labels configured | ✅ Successful |
| Runner listening for jobs | ✅ Successful |
| Pipeline job picked up | ✅ Successful |

---

## 🖼️ Evidence

![GitHub Runner Registered](../../screenshots/09-ci-cd/S55_github_runner_registered.png)

![Runner Listening for Jobs](../../screenshots/09-ci-cd/S56_runner_listening_for_jobs.png)

![Pipeline Triggered](../../screenshots/09-ci-cd/S57_pipeline_triggered.png)

---

## 🔐 Security Considerations

The runner should:

- Not run as root  
- Be restricted to trusted repositories  
- Have limited access to secrets  
- Be monitored by Wazuh where possible  
- Avoid unnecessary privileged permissions  

---

## ⚠️ Operational Lessons

During implementation, the runner setup revealed several real-world CI/CD issues:

- Runner download failures caused by DNS issues  
- Incorrect workflow paths  
- Duplicate workflow files  
- YAML syntax errors  
- Docker build context mismatch  
- Git identity and push authentication issues  

These issues reflect realistic DevSecOps troubleshooting conditions.

---

## 🧠 Research Reflection

The self-hosted runner demonstrates how CI/CD infrastructure becomes part of the security architecture.

It is not only an automation tool. It becomes a trusted execution node that must be secured, monitored, and validated.

---

## 🚀 Readiness Outcome

The runner is now ready for:

- Secure Docker builds  
- Registry push workflows  
- Vulnerability scanning integration  
- CI/CD evidence generation  
- DevSecOps security validation  
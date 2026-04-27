
# ⚙ GitHub Actions Workflow

## 🎯 Objective

Automate security validation.

---

## 🧩 Example Workflow

`.github/workflows/security-scan.yml`

```yaml
name: Security Scan
on: [push]
jobs:
  scan:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v3
      - name: Run Trivy
        run: trivy fs .

# 📷 GitHub Actions Success

Save as:
screenshots/05-ci-cd/03_github_actions_success.png



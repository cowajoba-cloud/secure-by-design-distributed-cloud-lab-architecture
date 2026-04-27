# 🐳 Secure Docker Build Process

## 🎯 Objective

Validate secure Docker image build and push operations within the CI/CD pipeline.

This section documents how the lab builds a container image, tags it, pushes it to the private registry, and validates successful artifact storage.

---

## 🧠 Architectural Context

The Docker build process is part of the software supply-chain layer.

```text
Source Code → Dockerfile → Docker Image → Registry Tag → Private Registry
```

This ensures that software artifacts are created and stored inside the controlled lab environment.

---

## 📁 Build Context

The secure application Dockerfile is located at:

```text
docker/secure-app/Dockerfile
```

Expected files:

```text
docker/
└── secure-app/
    ├── Dockerfile
    └── index.html
```

---

## 🧩 Dockerfile

Example Dockerfile:

```dockerfile
FROM nginx:alpine
COPY index.html /usr/share/nginx/html/index.html
```

---

## ⚙️ Manual Build Validation

Before pipeline automation, the image should build locally:

```bash
docker build -t secure-app:v1 ./docker/secure-app
```

Expected result:

```text
Successfully tagged secure-app:v1
```

---

## 🏷️ Image Tagging

Tag image for private registry:

```bash
docker tag secure-app:v1 192.168.56.100:5000/secure-app:v1
```

---

## 📦 Push to Private Registry

Push image:

```bash
docker push 192.168.56.100:5000/secure-app:v1
```

---

## 🔍 Registry Validation

Confirm registry contains the image:

```bash
curl -k https://192.168.56.100:5000/v2/_catalog
```

Expected output:

```json
{"repositories":["secure-app"]}
```

---

## 📊 Validation Results

| Check | Result |
|---|---|
| Dockerfile exists | ✅ Successful |
| Local Docker build | ✅ Successful |
| Image tagging | ✅ Successful |
| Image push | ✅ Successful |
| Registry catalog validation | ✅ Successful |
| Pipeline build execution | ✅ Successful |

---

## 🖼️ Evidence

![Secure App Dockerfile](../../screenshots/09-ci-cd/S51_dockerfile_secure_app.png)

![Docker Build Success](../../screenshots/09-ci-cd/S52_docker_build_success.png)

![Docker Image Tagging](../../screenshots/09-ci-cd/S53_docker_image_tagging.png)

![Docker Push Success](../../screenshots/09-ci-cd/S54_docker_push_success.png)

![Registry Catalog Validation](../../screenshots/09-ci-cd/S60_registry_catalog_validation.png)

---

## 🔐 Security Significance

The secure Docker build process supports:

- Repeatable artifact creation  
- Controlled image distribution  
- Internal registry storage  
- Reduced dependency on public registries  
- Traceability across pipeline stages  

---

## ⚠️ Threat Considerations

Container supply-chain risks include:

- Malicious base images  
- Insecure Dockerfiles  
- Registry tampering  
- Unauthorized image pushes  
- Unscanned vulnerabilities  

Mitigations include:

- Minimal base images  
- Controlled build context  
- Private registry  
- Planned Trivy scanning  
- Pipeline validation logs  

---

## 🧠 Research Reflection

The Docker build stage proves that the architecture can support secure software delivery.

It connects application build activity to the infrastructure security model and prepares the environment for vulnerability scanning and policy enforcement.

---

## 🚀 Readiness Outcome

The secure Docker build process is ready for:

- Trivy scanning  
- Versioned image tagging  
- Policy-based build failure  
- Registry monitoring  
- DevSecOps compliance evidence  
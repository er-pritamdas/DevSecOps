# DevSecOps Journey: From Code to Production

## Overview

This repository documents a complete DevSecOps journey, following an application from the moment a developer writes code until it is securely deployed and monitored in production.

The objective of this project is not only to learn individual tools but to understand how security integrates into every stage of the DevOps lifecycle.

In many organizations, security is treated as a final checkpoint before deployment. This approach often results in vulnerabilities being discovered late in the development cycle, increasing both remediation effort and operational risk.

DevSecOps shifts security to the left by embedding security practices, controls, and automation throughout the software delivery pipeline.

This repository demonstrates how modern engineering teams build, test, secure, deploy, and monitor applications using DevSecOps principles.

---

## What is DevSecOps?

DevSecOps stands for:

- **Dev** → Development
- **Sec** → Security
- **Ops** → Operations

DevSecOps is a culture and engineering practice where security becomes a shared responsibility across the entire software development lifecycle.

Instead of performing security checks only before production deployment, security controls are continuously integrated into the pipeline.

---

## The Story We Will Follow

Imagine a developer writes a new feature for an application.

The journey of that code looks like this:

```text
Developer
    ↓
Source Control
    ↓
Build
    ↓
Dependency Validation
    ↓
Security Scanning
    ↓
Containerization
    ↓
Infrastructure Provisioning
    ↓
Cloud Deployment
    ↓
Kubernetes Deployment
    ↓
Runtime Security
    ↓
Monitoring & Observability
    ↓
Production
```


## DevSecOps Pipeline Stages Covered

### Stage 1 - Source Control Security

* Git Fundamentals
* Branch Protection
* Pull Requests
* Secret Scanning
* Secure Code Reviews

### Stage 2 - Build & Dependency Management

* Build Process
* Package Management
* Dependency Validation
* Software Composition Analysis (SCA)

### Stage 3 - Continuous Integration (CI)

* CI Pipelines
* Automated Testing
* Pipeline Security
* Artifact Management

### Stage 4 - Static Application Security Testing (SAST)

* Code Quality Analysis
* Vulnerability Detection
* Secure Coding Practices

### Stage 5 - Containerization

* Docker Fundamentals
* Image Creation
* Container Security
* Image Scanning

### Stage 6 - Infrastructure as Code (IaC)

* Terraform
* Infrastructure Automation
* IaC Security Validation

### Stage 7 - Cloud Security

* AWS Fundamentals
* Identity & Access Management (IAM)
* Network Security
* Encryption

### Stage 8 - Kubernetes Security

* Kubernetes Fundamentals
* RBAC
* Network Policies
* Admission Controls

### Stage 9 - Dynamic Security Testing (DAST)

* Runtime Security Testing
* Vulnerability Discovery
* Security Validation

### Stage 10 - Secrets Management

* Secret Storage
* Secret Rotation
* Secure Access Controls

### Stage 11 - Monitoring & Incident Detection

* Logging
* Metrics
* Observability
* Threat Detection

### Stage 12 - Production Security

* Runtime Protection
* Compliance
* Continuous Monitoring


## Tools Covered

### Source Control

* Git
* GitHub / GitLab

### CI/CD

* GitLab CI/CD
* Jenkins

### Security

* Gitleaks
* GitGuardian
* SonarQube
* Semgrep
* OWASP Dependency Check
* Snyk
* OWASP ZAP

### Containers

* Docker
* Trivy

### Infrastructure

* Terraform
* Checkov

### Cloud

* AWS

### Kubernetes

* Kubernetes
* Helm
* Falco
* Kyverno

### Monitoring

* Prometheus
* Grafana
* ELK Stack
* Splunk

### Secrets Management

* HashiCorp Vault

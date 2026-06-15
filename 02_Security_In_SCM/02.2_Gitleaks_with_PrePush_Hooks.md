# Table of Contents

- [Objective](#objective)
- [Why Pre-Push Hooks?](#why-pre-push-hooks)
- [What is a Pre-Push Hook?](#what-is-a-pre-push-hook)
- [Security Layers](#security-layers)
- [Pre-Push Workflow](#pre-push-workflow)
- [Native Git Hook Method](#native-git-hook-method)
- [Why Native Hooks Are Not Ideal](#why-native-hooks-are-not-ideal)
- [Enterprise Solution: pre-commit Framework](#enterprise-solution-pre-commit-framework)
- [Install pre-commit](#install-pre-commit)
- [Install Gitleaks](#install-gitleaks)
- [Create .pre-commit-config.yaml](#create-pre-commit-configyaml)
- [Install Pre-Push Hook](#install-pre-push-hook)
- [Testing the Hook](#testing-the-hook)
- [Running Gitleaks at Both Stages](#running-gitleaks-at-both-stages)
  - [During Commit](#during-commit)
  - [During Push](#during-push)
- [Why Run Both?](#why-run-both)
- [Enterprise Architecture](#enterprise-architecture)
- [Bypass Methods](#bypass-methods)
- [Why CI/CD Is Still Required](#why-cicd-is-still-required)
- [Pre-Push vs CI/CD](#pre-push-vs-cicd)
- [Common Interview Questions](#common-interview-questions)
- [Best Practice Recommendation](#best-practice-recommendation)
- [Key Takeaways](#key-takeaways)

---

## Objective

Learn how to automatically run Gitleaks before every Git push to prevent secrets from reaching remote repositories such as GitHub, GitLab, or Bitbucket.

---

# Why Pre-Push Hooks?

Even with Pre-Commit Hooks configured, credentials can occasionally leak because developers might:
* Bypass hooks using the `--no-verify` flag.
* Commit before hooks were installed in their local environment.
* Receive commits from other developers or branches.
* Introduce secrets through operations like rebases or cherry-picks.

Therefore, a second layer of defense is necessary. This is where **Pre-Push Hooks** become useful.

---

# What is a Pre-Push Hook?

A Pre-Push Hook is a local Git hook script that executes automatically when a developer runs:
```bash
git push
```
Before the data is transmitted to the remote server, Git pauses the push operation and executes the script. The hook then decides to:
* **Allow Push** (Exit code `0`)
* **Block Push** (Exit code non-zero)

---

# Security Layers

A mature DevSecOps workflow relies on multiple layers of protection rather than trusting a single control.

```text
Layer 1 ──> Pre-Commit Hook
Layer 2 ──> Pre-Push Hook
Layer 3 ──> CI/CD Secret Scan
Layer 4 ──> Branch Protection
Layer 5 ──> GitGuardian Monitoring
Layer 6 ──> Scheduled Historical Scans
```

This multi-tiered approach is known as **Defense in Depth**.

---

# Pre-Push Workflow

```text
Developer ──> git commit ──> Local Repository ──> git push
                                                    │
                                                    ▼
                                            [Pre-Push Hook Runs]
                                                    │
                                                    ▼
                                             [Gitleaks Scan]
                                                    │
                                            ┌───────┴───────┐
                                      Secrets Found?        │
                                            │               │
                                        Yes │            No │
                                            ▼               ▼
                                      [Push Blocked]  [Push Allowed]
```

---

# Native Git Hook Method

Native hooks are shell scripts stored in the `.git/hooks/` directory.

### 1. Create hook file:
```bash
nano .git/hooks/pre-push
```

### 2. Add the bash script:
```bash
#!/bin/bash

echo "Running Gitleaks..."

gitleaks detect

if [ $? -ne 0 ]; then
    echo "Secrets detected. Push blocked."
    exit 1
fi

echo "No secrets found."
exit 0
```
Save and close the file.

### 3. Make script executable:
```bash
chmod +x .git/hooks/pre-push
```

---

# Why Native Hooks Are Not Ideal

Native hooks have a significant drawback:
```text
The .git/hooks/ directory is not committed to the repository.
```
This means:
* **Developer A** has the hook active.
* **Developer B** clones the repository, and the hook is missing.

This creates inconsistent security enforcement across the development team.

---

# Enterprise Solution: pre-commit Framework

The **`pre-commit` framework** is the enterprise standard for managing hooks centrally.

### Benefits:
* **Version Controlled**: Configurations are checked into Git.
* **Shared Across Team**: Config is distributed to all workspaces.
* **Easy Installation**: Set up hooks with simple cli commands.
* **Consistent Security Controls**: Standardized enforcement.
* **Supports Many Security Tools**: Integrates Gitleaks alongside formatters and linters.

---

# Install pre-commit

### Ubuntu Installation Command:
```bash
pip install pre-commit
```

### Verify Installation:
```bash
pre-commit --version
```

---

# Install Gitleaks

### Ubuntu Installation Command:
```bash
curl -sSfL https://raw.githubusercontent.com/gitleaks/gitleaks/master/install.sh | sudo sh -s -- -b /usr/local/bin
```

### Verify Installation:
```bash
gitleaks version
```

---

# Create .pre-commit-config.yaml

Create or edit `.pre-commit-config.yaml` in the root of your repository.

### Example Configuration:
```yaml
repos:
  - repo: https://github.com/gitleaks/gitleaks
    rev: v8.24.2
    hooks:
      - id: gitleaks
        stages:
          - pre-push
```

---

# Install Pre-Push Hook

Deploy the hook configuration using the framework:
```bash
pre-commit install --hook-type pre-push
```

### Expected Output:
```text
pre-commit installed at .git/hooks/pre-push
```

---

# Testing the Hook

### 1. Add a dummy secret:
```env
AWS_SECRET_ACCESS_KEY=ABC123XYZ
```

### 2. Commit the change:
```bash
git add .
git commit -m "Testing"
```

### 3. Attempt to push to the remote branch:
```bash
git push origin main
```

### Expected Output:
```text
Gitleaks................................Failed
```
The push operation is blocked.

---

# Running Gitleaks at Both Stages

It is highly recommended to configure Gitleaks to run at both the `pre-commit` and `pre-push` stages.

### Recommended Configuration:
```yaml
repos:
  - repo: https://github.com/gitleaks/gitleaks
    rev: v8.24.2
    hooks:
      - id: gitleaks
        stages:
          - pre-commit
          - pre-push
```

### Install Both Hook Types:
```bash
pre-commit install
pre-commit install --hook-type pre-push
```

---

# What Happens?

## During Commit

```text
git commit ──> [Gitleaks Scan] ──> Commit Allowed or Blocked
```

---

## During Push

```text
git push ──> [Gitleaks Scan] ──> Push Allowed or Blocked
```

---

# Why Run Both?

## Pre-Commit

* **Purpose**: Fast Feedback
* **Benefits**:
  * Immediate feedback and detection.
  * Secrets never enter the local Git history.
  * Better developer workflow.

---

## Pre-Push

* **Purpose**: Safety Net
* **Benefits**:
  * Catch commits that bypassed the pre-commit hook.
  * Scan commits created before the hooks were installed.
  * Catch secrets introduced indirectly (e.g., cherry-pick).

---

# Enterprise Architecture

```text
Developer Laptop
  │
  ├── Pre-Commit Hook (Runs Gitleaks)
  │
  └── Pre-Push Hook (Runs Gitleaks)
        │
        ▼ (Pushed code)
GitHub
  │
  ├── Pull Request Scan (Runs Gitleaks)
  │
  ├── Branch Protection
  │
  └── GitGuardian Monitoring
```

---

# Bypass Methods

Developers can bypass local hooks using Git override flags:
```bash
git push --no-verify
```
This skips the Pre-Push hook execution entirely.

> [!IMPORTANT]
> **Warning:** Local hooks do not equal enforcement.

---

# Why CI/CD Is Still Required

Because local client-side hooks can be bypassed, remote CI/CD scanning is required as a final enforcement gate.

```text
Developer Laptop ──> Pre-Commit ──> Pre-Push 
                             │
                             ▼ (Can be bypassed with --no-verify)
                         GitHub ──> Gitleaks CI/CD Scan ──> Protected Branch
```

---

# Pre-Push vs CI/CD

| Feature | Pre-Push Hook | CI/CD Scan |
| :--- | :--- | :--- |
| **Runs Locally** | Yes | No |
| **Can Be Bypassed** | Yes | No |
| **Fast Feedback** | Yes | No |
| **Enforcement** | No | Yes |
| **Developer Friendly** | Yes | Moderate |
| **Enterprise Security** | Additional Layer | Required Layer |

---

# Common Interview Questions

### Why use Pre-Push Hooks?
To prevent secrets from reaching remote repositories.

### Why not rely only on Pre-Commit?
Developers can bypass pre-commit or commit secrets before hooks were installed.

### Can Pre-Push Hooks be bypassed?
Yes, by using the `--no-verify` flag during pushing:
```bash
git push --no-verify
```

### Why still use CI/CD?
CI/CD runs on centralized infrastructure and cannot be bypassed by developers.

### Why use the pre-commit framework instead of native hooks?
Because configurations are version-controlled, shared across the team, and easy to maintain.

---

# Best Practice Recommendation

For a mature DevSecOps environment, never trust a single security control. Implementing a layered model is the correct practice:

```text
Developer Laptop
 │
 ├── Gitleaks Pre-Commit
 └── Gitleaks Pre-Push
 
GitHub
 │
 ├── Gitleaks PR Scan
 └── Branch Protection
 
Security Team
 │
 ├── GitGuardian Monitoring
 └── Historical Scans
```

---

# Key Takeaways

* Pre-Push Hooks are the second line of defense.
* Gitleaks can automatically run before every push.
* Native hooks are local and not shared.
* The `pre-commit` framework is the preferred enterprise solution.
* Pre-Push Hooks can be bypassed using `--no-verify`.
* CI/CD remains the final enforcement layer.
* Use Defense in Depth: Pre-Commit + Pre-Push + CI/CD + Monitoring.
* Security should prevent secrets from reaching remote repositories whenever possible.

---

### Summary of Commands Used

| Command | Description |
| :--- | :--- |
| `git push` | Push local commits to a remote repository |
| `nano .git/hooks/pre-push` | Create or edit the native pre-push hook script |
| `chmod +x .git/hooks/pre-push` | Make the native pre-push hook script executable |
| `pip install pre-commit` | Install the pre-commit framework via python package manager |
| `pre-commit --version` | Verify the installed version of the pre-commit framework |
| `curl -sSfL https://raw.githubusercontent.com/gitleaks/gitleaks/master/install.sh \| sudo sh -s -- -b /usr/local/bin` | Install Gitleaks command line tool |
| `gitleaks version` | Display the installed version of Gitleaks |
| `pre-commit install --hook-type pre-push` | Install the hooks configured in `.pre-commit-config.yaml` as pre-push hooks |
| `git add .` | Stage all changes in the current directory |
| `git commit -m "Testing"` | Commit staged changes locally |
| `git push origin main` | Push commits to the remote main branch on origin |
| `pre-commit install` | Install the hooks configured in `.pre-commit-config.yaml` as pre-commit hooks |
| `git commit` | Commit staged changes locally |
| `git push --no-verify` | Push local commits bypassing all pre-push hooks |

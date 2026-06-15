# Table of Contents

- [Objective](#objective)
- [Why Pre-Commit Hooks?](#why-pre-commit-hooks)
- [Security Principle](#security-principle)
- [What is a Git Hook?](#what-is-a-git-hook)
- [Workflow](#workflow)
- [Method 1: Native Git Hook](#method-1-native-git-hook)
  - [Create Hook](#create-hook)
  - [Make Executable](#make-executable)
  - [Test](#test)
- [Limitation of Native Hooks](#limitation-of-native-hooks)
- [Enterprise Solution: pre-commit Framework](#enterprise-solution-pre-commit-framework)
- [Install pre-commit](#install-pre-commit)
- [Create Configuration File](#create-configuration-file)
- [Install Hook](#install-hook)
- [What Happens Internally?](#what-happens-internally)
- [Test the Hook](#test-the-hook)
- [Bypassing the Hook](#bypassing-the-hook)
- [Why CI/CD is Still Required](#why-cicd-is-still-required)
- [Recommended Enterprise Strategy](#recommended-enterprise-strategy)
- [Real DevSecOps Interview Questions](#real-devsecops-interview-questions)
- [Key Takeaways](#key-takeaways)

---

## Objective

Automatically run Gitleaks before every commit so that secrets are blocked before entering Git history.

---

# Why Pre-Commit Hooks?

Without a hook in place, secrets can easily enter your repository's commits.

```text
Developer ──> git commit ──> Secret Enters Git History
```

> [!WARNING]
> **Problem:** Even if the secret is removed later, it remains in the Git history.

---

# Security Principle

The best secret is:
```text
A secret that never gets committed.
```

Therefore, the **Pre-Commit Hook** is the first line of defense.

---

# What is a Git Hook?

Git hooks are scripts that Git automatically executes when specific Git events occur.

| Hook | Trigger |
| :--- | :--- |
| **`pre-commit`** | Runs before a commit is created |
| **`commit-msg`** | Runs before a commit message is accepted |
| **`pre-push`** | Runs before a push is executed |
| **`post-merge`** | Runs after a merge completes |

For secret scanning, we use the `pre-commit` hook.

---

# Workflow

```text
Developer ──> git commit ──> [Pre-Commit Hook Runs]
                                       │
                                       ▼
                                [Gitleaks Scan]
                                       │
                                ┌──────┴──────┐
                          Secrets Found?      │
                                │             │
                            Yes │          No │
                                ▼             ▼
                          [Blocked]       [Allowed]
```

---

# Method 1: Native Git Hook

You can configure a native bash script as a git hook directly in your `.git` folder.

## Create Hook

Run the following commands to create the hook file:
```bash
mkdir -p .git/hooks
nano .git/hooks/pre-commit
```

Add the following bash script to `.git/hooks/pre-commit`:
```bash
#!/bin/bash

echo "Running Gitleaks..."

gitleaks detect --no-git --source .

if [ $? -ne 0 ]; then
    echo "Secrets detected!"
    exit 1
fi

echo "No secrets found."
exit 0
```
Save and close the file.

---

## Make Executable

You must give the script execution permissions:
```bash
chmod +x .git/hooks/pre-commit
```

---

## Test

### 1. Create a dummy secret file:
```env
AWS_SECRET_ACCESS_KEY=abc123
```

### 2. Attempt to commit:
```bash
git commit -m "test"
```

### Expected Output:
```text
Running Gitleaks...
Secrets detected!
```
The commit is successfully blocked and fails.

---

# Limitation of Native Hooks

The `.git/hooks/` directory has a key limitation:
```text
.git/hooks/ is not committed to Git.
```

* **Developer A** configures and gets the hook locally.
* **Developer B** clones the repository and the hook is missing.

This results in inconsistent application of the security policy across the development team.

---

# Enterprise Solution: pre-commit Framework

Most organizations use the **`pre-commit` framework** instead of manually creating and managing native Git hooks.

### Benefits:
* **Version Controlled**: Hooks are configured in a shared config file.
* **Shared Across Team**: Easily distributed to all developers.
* **Easy Installation**: Simple setup commands.
* **Supports Multiple Security Tools**: Can run linters, formatters, and scanners alongside Gitleaks.

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

# Create Configuration File

Create a file named `.pre-commit-config.yaml` in the root of your repository.

### Example Configuration (`.pre-commit-config.yaml`):
```yaml
repos:
  - repo: https://github.com/gitleaks/gitleaks
    rev: v8.24.2
    hooks:
      - id: gitleaks
```

---

# Install Hook

Run the installation command to set up the hooks:
```bash
pre-commit install
```

### Expected Output:
```text
pre-commit installed at .git/hooks/pre-commit
```

---

# What Happens Internally?

When a developer runs a commit command:
```bash
git commit -m "feature"
```

The pre-commit framework automatically intercepts the request and runs the configured tools before completing the commit:
```bash
gitleaks
```

---

# Test the Hook

### 1. Create a dummy secret:
```env
AWS_SECRET_ACCESS_KEY=ABC123
```

### 2. Attempt to add and commit:
```bash
git add .
git commit -m "testing"
```

### Expected Output:
```text
Gitleaks................................Failed
```
The commit is successfully blocked.

---

# Bypassing the Hook

Git allows users to bypass hooks using the `--no-verify` flag.

```bash
git commit --no-verify
```
This skips the `pre-commit` framework execution entirely.

> [!IMPORTANT]
> **Warning:** Pre-commit hooks alone do not guarantee complete security.

---

# Why CI/CD is Still Required

Because local hooks can be bypassed, they must be paired with remote checks.

```text
Developer Laptop ──> Pre-Commit Hook (Can be bypassed with --no-verify)
        │
        ▼
     GitHub ──> CI/CD Gitleaks Scan (Remote enforcement)
```

A defense-in-depth approach with multiple scanning layers is required.

---

# Recommended Enterprise Strategy

* **Layer 1**: Gitleaks Pre-Commit Hook
* **Layer 2**: Gitleaks Pre-Push Hook
* **Layer 3**: Gitleaks GitHub Action (CI/CD)
* **Layer 4**: GitGuardian Monitoring
* **Layer 5**: Scheduled Historical Scans

---

# Real DevSecOps Interview Questions

### Why use pre-commit hooks?
To prevent secrets from entering Git history.

### Can developers bypass pre-commit hooks?
Yes, using:
```bash
git commit --no-verify
```

### Are pre-commit hooks sufficient?
No. CI/CD scanning and repository monitoring are also required.

### Why use the pre-commit framework instead of native hooks?
Because native hooks are not shared with the repository, while pre-commit configurations can be version-controlled and distributed to all developers.

---

# Key Takeaways

* Pre-Commit Hooks are the first line of defense.
* Gitleaks can automatically run before every commit.
* Native Git hooks are local only.
* The `pre-commit` framework is preferred in enterprises.
* Hooks can be bypassed using `--no-verify`.
* CI/CD scanning must always be present as an additional control.
* Defense in depth is the correct DevSecOps approach.

---

### Summary of Commands Used

| Command | Description |
| :--- | :--- |
| `mkdir -p .git/hooks` | Create the local git hooks directory |
| `nano .git/hooks/pre-commit` | Create or edit the native pre-commit hook script |
| `chmod +x .git/hooks/pre-commit` | Make the native git hook script executable |
| `pip install pre-commit` | Install the pre-commit framework via python package manager |
| `pre-commit --version` | Verify the installed version of the pre-commit framework |
| `pre-commit install` | Install the hooks configured in `.pre-commit-config.yaml` to `.git/` |
| `git add .` | Stage all files in the current workspace |
| `git commit -m "message"` | Commit staged changes locally |
| `git commit --no-verify` | Commit changes bypassing all pre-commit hooks |

# Table of Contents

- [Objective](#objective)
- [What is Gitleaks?](#what-is-gitleaks)
- [Where Gitleaks Fits](#where-gitleaks-fits)
- [Installation](#installation)
- [Detection Techniques](#detection-techniques)
  - [Keywords](#keywords)
  - [Regex](#regex)
  - [Entropy](#entropy)
  - [Context](#context)
  - [File Patterns](#file-patterns)
- [Important Commands](#important-commands)
- [Understanding Results](#understanding-results)
- [Exit Codes](#exit-codes)
- [CI/CD Integration](#cicd-integration)
- [Pre-Commit Hook Usage](#pre-commit-hook-usage)
- [Baseline](#baseline)
- [Allowlists](#allowlists)
- [Limitations](#limitations)
- [Enterprise Strategy](#enterprise-strategy)
- [Interview Questions](#interview-questions)
- [Key Takeaways](#key-takeaways)

---

## Objective

Learn how Gitleaks detects secrets in files and Git history and how it is integrated into DevSecOps pipelines.

---

# What is Gitleaks?

Gitleaks is an open-source secret detection tool.

```text
Detect Secrets (NOT Manage Secrets)
```

### Examples of Secrets Detected:
* AWS Keys
* GitHub Tokens
* Database Passwords
* API Keys
* Private Keys
* OAuth Secrets

---

# Where Gitleaks Fits

Gitleaks can be positioned at various points in the software development lifecycle to prevent secrets from reaching production.

```text
Developer 
    ↓
[Pre-Commit Scan] 
    ↓
Git Commit 
    ↓
[Pre-Push Scan] 
    ↓
GitHub 
    ↓
[Pull Request Scan] 
    ↓
Merge
```

---

# Installation

### Ubuntu Installation Command:
```bash
curl -sSfL https://raw.githubusercontent.com/gitleaks/gitleaks/master/install.sh | sudo sh -s -- -b /usr/local/bin
```

### Verify Installation:
```bash
gitleaks version
```

---

# Detection Techniques

Gitleaks uses several methods to accurately find secrets while minimizing false positives.

## Keywords

Looks for specific terms that commonly precede credentials.

### Examples:
* `password`
* `token`
* `apikey`
* `secret`
* `access_key`

---

## Regex

Matches patterns of known credential formats.

### Example: AWS Access Key Pattern
```regex
AKIA[0-9A-Z]{16}
```

---

## Entropy

Detects highly random strings that are likely to be auto-generated API keys or passwords.

### Example: High-Entropy String
```text
A8k3#Lm9Qw2!Zx7P
```

---

## Context

Analyzes the surrounding structure to confirm if a string is a secret.

### Example: Suspicious context
```python
DB_PASSWORD="secret"
```

This context is much more suspicious than a generic assignment:
```python
message="secret"
```

---

## File Patterns

Scans for specific filenames that are known to contain credentials.

### Examples:
* `.env`
* `credentials.json`
* `terraform.tfvars`
* `id_rsa`

---

# Important Commands

Commands to run Gitleaks in different scenarios.

## Scan Git History
```bash
gitleaks detect
```

## Scan Current Files
```bash
gitleaks detect --no-git --source .
```

## Verbose Mode
```bash
gitleaks detect -v
```

## Save Report
```bash
gitleaks detect --report-path report.json
```

## Redact Secrets
```bash
gitleaks detect --redact
```

## Scan Specific Directory
```bash
gitleaks detect --no-git --source ./app
```

## Scan Specific File
```bash
gitleaks detect --no-git --source secrets.env
```

## Scan Last 20 Commits
```bash
gitleaks detect --log-opts="-n 20"
```

## Scan Commit Range
```bash
gitleaks detect --log-opts="main..feature-branch"
```

---

# Understanding Results

When Gitleaks detects a secret, it reports details with the following typical fields:

| Field | Meaning |
| :--- | :--- |
| **RuleID** | The detection rule that was triggered |
| **File** | The name of the file containing the secret |
| **Commit** | The commit hash where the secret was found |
| **Author** | The author of the commit |
| **StartLine** | The starting line number of the secret |
| **EndLine** | The ending line number of the secret |

---

# Exit Codes

Gitleaks uses exit codes to report status, which makes it ideal for automated scripts.

* **Exit Code `0`**: No secrets were found.
* **Exit Code `1`**: Secrets were found.

> [!NOTE]
> **Pipeline Behavior:** Exit code `1` is used to fail CI/CD build pipelines if secrets are detected.

---

# CI/CD Integration

You can integrate Gitleaks as a step in your CI/CD configuration file.

### Example GitHub Actions Step:
```yaml
- name: Run Gitleaks
  run: gitleaks detect
```

If the exit code is `1`, the pipeline will fail, stopping deployment.

---

# Pre-Commit Hook Usage

A pre-commit hook runs Gitleaks before a commit is created to prevent leaks locally.

```text
Developer
    ↓
git commit
    ↓
[Gitleaks Hook]
    ↓
Secret Found?
  ├── Yes ──> Commit Blocked
  └── No  ──> Commit Allowed
```

---

# Baseline

Baselines are useful when integrating Gitleaks into an existing repository with historical secrets that cannot be easily removed immediately.

### 1. Generate Baseline Report:
```bash
gitleaks detect --report-path baseline.json
```

### 2. Scan Using Baseline:
```bash
gitleaks detect --baseline-path baseline.json
```
Using the baseline report will ensure only new leaks are reported.

---

# Allowlists

Allowlists let you configure Gitleaks to ignore known false positives.

### Example config (`gitleaks.toml`):
```toml
[allowlist]
paths = [
  '''docs/.*'''
]
```

> [!WARNING]
> **Warning:** Use allowlists carefully. Never allowlist real, active secrets.

---

# Limitations

It is important to understand the boundary of what Gitleaks can do.

### Gitleaks Can:
* Detect exposed secrets
* Report locations and hashes
* Block commits via Git Hooks

### Gitleaks Cannot:
* Rotate secrets
* Revoke secrets
* Store secrets
* Manage secrets

---

# Enterprise Strategy

An effective enterprise deployment secures multiple lifecycle layers:

* **Layer 1**: Pre-Commit Hook
* **Layer 2**: Pre-Push Hook
* **Layer 3**: Pull Request Scan
* **Layer 4**: Main Branch Scan
* **Layer 5**: Continuous Repository Monitoring

---

# Interview Questions

### What is Gitleaks?
An open-source secret detection tool that scans files and Git history for exposed credentials.

### Does Gitleaks manage secrets?
No, it only detects them.

### Why use Gitleaks in CI/CD?
To block secrets from reaching protected branches.

### What is a baseline?
A mechanism used to ignore previously known findings and focus on new leaks.

---

# Key Takeaways

* Gitleaks is a Secret Detection tool.
* It scans both workspace files and Git history.
* It uses keywords, regex patterns, entropy thresholds, and context.
* It integrates with Git hooks and CI/CD pipelines.
* It supports baselines and configuration allowlists.
* It cannot manage or rotate secrets.

---

### Summary of Commands Used

| Command | Description |
| :--- | :--- |
| `curl -sSfL https://raw.githubusercontent.com/gitleaks/gitleaks/master/install.sh \| sudo sh -s -- -b /usr/local/bin` | Download and install Gitleaks on Ubuntu/Linux |
| `gitleaks version` | Display the installed version of Gitleaks |
| `gitleaks detect` | Scan the entire local Git repository's commit history for secrets |
| `gitleaks detect --no-git --source .` | Scan current files in the workspace directory without checking Git history |
| `gitleaks detect -v` | Run secret detection with verbose output |
| `gitleaks detect --report-path report.json` | Scan history and save the findings to a JSON report file |
| `gitleaks detect --redact` | Redact sensitive values from the detection logs and output |
| `gitleaks detect --no-git --source ./app` | Scan files in the `./app` directory without checking Git history |
| `gitleaks detect --no-git --source secrets.env` | Scan a specific file (`secrets.env`) without checking Git history |
| `gitleaks detect --log-opts="-n 20"` | Scan only the last 20 commits in the Git history |
| `gitleaks detect --log-opts="main..feature-branch"` | Scan commit history within the specified branch range |
| `gitleaks detect --baseline-path baseline.json` | Scan repository ignoring any historic findings listed in the baseline report |

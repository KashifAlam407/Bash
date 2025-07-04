# 🧪 ShellCheck + GitHub Actions (CI for Bash)

`ShellCheck` is a **static analysis tool** for shell scripts. It warns you about syntax errors, bad practices, and potential bugs.

This guide shows how to:
- Use `shellcheck` locally
- Automate it with GitHub Actions
- Enforce quality checks in pull requests

---

## 🛠️ What is ShellCheck?

**ShellCheck** analyzes Bash scripts and reports:
- Quoting issues
- Deprecated syntax
- Unset variables
- Unsafe redirects
- Logical errors

---

## 🔧 1. Installing ShellCheck

### ✅ Ubuntu / Debian
```bash
sudo apt install shellcheck
```

### ✅ macOS (Homebrew)
```bash
brew install shellcheck
```

### ✅ Manual (Portable)
Download from: [https://github.com/koalaman/shellcheck/releases](https://github.com/koalaman/shellcheck/releases)

---

## 🧪 2. Using ShellCheck Locally

Run it on a script:
```bash
shellcheck script.sh
```

To check all scripts in your repo:
```bash
find . -name "*.sh" -exec shellcheck {} \;
```

---

## 🚀 3. GitHub Actions: `shellcheck.yml`

### ➕ Add Workflow File

Create `.github/workflows/shellcheck.yml`:

```yaml
name: ShellCheck Linter

on:
  push:
    paths:
      - '**.sh'
  pull_request:
    paths:
      - '**.sh'

jobs:
  lint:
    runs-on: ubuntu-latest

    steps:
    - name: Checkout repository
      uses: actions/checkout@v3

    - name: Install ShellCheck
      run: sudo apt-get install -y shellcheck

    - name: Run ShellCheck
      run: |
        find . -name "*.sh" | xargs shellcheck
```

### ✅ Features:
- Lints all `.sh` files on push/PR
- Fails if any warnings are detected

---

## 🧠 Example Output

```text
In script.sh line 4:
for f in $(ls *.txt); do
         ^-- SC2045: Iterating over ls output is fragile. Use globs.
```

---

## 🧹 Best Practices

| Practice | Why |
|----------|-----|
| Fix all `shellcheck` warnings | Improve reliability |
| Run on every PR | Maintain quality |
| Use consistent quoting | Prevent bugs |
| Enable `set -euo pipefail` in scripts | Add extra safety |

---

## 📚 References

- [ShellCheck homepage](https://www.shellcheck.net/)
- [ShellCheck GitHub](https://github.com/koalaman/shellcheck)
- [Awesome ShellCheck Tips](https://github.com/koalaman/shellcheck/wiki/SC2086)

---

> 📁 File: `advance/shellcheck-ci.md`  
> Author: [Kashif Alam](https://github.com/KashifAlam407)

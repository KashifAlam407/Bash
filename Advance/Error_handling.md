# ❗ Error Handling in Bash

Robust error handling ensures your Bash scripts behave predictably when something goes wrong. This is especially important in automation, backups, and server management scripts.

---

## 📌 Why Error Handling Matters

Without error handling:
- Scripts can silently fail
- Important tasks may be skipped
- Partial or corrupted data may result

---

## 🛑 Exit Codes (`$?`)

Every Bash command returns an **exit code**:
- `0` = success
- non-zero = failure

```bash
ls /nonexistent
echo $?   # 2 → Error
```

Use exit codes in conditions:

```bash
if [ $? -ne 0 ]; then
  echo "Command failed"
fi
```

---

## ⚙️ `set` Options for Strict Error Checking

### `set -e`
- Exit script immediately if any command fails.

```bash
set -e
cp file.txt /protected/path/    # If fails, script stops
```

### `set -u`
- Treat unset variables as an error.

```bash
set -u
echo $username   # Error if 'username' not set
```

### `set -o pipefail`
- Fail entire pipeline if any command fails.

```bash
set -o pipefail
grep "something" file.txt | sort | head
```

> Without `pipefail`, only the last command’s exit code is checked.

---

## 🧲 `trap` – Catch and Handle Errors or Signals

You can trap signals like `EXIT`, `ERR`, `INT`:

```bash
trap 'echo "An error occurred."' ERR
```

### Cleanup Example:
```bash
#!/bin/bash
set -e

cleanup() {
  echo "Cleaning up temporary files..."
  rm -f /tmp/tempfile
}
trap cleanup EXIT

touch /tmp/tempfile
cp /nonexistent /tmp/tempfile   # Will trigger trap
```

---

## 📋 Check Command Before Use

Use `command -v` to verify a tool exists before using it:

```bash
if ! command -v rsync &> /dev/null; then
  echo "rsync not found. Please install it." >&2
  exit 1
fi
```

---

## 🔁 Wrapping Commands with `||`

Use `||` to run fallback logic:

```bash
mkdir /protected/dir || { echo "Failed to create dir"; exit 1; }
```

---

## ✅ Best Practices

| Tip | Reason |
|-----|--------|
| Use `set -euo pipefail` | Makes script safer |
| Use `trap` | Ensure cleanup |
| Check exit codes | Prevent silent failures |
| Redirect stderr | `command 2>error.log` |
| Quote your variables | Avoid word splitting |

---

## 🧪 Example Script

```bash
#!/bin/bash
set -euo pipefail
trap 'echo "Something went wrong"; exit 1' ERR

backup_file="/tmp/backup.tar.gz"

echo "Starting backup..."
tar -czf "$backup_file" /important/data
echo "Backup completed at $backup_file"
```

---

## 📚 Related Topics

- [Debugging with `set -x`](./debug-trap.md)
- [Using `trap`](https://linuxize.com/post/bash-trap-command/)
- [ShellCheck](https://www.shellcheck.net/) for linting scripts

---

> 📁 File: `advance/error-handling.md`  
> Author: [Kashif Alam](https://github.com/KashifAlam407)


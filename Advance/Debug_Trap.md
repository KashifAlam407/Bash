# 🐞 Bash Debugging & `trap` Command

Debugging is crucial when your script isn't behaving as expected. Bash provides built-in tools like `set -x`, `trap`, and line tracing to help identify bugs.

---

## 🛠️ Enable Debugging with `set`

### `set -x`
Print each command and its arguments as they execute.

```bash
#!/bin/bash
set -x

name="Kashif"
echo "Hello, $name"
```

Output:
```bash
+ name=Kashif
+ echo 'Hello, Kashif'
Hello, Kashif
```

### `set +x`
Turn off debugging.

```bash
set -x
echo "Debugging"
set +x
echo "No debug"
```

---

## ⚙️ `trap` – Capture Script Events

### Syntax:
```bash
trap 'commands' SIGNAL
```

**Common Signals:**

| Signal | Meaning        |
|--------|----------------|
| `EXIT` | When script exits |
| `ERR`  | On any error (use with `set -e`) |
| `INT`  | Ctrl+C interrupt |
| `DEBUG`| Before every command |

---

### 🧹 Cleanup Example (trap EXIT)
```bash
#!/bin/bash
trap 'rm -f /tmp/tempfile' EXIT

touch /tmp/tempfile
echo "Working..."
sleep 3
exit 0
```

Even if the script fails or is killed, `/tmp/tempfile` will be removed.

---

### 🧨 Catching Errors (trap ERR)
```bash
#!/bin/bash
set -e
trap 'echo "❌ Error on line $LINENO"; exit 1' ERR

cp file.txt /nonexistent/dir
```

Output:
```bash
❌ Error on line 5
```

---

### 🔎 Line-by-Line Trace (trap DEBUG)
```bash
#!/bin/bash
trap 'echo "Running line: $BASH_COMMAND"' DEBUG

echo "Line 1"
ls /invalid/path
echo "Line 3"
```

> Useful for deep debugging.

---

## 🧰 Combine All: Debugging Template

```bash
#!/bin/bash
set -euo pipefail
trap 'echo "Error on line $LINENO: $BASH_COMMAND"; exit 1' ERR
trap 'echo "Finished script"; exit 0' EXIT
trap 'echo "Interrupted by user"' INT

echo "Starting work..."
# Simulated error
cp file.txt /root/
```

---

## 📌 Best Practices

| Practice | Benefit |
|----------|---------|
| Use `set -euo pipefail` | Safer scripts |
| Trap `ERR` and `EXIT`   | Cleanup and error logs |
| Debug with `set -x`     | Trace issues easily |
| Use logging functions   | Record errors in a log file |

---

## 📚 More Resources

- [`trap` command explained](https://linuxize.com/post/bash-trap-command/)
- [`set` command options](https://www.gnu.org/software/bash/manual/html_node/The-Set-Builtin.html)
- [Bash Debugging Guide](https://tldp.org/LDP/Bash-Beginners-Guide/html/sect_02_03.html)

---

> 📁 File: `advance/debug-trap.md`  
> Author: [Kashif Alam](https://github.com/KashifAlam407)

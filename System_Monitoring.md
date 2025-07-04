# ⚙️ ps – Display Process Status

**Syntax:**
```bash
ps [OPTIONS]
```

**Options:**

| Option | Description |
|--------|-------------|
| `-e`   | Show all processes |
| `-f`   | Full-format listing |
| `-u`   | User-oriented format |
| `-aux` | Show all processes with user info (BSD style) |

**Examples:**
```bash
ps
ps -e
ps -ef
ps aux
ps -u username
```

---

# 📊 top – Real-Time Process Monitoring

**Syntax:**
```bash
top [OPTIONS]
```

**Key Info:**
- Displays CPU, memory usage, process stats.
- Press `q` to quit.
- Press `k` to kill a process (enter PID).
- Press `M` to sort by memory, `P` for CPU.

**Examples:**
```bash
top
top -u username
```

---

# 💽 df – Disk Space Usage

**Syntax:**
```bash
df [OPTIONS]
```

**Options:**

| Option | Description |
|--------|-------------|
| `-h`   | Human-readable sizes (KB/MB/GB) |
| `-T`   | Show filesystem type |
| `-a`   | Include dummy filesystems |

**Examples:**
```bash
df
df -h
df -Th
```

---

# 📦 du – Disk Usage of Files and Directories

**Syntax:**
```bash
du [OPTIONS] [DIRECTORY]
```

**Options:**

| Option | Description |
|--------|-------------|
| `-h`   | Human-readable |
| `-s`   | Summary only |
| `-a`   | Show all files |
| `-c`   | Show total size |

**Examples:**
```bash
du -h /home/user/
du -sh /var/log
du -ah . | sort -rh | head -10
```

---

# 🧠 free – Show Memory and Swap Usage

**Syntax:**
```bash
free [OPTIONS]
```

**Options:**

| Option | Description |
|--------|-------------|
| `-h`   | Human-readable format |
| `-m`   | Show in MB |
| `-g`   | Show in GB |
| `-t`   | Display total summary |

**Examples:**
```bash
free
free -h
free -m
```

---

# ☠️ kill – Terminate Processes by PID

**Syntax:**
```bash
kill [OPTIONS] PID
```

**Options:**

| Option | Description |
|--------|-------------|
| `-9`   | Force kill (SIGKILL) |
| `-15`  | Graceful stop (SIGTERM - default) |
| `-l`   | List all signal names |

**Examples:**
```bash
kill 1234
kill -9 4567
kill -15 8901
```

> Use `ps`, `top`, or `pidof` to find PIDs.

---

# ⏱️ uptime – Show System Uptime

**Syntax:**
```bash
uptime
```

**Description:**
Displays how long the system has been running, number of users, and load average.

**Example:**
```bash
uptime
# Output: 04:28:15 up 1 day,  3:12,  2 users,  load average: 0.45, 0.31, 0.28
```

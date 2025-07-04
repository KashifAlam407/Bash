# 🐚 Bash Language Mastery

This repository is a **complete learning resource for Bash scripting** — from beginner-friendly commands to advanced automation and CI/CD techniques.

Every topic is structured into a dedicated markdown file, including command examples, flags, real use cases, and best practices.

---

## 📂 Topics Covered

### 🔰 1. [Bash Commands](Bash_command.md)
> Learn foundational Bash commands such as:
- `ls`, `cd`, `pwd`, `echo`, `cat`, `cp`, `mv`, `rm`
- File and directory handling
- Manual pages and `alias`

---

### 📄 2. [Text Processing](Text_Processing.md)
> Learn to manipulate text streams using:
- `grep`, `awk`, `sed`, `cut`, `sort`, `head`, `tail`
- Field extraction, search patterns, and formatting

---

### 📊 3. [System Monitoring](System_Monitoring.md)
> Monitor your system using:
- `ps`, `top`, `df`, `du`, `free`, `kill`, `uptime`
- Process and memory tracking, disk usage

---

### 🌐 4. [Networking](Networking.md)
> Bash for networking tasks:
- `ping`, `curl`, `wget`, `ssh`, `scp`, `rsync`
- Download, transfer, and remote connections

---

### 📦 5. [File Compression](File_Compression.md)
> Work with archives and compression:
- `zip`, `unzip`, `tar`

---

### 🔐 6. [File Permissions](File_Permission.md)
> Secure and manage file access:
- `chmod`, `chown`, `chgrp`

---

### 📜 7. [Scripting](Scripting.md)
> Write and manage shell scripts:
- Syntax, variables, data types
- Operators, conditionals, loops, functions, arrays
- Task scheduling with `cron`

---

## 🧠 Advanced Bash (Located in `advance/`)

| Topic | Description |
|-------|-------------|
| [`error-handling.md`](Advance/Error_Handling.md) | Error trapping, exit codes, `set -euo pipefail` |
| [`debug-trap.md`](Advance/Debug_Trap.md) | Debugging with `trap`, `set -x`, `DEBUG` tracing |
| [`regex-patterns.md`](Advance/Regex_Patterns.md) | Use regex in Bash with `[[ =~ ]]`, `grep`, `awk` |
| [`io-redirection.md`](Advance/IO_redirection.md) | Input/output, pipes, file descriptors |
| [`concurrency.md`](Advance/Concurrency.md) | Background jobs, `xargs -P`, parallel execution |
| [`libraries-getopts.md`](Advance/Libraries_getopts.md) | Modular code, function libraries, `getopts` CLI parser |
| [`shellcheck-ci.md`](Advance/Shellcheck.md) | Lint Bash with `shellcheck`, use CI with GitHub Actions |

---

## 🚀 How to Use This Repo

1. **Clone it:**
   ```bash
   git clone https://github.com/KashifAlam407/Bash
   cd Bash
   ```

2. **Browse by topic:**
   - Open any `.md` file to read concepts and run examples.
   - Scripts are written to run directly in any Bash environment.

3. **Use as a reference:**
   - Perfect for beginners, sysadmins, DevOps engineers, or anyone automating tasks with Bash.

---

## ✍️ Contributing

You are welcome to:
- Open issues or suggestions
- Submit pull requests with improvements
- Help expand sections with more examples

---

## 📜 License

This project is licensed under the [MIT License](LICENSE).

> Made with ❤️ by [Kashif Alam](https://github.com/KashifAlam407)

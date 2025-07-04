# 🔍 grep – Search Text Using Patterns

**Syntax:**
```bash
grep [OPTIONS] PATTERN [FILE...]
```

**Options:**

| Option | Description |
|--------|-------------|
| `-i`   | Ignore case |
| `-v`   | Invert match |
| `-r`   | Recursive search |
| `-n`   | Show line numbers |
| `-l`   | List matching file names only |
| `-c`   | Count matching lines |

**Examples:**
```bash
grep "error" logfile.txt
grep -i "hello" file.txt
grep -rn "TODO" ./src
grep -v "DEBUG" app.log
```

---

# 🧠 awk – Pattern Scanning and Processing Language

**Syntax:**
```bash
awk 'pattern {action}' [FILE...]
```

**Options (within scripts):**

| Option | Description |
|--------|-------------|
| `$1`, `$2`, ... | Columns/fields |
| `NF`   | Number of fields in a line |
| `NR`   | Current record number |
| `BEGIN` | Run before processing |
| `END`   | Run after all lines |

**Examples:**
```bash
awk '{print $1}' file.txt             # Print first column
awk '/error/ {print $0}' log.txt      # Print lines containing "error"
awk 'BEGIN{print "Start"}'            # Just print "Start"
awk '{sum += $2} END {print sum}' data.txt
```

---
# 🧰 sed – Stream Editor

**Syntax:**
```bash
sed [OPTIONS] 'command' [FILE...]
```

**Common Commands:**

| Command | Description |
|---------|-------------|
| `s/pattern/replace/` | Replace text |
| `d`     | Delete lines |
| `p`     | Print lines |
| `-n`    | Suppress default output |

**Examples:**
```bash
sed 's/apple/orange/' file.txt
sed 's/foo/bar/g' file.txt
sed -n '/hello/p' file.txt     # Print only lines containing "hello"
sed '2d' file.txt              # Delete 2nd line
```

---

# ✂️ cut – Remove Sections from Lines

**Syntax:**
```bash
cut [OPTIONS] [FILE...]
```

**Options:**

| Option | Description |
|--------|-------------|
| `-f`   | Specify field number |
| `-d`   | Set delimiter (default: tab) |
| `-c`   | Cut by character position |

**Examples:**
```bash
cut -f1 file.txt                     # First tab-separated field
cut -d',' -f2 file.csv               # Second column using comma
cut -c1-5 filename.txt               # First 5 characters of each line
```

---

# 🔃 sort – Sort Lines of Text Files

**Syntax:**
```bash
sort [OPTIONS] [FILE...]
```

**Options:**

| Option | Description |
|--------|-------------|
| `-r`   | Reverse sort |
| `-n`   | Sort numerically |
| `-k`   | Sort by specific field |
| `-u`   | Remove duplicates |

**Examples:**
```bash
sort file.txt
sort -r file.txt
sort -n numbers.txt
sort -k2 file.csv
sort -u names.txt
```

---

# 📉 tail – View End of File

**Syntax:**
```bash
tail [OPTIONS] [FILE...]
```

**Options:**

| Option | Description |
|--------|-------------|
| `-n`   | Number of lines to show |
| `-f`   | Follow file (real-time updates) |

**Examples:**
```bash
tail file.txt
tail -n 20 error.log
tail -f /var/log/syslog
```

---

# 📈 head – View Start of File

**Syntax:**
```bash
head [OPTIONS] [FILE...]
```

**Options:**

| Option | Description |
|--------|-------------|
| `-n`   | Number of lines to show |

**Examples:**
```bash
head file.txt
head -n 15 logfile.log
```
---

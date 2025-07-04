# 📂 ls – List Directory Contents

**Syntax:**
```bash
ls [OPTIONS] [FILES...]
```

**Options:**

| Option | Description |
|--------|-------------|
| `-l`   | Long listing format |
| `-a`   | Show hidden files |
| `-h`   | Human-readable file sizes |
| `-R`   | Recursively list directories |
| `-t`   | Sort by modification time |
| `-r`   | Reverse sort order |

**Examples:**
```bash
ls
ls -l
ls -la
ls -lh
ls -ltr
```
---
# 📁 cd – Change Directory

**Syntax:**
```bash
cd [directory]
```

**Examples:**
```bash
cd            # Home directory
cd /etc       # Go to /etc
cd ..         # One level up
cd -          # Switch to previous dir
```
---
# 📍 pwd – Print Working Directory

**Syntax:**
```bash
pwd
```

**Description:**
Prints the full path of the current directory.

**Example:**
```bash
pwd
# Output: /home/user/Desktop
```
---
# 🗨️ echo – Display Messages

**Syntax:**
```bash
echo [OPTIONS] [STRING...]
```

**Options:**

| Option | Description |
|--------|-------------|
| `-n`   | Do not print newline |
| `-e`   | Enable backslash escapes |
| `-E`   | Disable escape interpretation (default) |

**Examples:**
```bash
echo "Hello"
echo -n "Same line"
echo -e "Line1\nLine2\tTabbed"
```
---
# 📄 cat – Concatenate and View Files

**Syntax:**
```bash
cat [OPTIONS] [FILES...]
```

**Options:**

| Option | Description |
|--------|-------------|
| `-n`   | Number all lines |
| `-b`   | Number only non-blank lines |
| `-E`   | Show `$` at end |
| `-T`   | Show tabs as ^I |

**Examples:**
```bash
cat file.txt
cat -n file.txt
cat file1.txt file2.txt > combined.txt
```
---
# 📋 cp – Copy Files and Directories

**Syntax:**
```bash
cp [OPTIONS] SOURCE DEST
```

**Options:**

| Option | Description |
|--------|-------------|
| `-r`   | Copy directories recursively |
| `-u`   | Only copy if newer |
| `-i`   | Prompt before overwrite |
| `-v`   | Verbose output |

**Examples:**
```bash
cp file.txt backup.txt
cp -r dir1/ dir2/
cp -uv config.sh /etc/
```
---
# 🚚 mv – Move or Rename Files

**Syntax:**
```bash
mv [OPTIONS] SOURCE DEST
```

**Options:**

| Option | Description |
|--------|-------------|
| `-i`   | Prompt before overwrite |
| `-u`   | Move only if newer |
| `-v`   | Verbose output |

**Examples:**
```bash
mv old.txt new.txt
mv file.txt ~/Downloads/
mv -iv script.sh /usr/local/bin/
```
---
# ❌ rm – Remove Files or Directories

**Syntax:**
```bash
rm [OPTIONS] FILE...
```

**Options:**

| Option | Description |
|--------|-------------|
| `-r`   | Recursively delete dirs |
| `-f`   | Force delete (no prompt) |
| `-i`   | Ask before delete |
| `-v`   | Show deleted files |

**Examples:**
```bash
rm file.txt
rm -rf /tmp/test/
rm -iv backup.zip
```

> ⚠️ `rm -rf` can delete everything — use with extreme caution!
---
# 🕒 touch – Create or Update File Timestamp

**Syntax:**
```bash
touch [OPTIONS] FILE...
```

**Options:**

| Option | Description |
|--------|-------------|
| `-c`   | Don't create if missing |
| `-a`   | Change access time |
| `-m`   | Change modification time |
| `-t`   | Use custom time: `[[CC]YY]MMDDhhmm[.ss]` |

**Examples:**
```bash
touch newfile.txt
touch -c file.txt
touch -t 202507041200.00 data.log
```
---
# 📦 mkdir – Create Directories

**Syntax:**
```bash
mkdir [OPTIONS] DIRECTORY...
```

**Options:**

| Option | Description |
|--------|-------------|
| `-p`   | Create parent directories |
| `-v`   | Show created directories |

**Examples:**
```bash
mkdir mydir
mkdir -p parent/child/grandchild
mkdir -vp logs/errors/
```
---
# 📘 man – Manual Page Viewer

**Syntax:**
```bash
man [COMMAND]
```

**Description:**  
Shows the manual page for a command.

**Examples:**
```bash
man ls
man bash
```

> Press `q` to exit.
---
# 🧩 alias – Create Command Shortcuts

**Syntax:**
```bash
alias name='command'
```

**Examples:**
```bash
alias ll='ls -l'
alias gs='git status'
alias rm='rm -i'
alias update='sudo apt update && sudo apt upgrade'
```

**Remove alias:**
```bash
unalias ll
```

💡 To make the alias permanent across terminal sessions, add it to your `~/.bashrc` file:

```bash
echo "alias ll='ls -l'" >> ~/.bashrc
source ~/.bashrc  # Apply changes immediately
```
---

# 🔐 chmod – Modify File Permissions

**Syntax:**
```bash
chmod [OPTIONS] MODE FILE
```

**Permission Values:**

| Symbolic | Numeric | Meaning          |
|----------|---------|------------------|
| `r`      | 4       | Read             |
| `w`      | 2       | Write            |
| `x`      | 1       | Execute          |

**Common Usage:**

| Mode | Description             |
|------|-------------------------|
| `755`| rwxr-xr-x (owner all, others read/exec) |
| `644`| rw-r--r-- (owner read/write) |
| `700`| rwx------ (private)     |

**Examples:**
```bash
chmod 755 script.sh
chmod +x file.sh            # Add execute permission
chmod -x file.sh            # Remove execute
chmod u+x file.sh           # Add exec to owner
chmod g-w file.txt          # Remove write from group
```

--

# 👤 chown – Change File Owner

**Syntax:**
```bash
chown [OPTIONS] OWNER[:GROUP] FILE
```

**Options:**

| Option | Description |
|--------|-------------|
| `-R`   | Recursive |
| `-v`   | Verbose output |

**Examples:**
```bash
chown user file.txt
chown user:group file.txt
chown -R newuser /home/newuser/
```

> You must be root or use `sudo` to change ownership.

---

# 👥 chgrp – Change Group Ownership

**Syntax:**
```bash
chgrp [OPTIONS] GROUP FILE
```

**Options:**

| Option | Description |
|--------|-------------|
| `-R`   | Apply recursively |
| `-v`   | Verbose mode |

**Examples:**
```bash
chgrp developers script.sh
chgrp -R teamgroup /var/www/
```

> Useful when multiple users share a group for project files.

---

# 🔑 Understanding File Ownership in Linux

Each file or directory in Linux has:

- **Owner**: The user who owns the file.
- **Group**: The group associated with the file.
- **Others**: Everyone else.

**View Ownership:**
```bash
ls -l
```

Example output:
```bash
-rw-r--r-- 1 alice developers 1024 Jul 3 file.txt
```

- `alice` is the **owner**
- `developers` is the **group**

**Change Ownership:**
```bash
chown newuser file.txt
```

**Change Group:**
```bash
chgrp newgroup file.txt
```


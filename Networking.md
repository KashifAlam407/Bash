# 🌐 ping – Check Network Connectivity

**Syntax:**
```bash
ping [OPTIONS] HOST
```

**Options:**

| Option | Description |
|--------|-------------|
| `-c`   | Number of packets to send |
| `-i`   | Interval between packets |
| `-t`   | Set TTL (Time To Live) |
| `-q`   | Quiet output (summary only) |

**Examples:**
```bash
ping google.com
ping -c 4 8.8.8.8
ping -i 2 example.com
```

---

# 🌍 curl – Transfer Data From or To a URL

**Syntax:**
```bash
curl [OPTIONS] [URL]
```

**Options:**

| Option | Description |
|--------|-------------|
| `-O`   | Save with original filename |
| `-o`   | Specify output file |
| `-L`   | Follow redirects |
| `-I`   | Show only headers |
| `-d`   | Send POST data |
| `-X`   | Specify HTTP method |

**Examples:**
```bash
curl https://example.com
curl -O https://example.com/file.txt
curl -o saved.txt https://example.com/data.txt
curl -I https://example.com
curl -X POST -d "name=test" https://api.example.com/data
```

---

# 📥 wget – Non-Interactive Network Downloader

**Syntax:**
```bash
wget [OPTIONS] [URL]
```

**Options:**

| Option | Description |
|--------|-------------|
| `-O`   | Set output filename |
| `-c`   | Continue download |
| `-q`   | Quiet mode |
| `-r`   | Recursive download |
| `--limit-rate` | Limit download speed |

**Examples:**
```bash
wget https://example.com/file.zip
wget -O custom.zip https://example.com/file.zip
wget -c largefile.iso
wget -r https://example.com/docs/
```

---

# 🔐 ssh – Secure Shell Remote Login

**Syntax:**
```bash
ssh [OPTIONS] user@host
```

**Options:**

| Option | Description |
|--------|-------------|
| `-p`   | Port number |
| `-i`   | Identity file (private key) |
| `-v`   | Verbose mode for debugging |

**Examples:**
```bash
ssh user@192.168.1.10
ssh -p 2222 admin@example.com
ssh -i ~/.ssh/id_rsa user@server.com
```

---

# 📤 scp – Secure Copy Over SSH

**Syntax:**
```bash
scp [OPTIONS] source destination
```

**Options:**

| Option | Description |
|--------|-------------|
| `-r`   | Copy directories recursively |
| `-P`   | Specify remote SSH port |
| `-i`   | Identity (private key) file |
| `-v`   | Verbose output |

**Examples:**
```bash
scp file.txt user@host:/home/user/
scp -r dir/ user@host:/var/www/
scp -P 2222 backup.sql user@192.168.1.100:/tmp/
```

---

# 🔄 rsync – Efficient File Synchronization

**Syntax:**
```bash
rsync [OPTIONS] SOURCE DESTINATION
```

**Options:**

| Option | Description |
|--------|-------------|
| `-a`   | Archive mode (recursive + preserve) |
| `-v`   | Verbose output |
| `-z`   | Compress during transfer |
| `-r`   | Recursive |
| `--delete` | Delete files not in source |
| `-e`   | Specify remote shell (like SSH) |

**Examples:**
```bash
rsync -avz dir/ user@remote:/backup/
rsync -r file.txt /mnt/usb/
rsync -av --delete local/ remote:/sync/
rsync -e ssh file user@host:/path/
```

---

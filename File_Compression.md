# 🗜️ zip – Compress Files into a ZIP Archive

**Syntax:**
```bash
zip [OPTIONS] archive_name.zip file1 file2 ...
```

**Options:**

| Option | Description |
|--------|-------------|
| `-r`   | Recursively add directories |
| `-q`   | Quiet mode |
| `-9`   | Maximum compression |
| `-e`   | Encrypt archive with password |

**Examples:**
```bash
zip files.zip file1.txt file2.txt
zip -r archive.zip folder/
zip -9 logs.zip *.log
zip -e secret.zip secrets.txt
```

---

# 📂 unzip – Extract ZIP Archive Contents

**Syntax:**
```bash
unzip [OPTIONS] archive.zip
```

**Options:**

| Option | Description |
|--------|-------------|
| `-l`   | List contents of ZIP |
| `-d`   | Specify output directory |
| `-o`   | Overwrite existing files |
| `-n`   | Never overwrite existing files |

**Examples:**
```bash
unzip archive.zip
unzip -l archive.zip
unzip -d output/ files.zip
unzip -o files.zip
```

---

# 📦 tar – Create or Extract TAR Archives

**Syntax:**
```bash
tar [OPTIONS] archive.tar [FILES...]
```

**Options:**

| Option | Description |
|--------|-------------|
| `-c`   | Create a new archive |
| `-x`   | Extract an archive |
| `-v`   | Verbose output |
| `-f`   | Use archive file |
| `-z`   | Compress with gzip (`.tar.gz`) |
| `-j`   | Compress with bzip2 (`.tar.bz2`) |
| `-C`   | Change to directory before extracting |

**Examples:**
```bash
tar -cvf archive.tar file1 file2
tar -czvf archive.tar.gz folder/
tar -xvf archive.tar
tar -xzvf archive.tar.gz -C /output/
```

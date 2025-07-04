# 📦 Bash Libraries & `getopts` (Option Parsing)

Creating modular, maintainable Bash scripts is crucial for large projects. This includes separating code into reusable files and parsing CLI flags using `getopts`.

---

## 📁 1. Creating a Library File (`lib/log.sh`)

Modular scripts allow you to split reusable functions into external `.sh` files.

### `lib/log.sh`
```bash
#!/bin/bash

log_info() {
  echo "[INFO] $1"
}

log_error() {
  echo "[ERROR] $1" >&2
}
```

### Main Script:
```bash
#!/bin/bash
source lib/log.sh

log_info "Script started"
log_error "Something went wrong"
```

---

## 🧩 2. Using `source` to Import Files

```bash
source ./utils.sh
```
or simply:
```bash
. ./utils.sh
```

This runs the file in the current shell, allowing access to its functions and variables.

---

## ⚙️ 3. Parsing Options with `getopts`

`getopts` is a Bash built-in used to handle command-line flags like `-f`, `-v`, `-h`.

### Syntax:
```bash
while getopts ":f:v:h" opt; do
  case $opt in
    f) file=$OPTARG ;;
    v) value=$OPTARG ;;
    h) echo "Help message"; exit 0 ;;
    \?) echo "Invalid option: -$OPTARG" >&2 ;;
  esac
done
```

### Example:
```bash
#!/bin/bash

while getopts ":n:a:" opt; do
  case $opt in
    n) name="$OPTARG" ;;
    a) age="$OPTARG" ;;
    \?) echo "Invalid option: -$OPTARG" ;;
  esac
done

echo "Name: $name"
echo "Age: $age"
```

Run it like:
```bash
./script.sh -n Kashif -a 24
```

---

## 🧠 Tips for `getopts`

| Symbol | Meaning |
|--------|---------|
| `:` after a letter | Option requires an argument |
| `\?` | Catch invalid options |
| `:` (before string) | Suppress error messages (silent mode) |

---

## 🔄 Optional: Long Options (with `getopt`)

Bash `getopts` does not support long options like `--help` directly. You can use GNU `getopt` for advanced parsing:

```bash
getopt -o h --long help -- "$@"
```

---

## 📌 Best Practices

| Practice | Benefit |
|----------|---------|
| Use `source` for reusable code | Cleaner scripts |
| Group related functions | Easier maintenance |
| Always validate arguments | Prevent errors |
| Provide a `-h` or `--help` flag | Friendly UX |

---

## 📚 References

- [getopts man page](https://man7.org/linux/man-pages/man1/getopts.1p.html)
- [Advanced option parsing](https://stackoverflow.com/a/402410/1084774)
- [Bash function libraries](https://linuxhint.com/bash-function-library-example/)

---

> 📁 File: `advance/libraries-getopts.md`  
> Author: [Kashif Alam](https://github.com/KashifAlam407)

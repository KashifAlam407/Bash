# 🔃 Bash I/O Redirection

Bash allows you to redirect standard input, output, and errors to/from files, devices, and other commands. This is powerful for logging, error handling, and automation.

---

## 🔢 File Descriptors

| FD  | Stream             |
|-----|--------------------|
| `0` | stdin (input)      |
| `1` | stdout (output)    |
| `2` | stderr (error)     |

---

## 📤 Output Redirection

### Overwrite output:
```bash
echo "Hello" > output.txt
```

### Append output:
```bash
echo "More text" >> output.txt
```

---

## 📥 Input Redirection

Use input from a file:
```bash
cat < input.txt
```

Can be used in loops:
```bash
while read line; do
  echo $line
done < file.txt
```

---

## ❌ Redirecting Errors

### Redirect `stderr` to a file:
```bash
ls /invalid/path 2> error.log
```

### Redirect `stdout` and `stderr` to different files:
```bash
command > out.log 2> err.log
```

### Combine both to same file:
```bash
command > all.log 2>&1
```

---

## 🔄 Use `tee` to Split Output

Write to file and show on terminal:
```bash
ls -l | tee output.log
```

Append to file:
```bash
ls -l | tee -a output.log
```

---

## 🧪 Examples

### Log everything (stdout + stderr):
```bash
myscript.sh > script.log 2>&1
```

### Silent execution (discard output):
```bash
command > /dev/null 2>&1
```

---

## 🧲 Process Substitution

Use command output as a file:
```bash
diff <(ls dir1) <(ls dir2)
```

This lets you treat the result of a command as a temporary file.

---

## 🧬 Advanced File Descriptors

### Open a new file descriptor:
```bash
exec 3> file.txt
echo "Hello" >&3
exec 3>&-    # Close it
```

### Read from descriptor:
```bash
exec 4< input.txt
read line <&4
exec 4<&-
```

---

## 📌 Best Practices

| Tip | Reason |
|-----|--------|
| Use `2>&1` for error and output logs | Easier debugging |
| Use `tee` to log and view output     | Great for scripts |
| Redirect to `/dev/null` for silence | For crons and clean logs |
| Quote filenames in redirections     | Avoid word splitting |

---

## 📚 References

- [Redirection in Bash (GNU docs)](https://www.gnu.org/software/bash/manual/html_node/Redirections.html)
- [`tee` command](https://linuxize.com/post/linux-tee-command/)

---

> 📁 File: `advance/io-redirection.md`  
> Author: [Kashif Alam](https://github.com/KashifAlam407)

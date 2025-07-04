# 🔍 Regular Expressions in Bash

Regular expressions (regex) allow powerful pattern matching in Bash. They're used with tools like `grep`, `sed`, `awk`, and even in Bash `[[ ]]` conditionals.

---

## ✅ What Is a Regular Expression?

A regular expression is a pattern that describes a set of strings. You can use it to:
- Match specific characters
- Search or replace text
- Validate inputs

---

## 🧪 Basic Regex Symbols

| Symbol | Meaning                          | Example        |
|--------|----------------------------------|----------------|
| `.`    | Any single character             | `c.t` → cat, cut |
| `*`    | Zero or more of previous char    | `lo*` → lo, loo, looo |
| `+`    | One or more                      | `lo+` → loo, looo (not just "l") |
| `?`    | Zero or one                      | `lo?` → l, lo |
| `^`    | Start of line                    | `^Hello` |
| `$`    | End of line                      | `done$` |
| `[]`   | Character class                  | `[aeiou]` |
| `[^]`  | Negated class                    | `[^0-9]` |
| `\`    | Escape special characters        | `\.` matches literal `.` |

---

## 🔎 Using Regex with `grep`

### Basic:
```bash
grep "error" logfil
```

### Extended (`-E`):
```bash
grep -E "^User: [A-Z][a-z]+$" users.txt
```

---

### Case-insensitive:
```bash
grep -i "warning" app.log
```

### Match any digit:
```bash
grep "[0-9]" input.txt
```

---

## 🧰 Regex with `[[ =~ ]]` in Bash

Bash supports regex matching inside `[[ ]]`:
```bash
text="user_123"
if [[ $text =~ ^user_[0-9]+$ ]]; then
  echo "Valid user ID"
fi
```

**⚠️ Note:**
- No quotes around regex inside `[[ ... =~ REGEX ]]`
- Use parentheses for groups like `([a-z]+)` if needed

---

## 🔁 Regex with `sed`

### Replace all numbers with `#`:
```bash
sed 's/[0-9]/#/g' file.txt
```

### Replace multiple spaces with one:
```bash
sed -E 's/ +/ /g' text.txt
```

---

## 📊 Regex with `awk`

### Match lines starting with "user":
```bash
awk '/^user/ { print $0 }' users.txt
```

### Use regex in condition:
```bash
awk '$0 ~ /error/ { print $1 }' log.txt
```

---

## 🧠 Advanced Patterns

| Pattern | Matches                          |
|---------|----------------------------------|
| `[A-Za-z0-9_]{3,8}` | Word with 3–8 alphanumerics |
| `^[a-z]+\@[a-z]+\.[a-z]+$` | Basic email format |
| `[0-9]{3}-[0-9]{2}-[0-9]{4}` | SSN pattern (e.g. 123-45-6789) |

---

## 🔒 Best Practices

- Use `grep -E` for extended syntax
- Always test with test strings before applying to files
- Use `[[ ]]` instead of `[` when doing regex in Bash

---

## 📚 References

- [Regex 101 (Test Online)](https://regex101.com/)
- [Grep & Regex Cheatsheet](https://www.gnu.org/software/grep/manual/)
- [Sed & Awk](https://www.grymoire.com/Unix/Sed.html)

---

> 📁 File: `advance/regex-patterns.md`  
> Author: [Kashif Alam](https://github.com/KashifAlam407)


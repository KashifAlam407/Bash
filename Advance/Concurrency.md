# ⚙️ Bash Concurrency & Parallelism

Bash can run multiple processes concurrently, allowing you to speed up tasks like downloading files, processing logs, or batch operations. This is useful in automation, scripting, DevOps, and data pipelines.

---

## 🧵 1. Run in Background with `&`

Start any command as a background job:

```bash
sleep 5 &
echo "Sleeping in background..."
```

Use `jobs` to list background tasks.

---

## ⏳ 2. Wait for Background Jobs

The `wait` command pauses until all background jobs finish.

```bash
echo "Starting jobs..."
sleep 3 &    # Job 1
sleep 5 &    # Job 2

wait         # Waits for both to complete
echo "All done"
```

Wait for a specific PID:
```bash
wait 12345
```

---

## 🧮 3. Background Loop Tasks

Example: Download 3 files in parallel

```bash
for i in 1 2 3; do
  curl -O http://example.com/file$i.txt &
done
wait
```

---

## 🧰 4. Parallel Processing with `xargs -P`

`xargs` can run multiple commands in parallel using `-P`:

```bash
cat urls.txt | xargs -n 1 -P 4 curl -O
```

| Option | Description                  |
|--------|------------------------------|
| `-n 1` | One argument per command     |
| `-P 4` | Run up to 4 processes in parallel |

---

## 🚦 5. Using GNU `parallel` (optional)

Powerful tool for multi-core execution:

```bash
cat files.txt | parallel gzip
```

Install it:
```bash
sudo apt install parallel
```

---

## 🔧 6. Monitor Jobs

```bash
jobs         # List jobs
fg %1        # Bring job 1 to foreground
bg %1        # Resume job in background
```

---

## 🚫 7. Kill Background Jobs

Store PID and kill manually:

```bash
my_script.sh &
pid=$!
sleep 5
kill $pid
```

---

## 📌 Best Practices

| Tip | Why |
|-----|-----|
| Use `wait` after `&` | Prevent premature script exit |
| Use `xargs -P` | Efficient for batch workloads |
| Limit background jobs | Avoid resource overuse |
| Redirect output | Prevent mixed stdout/stderr |

---

## 📚 References

- [Bash Job Control](https://www.gnu.org/software/bash/manual/html_node/Job-Control.html)
- [`xargs` parallelism](https://www.gnu.org/software/findutils/manual/html_node/xargs-options.html)
- [GNU parallel docs](https://www.gnu.org/software/parallel/)

---

> 📁 File: `advance/concurrency.md`  
> Author: [Kashif Alam](https://github.com/KashifAlam407)


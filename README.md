# 🧪 Git Conflict Practical Demo (Single File Project)

This guide demonstrates how to create and resolve a Git merge conflict using branches. Everything you need is described here — no external files required.

---

## 🔧 Step-by-Step Git Conflict Demo

### ✅ 1. Initialize a Git Repository

```bash
mkdir git-conflict-demo
cd git-conflict-demo
git init
```

---

### ✅ 2. Create and Commit a File

```bash
echo "Hello from main branch" > greeting.txt
git add greeting.txt
git commit -m "Initial commit with greeting"
```

---

### ✅ 3. Create Branch `feature1` and Modify File

```bash
git checkout -b feature1
echo "Hello from feature1 branch" > greeting.txt
git add greeting.txt
git commit -m "Change greeting in feature1"
```

---

### ✅ 4. Create Branch `feature2` and Modify File

```bash
git checkout main
git checkout -b feature2
echo "Hello from feature2 branch" > greeting.txt
git add greeting.txt
git commit -m "Change greeting in feature2"
```

---

### ✅ 5. Merge Branches into `main`

```bash
git checkout main
git merge feature1
```

✅ This merge will succeed.

```bash
git merge feature2
```

❌ This will cause a **merge conflict** in `greeting.txt`.

---

### ⚠️ Conflict Message

Git will display something like:

```
Auto-merging greeting.txt
CONFLICT (content): Merge conflict in greeting.txt
Automatic merge failed; fix conflicts and then commit the result.
```

---

### 🔍 Conflict in File `greeting.txt`

```text
<<<<<<< HEAD
Hello from feature1 branch
=======
Hello from feature2 branch
>>>>>>> feature2
```

---

### 🛠️ 6. Resolve the Conflict

Manually change the file to something like:

```text
Hello from both feature1 and feature2 branches
```

Then commit:

```bash
git add greeting.txt
git commit -m "Resolved conflict between feature1 and feature2"
```

---

## ✅ Done! Conflict Resolved

You’ve successfully:
- Simulated a merge conflict
- Manually resolved it
- Committed the resolved version

---

## 📘 Summary Table

| Step | Command | Description |
|------|---------|-------------|
| 1 | `git init` | Start a repo |
| 2 | `git add`, `commit` | Add file |
| 3 | `git checkout -b` | Create branches |
| 4 | Edit and commit | Change file |
| 5 | `git merge` | Attempt to merge |
| 6 | Manual edit | Resolve conflict |
| 7 | `git add`, `commit` | Finalize resolution |

---

## 🧠 Tips

- Conflicts only happen when the **same lines** are changed in both branches.
- Git marks them using `<<<<<<<`, `=======`, and `>>>>>>>`.
- Always test your merged code after resolving conflicts.

---

Happy Git-ing! 🚀

---

👨‍💻 **Author:** Shubham Dhole

# 🚀 Advanced Git Exercises

This repo contains step-by-step solutions to advanced Git exercises including:

- Interactive rebase
- Commit squashing
- Commit splitting using `git reset`
- Cleaning commit history using `rebase --root`
- Reordering commits
- Cherry-picking
- Visualizing commit history
- Using `git reflog` to undo mistakes

---

## ✅ Step-by-Step Git Process

---

### 🟢 Step 1: Cloning the Repo and Making Initial Commits

```bash
# Cloned the GitHub repo
git clone https://github.com/Celxine/advanced-git-exercises.git
cd advanced-git-exercises

# Created test files and made first two commits
touch test1.md test2.md
git add .
git commit -m "chore: Create initial file"

touch test3.md test4.md
git add .
git commit -m "chore: Create third and fourth files"
```

---

### 🟢 Step 2: Squashing Commits from Root

```bash
# Start an interactive rebase from the root
git rebase -i --root
```

👨‍💻 In the editor:

- Change the second commit from `pick` to `squash`
- Combine commit messages into:
  ```
  chore: Create initial file and second file
  ```

---

### 🟢 Step 3: Splitting a Commit Using `git reset`

```bash
# Go back one commit and unstage changes
git reset --soft HEAD~1

# Add and commit third file only
git add test3.md
git commit -m "chore: Create third file"

# Add and commit fourth file
git add test4.md
git commit -m "chore: Create fourth file"
```

✅ Verify using:

```bash
git log --oneline
```

---

### 🟢 Step 4: Squashing Last Two Commits

```bash
git rebase -i HEAD~2
```

👨‍💻 In the editor:

- Change second `pick` to `squash`
- Edit commit message to:
  ```
  chore: Create third and fourth file
  ```

✅ Confirm:

```bash
git log --oneline
```

---

### 🟢 Step 5: Reordering Commits

```bash
git rebase -i HEAD~3
```

👨‍💻 In the editor:

- Drag lines up/down to change commit order

📌 This is useful to group related commits together and make history cleaner before pushing.

---

### 🟢 Step 6: Cherry-Picking a Commit

```bash
# Create a feature branch
git checkout -b ft/branch

# Create and commit a file
echo "Test 5 content" > test5.md
git add test5.md
git commit -m "Implemented test 5"
```

✅ Cherry-pick into master:

```bash
git checkout master
git cherry-pick <commit-hash>
```

🧠 Use `git log` to find the commit hash.

---

### 🟢 Step 7: Visualizing Commit History

```bash
git log --oneline --graph --all
```

This helps visualize branching and merging clearly when presenting on GitHub.

---

### 🟢 Step 8: Undo Mistakes with `git reflog`

```bash
git reflog
```

🧠 This shows a full timeline of actions (rebases, branch switches, etc.)  
✅ Use it to recover lost commits or undo mistakes.

---

### ✅ Final Notes

These advanced Git techniques help clean your commit history, explain your work better on GitHub, and recover easily from mistakes.  
Practice these regularly to become confident with Git in real-world projects.
